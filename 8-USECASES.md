# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 8. Use Cases

This Reference Architecture (RA) will be driven by use cases.  There are some sections of the RA that will be referenced by many use cases e.g.
-	Trust Model
-	Levels of Assurance
-	Enrolment, verification, update and revocation of the credential 
-	Channels of engagement
-	Privacy, Accessibility and Inclusion requirements

Where there may be difference between use cases are in the areas of:
-	Governance
-	Data Models and namespace
-	Data Flows
-	Minimum levels of trust
-	Functions in the ecosystem

For each use case the following sections will be incorporated.
-	**Overview:**  Provides the scope and context of how this use case is being considered.
-	**High level workflow:**  The functions and data flow between the different services to support the use case.
-	**Channels of verification:** The channels that are available for the verification of the digital credentials
-	**Legislation, Regulation and Standards:**  The legislative and regulatory consideration and standards underpinning the use cases
-	**Data and claim assertions:**  The minimum data attributes that are required to deliver on this use case, where data minimisation is a core principle.
-	**High level benefit profile:**  High level benefits of the use case
-	**High level risk profile:** High level risks of the use case and high-level mitigations available

### 8.1 Licence Credential

#### 8.1.1 Assumptions

This use case is focused on the enrolment of an existing regulated credential where the individual has already:
-  Established their identity for the Information Service provider
-  That credential is current and not revoked
-  Facilitation service is a digital wallet
-  Following a happy path (no errors or poor customer experience)

>[!NOTE]
>The workflows do not denote any security controls and is provided as a high-level flow between services and functions. Future iterations of the RA will move the workflow into a Unified Modelling Language (UML).

#### 8.1.2 Overview

When government organisations issue a licence credential like a driver licence, it is often underpinned by statutory or regulatory requirements. Often these licence credentials are accompanied by an qualification process to ensure the holder is safe or deemed capable of undertaking or doing a task, role or occupation.

A regulated credential might be:
-	Capable to drive a class of vehicle (Driver Licence)
-	Safe to work with children (Children’s Worker Safety Check)
-	Occupational Licences like:
    -  Electricians (Electrical Workers Registration Board)
    -  Plumbers, Gasfitters and Drainlayers (Plumbers, Gasfitters and Drainlayers Board)
    -  Educational and social services (Social Workers Registration Board)

There are many other credential types, but this will focus on a generic regulated credentials and use the Mobile Driver Licence (mDL) standard to highlight how you may support the extensions of the data model and namespace to accommodate new credential types.

#### 8.1.3 High Level Generic Workflows
The following workflow uses the services and functions represented in the 7.0 Trust Model.  This is based on an enrolment through an existing wallet.  (There could also be pre-authorisation through other channels).

<ins>**Enrolment**</ins>

![](/media/8-enrolment.png)

**High Level Flow:**
1.	A user opens their **3.4 Wallet App** and undertakes device-based authentication
2.	The Information service through the credential and facilitation service, undertakes identity proofing process to check that a real person is part of this process.  Subject to the level of assurance required, additional authentication and identity proofing may be undertaken.
3.	In this example the user takes a (**3.1 Biometric Capture and Matching**) selfie that will be compared to their photo from the system of record provided by the Information Service provider.
4.	The user can either scan an existing card or manually enter attributes from the credentials for matching.
5.	The Credential service does image matching on the selfie capture from the Information Biographic image stored in a **1.1 System of Record**
6.	The Credential service does data attribute matching to support Identity Proofing to the Information Service **1.1 System of Record** (Note this could be one or more system of records)
7.	The Credential broker sends a message to inform the Facilitation that a new mdoc can be retrieved. This message includes the **1.8 ISO/IEC Certificate Authority Service** Static Public Key. 
8.	The Facilitation Service:
    -  Generates a **3.12 Device Key**
    -  Generates a Wallet Ephemeral Key for Issuing Authority
    -  Does key agreement use the **1.7 Issuing Authority Certificate Authority** (IACA) Certificate Static Public Key and the private part of the Wallet Ephemeral Key for Issuing Authority
    -  Encrypts the public part of the Device Key with the key to the previous step
9.	The Facilitation Service forwards the message of the previous step to the Credential Service
10.	The Credential Service undertakes **2.6  Document preparation** (For more detail on the binding in this step go to: **5.6.4 Device-Credential Binding**)
    -  Undertakes the key agreement using the private part of the Issuing Authority Static Key and the public part of the Wallet Ephemeral Key for Issuing Authority
    -  Decrypts the public part of the 3.12 Device Key with the Wallet Ephemeral key of the previous step
    -  Generates an mdoc and MSO using the public part of the **3.12 Device Key**
    -  Encrypts the mdoc and MSO based on key agreement between the Device Key and the Ephemeral key.
    -  Sends the encrypted mdoc and MSO to the Facilitation Service
11.	The Facilitation service stores the mDoc and MSO in secure element/enclave that is only accessible by the user.
12.	The Facilitation service sends an encrypted proof of provisioning to the Credential Service
13.	The Credential Service informs the Information Service that an mdoc is issued

<ins>**Revocation and update of a credential**</ins>

When you add or delete a credential, the process of doing this is substantially the same as when a mDoc and MSO is removed. For a change of data or removal of the credential, the differences are: 
-  The current mDoc and MSO is replaced with the news mDoc and MSO for a change, versus total removal for a change.
-  The message from the credential service to both the information service and facilitation service notes a removal versus a change
-  Facilitation service provides a message that it has removed the credential rather than just updated this. 

What is important to understand is that a credential has generally two uses that is worth noting.  
1.	What it licences. A driver licences is for instance a licence credential that attests when current, your eligibility to continue to drive.
2.	An identity, used for age attestation, or access services, where relying parties are not generally concerned about the licencing claims. In the case of a driver licence your driving privileges is not needed to prove you are over 18 and a form of identity.

Therefore, careful policy considerations need to be undertaken as to whether a full revocation is necessary. E.g. someone can be suspended from driving, but the individual may be permitted to keep at least their digital credential to allow them to continue to use the credential as a digital identity.

Other reasons for revocation could include:
-	Expiry of the credential
-	Status of credential change
-	Change of class or type of licence
-	Fraud identified
-	Issuer updates cryptographic key series
-	User decides to revoke the credential because (and not exclusively), they:
    -  Have been a victim of fraud, and want to remove the instance themselves
    -  Are wanting to install licence on other devices and have reached that maximum install limit
    -  Ex partner has access to their licence

Depending on the reasons for changing attributions and revoking a credential and who undertakes it will be subject to policy, privacy, accessibility and information security requirements.

**Assumption of this workflow:**

This revocation is based on: 
-	The Information Service provider administrator (the Issuer) revoking the credential 
-	This is either done through their primary enterprise system that manages the user’s data and attestations: or 
-	Through an administration portal managed by the Credential Service provider
-	A ‘happy path’ scenario’.

![](/media/8-revocation.png)

**High Level Flow**
1.	An Administrator of credentials either goes through an Enterprise system connected to their **1.1 System of Record** or **2.4 Administrative Portal and/or API management for the Issuer** that is linked to the **2.3 Credential Management**.  The Credential Management platform should be exclusively under the management of the Issuing Authority.
2.	The **2.3 Credential Management** function gets a request to change or delete the credential and adds the relevant **2.9 MSO Revocation Certificate** related to the user, to the **5.2 MSO Revocation List**. 
3.	The **2.3 Credential Management** function sends an mDoc and MSO deletion message to the Facilitation Service
4.	The Facilitation Service deletes the mDoc and MSO from the **3.4 Wallet App** and in the case of an update, replaces the previous mDoc and MSO with a new one.
5.	The Facilitation Service sends a proof of deletion/update to the **2.3 Credential Management/service**.
6.	The **2.3 Credential Management** function deletes the **2.9 MSO Revocation Certificate** from the **5.2 MSO Revocation List**.
7.	The **2.3 Credential Management** sends a proof of deletion/update back to the **1.1 System of Record**.

#### 8.1.4 Channels of Verification

The verification of selectively disclosed data is available across two authenticated channels.
1.	In-person presentation where you have a choice of three protocols (which can operate also offline)
    -  Rotating QR Code with Bluetooth Transfer
    -  Near Field Communication (NFC) 
    -  Wi-Fi Aware that allows nearby Wi-Fi devices to discover, pair and exchange data
2. Online presentation using ISO/IEC 18013-7 using three Annexes that are not aligned. As all OEM wallet providers support Annex C, this is currently the preferred method to use the W3C Digital Credential API for online verification combined with a Passkey for authentication. The other Annexes in ISO/IEC 18013-7 are being also reviewed for either replacement or deprecation.

Regardless of channel and dependant on the Level of Assurance required, the mDoc and MSO has the ability to undertake biometric matching even when offline.

#### 8.1.5 Data and claim assertions in the Mobile Security Object (MSO)

You will note that the mDoc (Mobile Document) and MSO (Mobile Security Object) is often used together (sometimes inseparable or the term mDoc is only used).  The mDoc contains the credential data structure, subset of claims and namespaces (9.1 Internationally name spaces for specific use types). These are presented to the Verifying Service as part of the selective disclosure process to a 4.1 Reader or verifier.

The MSO has encrypted (salted hashes) of the corresponding data elements and claims to provide the non-reputable attestation of the data and claims being made.

![](/media/8-mso.png)

Each data element and claim is digitally signed by the Issuing Authority Certificate Authority (IACA).  In the example above age_over_18 attestation is digitally signed by the Issuing Authorities IACA.   This allows only the selectively disclosed attestation (and not the date of birth) to be provided and stored by the verifier, protecting the privacy of individuals when stored by a third party.

When verifiable credentials say that they are cryptographically bound and verified, this key signing and subsequent pairing at verification is the core of how data and claims/attestations can be trusted.

The Trust Lists like the ISO/IEC 18013-5 Annex C Verified Issuer Certificate Authority List (VICAL) hosts the public IACA keys. That allows then any verifier to cryptographically match the signed data claims and data to provide nonrepudiation that the data was provided by the claimed issuer.

The mDoc in combination with the MSO is stored in a Secure Element of a device or smart storage and can work offline without having to check back to the issuer on the validity of the claims.  For age attestation that is particularly true as you never get younger (once you are over 18 you remain over 18).  The verifying service can check whether there is any change or revocation of the mDoc and MSO by checking an MSO revocation list (which is also a cryptographic trust list) that does not store any Personal Information (PI).

#### 8.1.6 Verification of Age
In Section 2.5.1.3 we showed how age attestation is formed in the mDoc and encrypted in the MSO.  The data elements covering age in ISO/IEC 23220-2 is below:

| Data element                                                     | Data element identifier | Description                                                                                                                                                                      | Encoding               |
|------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|
| Age attestation: How old are you (in years)?                    | age_in_years              | The age of the holder                                                                                                                                                            | uint                   |
| Age attestation: In what year were you born?                    | age_birth_year            | The year when the holder was born                                                                                                                                                | uint                   |
| Age attestation: Nearest “true” attestation above request       | age_over_NN               | This set of elements is used to convey to a verifier, in a data-minimized fashion, if the holder is as old or older than a specified age, or if the holder is younger than a specified age. | bool                   |
| Date of Birth                                                    | birth_date                | Day, month and year on which the holder was born. Unknown parts (i.e., year, month, day) are masked with 1                                                                     | full-date |


It is recommended that if the Date of Birth is being used as a data element, then age attestations are also made available so that users can provide privacy preserving attestations of their age without disclosing their date of birth.

![](/media/8-age.png)

**High Level Age Attestation Flow**
1.	A user validates their credential with a **4.1 Reader or verifier** and does ephemeral key pairing and agreement with the reader/verifier.
2.	The verifier encrypts a request and asks for data, and in a happy path for age verification, only the age attestation. If it is storing the date of birth or other Personal information in **4.2 Data Repository**, it will be recommended it undertake reader authentication.  This ensures that each data element stored in the verification service data repository is signed and non-reputable as a privacy agreement
3.	The **3.4 Wallet App** receives the request and if reader auth with Reader CA Cert is provided, it is matched with **4.5 Relying Party CA Certificate** that is in the 5.5 Reader Trust List
4.	If the **4.5 Relying Party CA Certificate** is matched, the user undertakes the **3.3 Selective Disclosure** and picks the age attestation.
5.	The **4.1 Reader or verifier** receives the mDoc and checks with the **5. Trust Services** whether MSO is current in the **5.2 MSO Revocation List** and assuming it is continues.
6.	The **4.1 Reader or verifier** matches the mDoc IACA with the **1.7 Issuing Authority Certificate Authority (IACA) Certificate** is on the **5.3 Issuer Trust List**. If all confirmed the **4.0 Verifying Service** stores just the attestation (as it relates to just age assurance, or can retain data (if further attributes are selectively disclosed by the user) in its **4.2 Data Repository**.
7.	The **4.1 Reader or verifier** sends a confirmation of the verification and retention (if it is retained) to the **3.4 Wallet App**.
8.	The facilitation service will then write the data treatment in the **3.2 Client-Side Transaction Log** (that is stored in the secure element/enclave of the device only accessible to the user).

#### 8.1.7 Data model of a verifiable credential

For more information on data models and namespace, go to section 9.1 Internationally name spaces for specific use types.   For each Document/mDoc type, a set of data model can be prescribed. 

The recommendation is to start with a base PhotoID data model (even if you do not have a photo, you can make the image optional).  Refer to nz.govt.digital.common1 namespace for the minimum data elements and attestations.  (Refer to Section 9.2.1 Photo IDs derived from ICAO 9303 compliant ePassports and eIDs)

As each document type is developed the extension of the data model should take into consideration:
-	Any existing international standard namespace prescribed for your credential type if you are seeking verification of international credentials in New Zealand, or for New Zealand credentials to be verified overseas.  Current international examples include:
-	PhotoID documentType:  org.iso.23220.photoid.1
-	Driver licences in an mDL documentType:  org.iso.18013.5.1
-	Mobile Vehicle Registration documentType: org.iso.7367.1.mVRC
-	International Vaccination Certificate documentType : org.micov.1
-	Any data models being prescribed for your industry, whether through international standards (that may not yet be digital) or in New Zealand/Australia that can be used as a data and claims model for your proposed accreditation verifiable credential.
-	Prior to finalising your own namespace and data model for your credential document type refer to the section 9.2 Data models and Document Types

#### 8.1.8 Legislation and Regulation and Standards for your consideration
As accredited credentials will generally have been created as part of legislative and regulatory instrument to ensure compliance, you should seek first the legislation, regulation and organisational policy that may have been established to provide guidance on the original physical certified credential.

Additional considerations include:
-	[The Digital Identity Services Trust Framework Act 2023 ](https://www.legislation.govt.nz/act/public/2023/0013/latest/LMS459583.html)
-	[New Zealand Privacy Act 2020](https://www.legislation.govt.nz/act/public/2020/0031/latest/LMS23223.html)
-	[New Zealand Identification Standards](https://www.digital.govt.nz/standards-and-guidance/identity/identification-management/identification-standards)
-	[New Zealand Mandated Data Standards](https://www.digital.govt.nz/standards-and-guidance/identity/identification-management/identification-standards/authentication-assurance-standard)
-	[New Zealand Information Security Manual (NZISM)](https://nzism.gcsb.govt.nz/)
-	[ISO/IEC 23220-2](https://www.iso.org/standard/86782.html) and [23220-4](https://www.iso.org/standard/86785.html)
-	[ISO/IEC 18013-5](https://www.iso.org/standard/69084.html)
-	[ICAO Doc 9303 Machine Readable Travel Documents](https://www.icao.int/publications/doc-series/doc-9303)

