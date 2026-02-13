# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 7. Trust Model

The purpose of the Trust Model is to define how the services enable trust in the identity and verifiable credential ecosystem.  

>[!NOTE]
>This trust model discusses broader authentication and binding. This broader usage shouldn't be confused with the narrower and more specific definitions of [Authentication Service]() and [Binding Service]() as defined by the Trust Framework.

### 7.1 Scope
![](/media/trust-scope.png)

**Figure 1** Trust Model Scope

The scope of the Trust Model is based on the services defined under the DISTF. Each of these services plays a role in the management of verifiable credentials and identity. Some of these roles are:
-	Issuance
-	Currency/Updating
-	Verification 
-	Revocation of Verifiable Credentials and the identity attested by them
-	Managing the data at rest
-	Protecting and managing the cryptographic keys that support authentication and binding; and
-	Authentication and authorisation of their services and functions that protect the perimeter of their system access and controls to their systems.

This section defines the overall architecture of the trust model that includes the services and functions that enable the overall capability to deliver trusted verifiable credentials.

### 7.2 Trust Architecture

When developing an architecture there can be different perspectives on how you position the architecture.  Traditionally under an Identity Architecture, we would take a role-based approach.  The international standard would refer to the triangle of actors that includes the Issuer, holder and verifier:

![](/media/18013-model.png)

**Figure 2** in ISO/IEC 18013-5:2021

This Trust Architecture needs to take the perspective of the Identity Services established under the legislation and so requires the following services to be the anchor of the architecture (Section 3.1 Provides more details on Ecosystem Roles):
-	Information Service
-	Credential Service
-	Facilitation Service
-	Binding Service
-	Authentication Service

Additionally, the RA proposes two new services for consideration. They are:
-	Verifying Service
-	Trust Service 

![](/media/tfra.png)

**Figure 3** Trust Model Reference Architecture

The Trust Model Reference Architecture (TMRA) **should not be viewed as the roles under the ISO/IEC triangle**. The architecture is a range of **services** and beneath those, **functions** that enable secure and privacy preserving management of a verifiable credentials.

Any one organisation could undertake some or all the services and proposed functions in the TMRA. If we take as an example a Transport Authority that issues licences, it can simultaneously be:
-	An **Information Service** Provider, as it has a system of record that provide core attributes and attestations through a credential to a Wallet.
-	A **Binding Service** Provider, as it may undertake checks to ensure the correct information is matched to the correct user.
-	A **Credential Service** Provider, because it manages the lifecycle of their credentials end to end including issuance and revocation.
-	A **Facilitation Service**, as it may issue its own wallet to hold credentials
-	A **Verifying Service**, because their customer service centres will be a relying party of its own credentials and that of others

The architecture therefore does not specify unique functions for a role, but services being provisioned. Additionally, the structure of the legislation has determined the services that has been employed in the TMRA.

The TMRA has as a primary goal, to develop an architecture that is role agnostic but defines the core functions that are required to be considered when being accredited and managed under the DISTF.

Note: Not all functions need to be present to deliver a DISTF service, e.g. 3.6 Wallet SDK may not be provided by all Wallet providers.  However, the purpose of the TMRA is to ensure that if the function under the service exists, it is understood and context is provided to which services it belongs to.



Here is a tightened and clearer version, keeping the intent but making the distinction explicit and consistent. Written in GitHub-friendly Markdown, with straightforward language and NZ spelling.


#### 7.2.1 Authentication and Binding Services vs Broader Authentication and Binding

Under the New Zealand Identification Standards:

* An **Authentication Service** is a digital identity service that enables a person to use an authenticator to access a service (see Section 5.8 Authentication Service).
* A **Binding Service** is a digital identity service that binds a person and or organisation (entities) to their entity information (see Section 5.6 Binding Services).

These definitions describe specific **services** as regulated under the Trust Framework. They are primarily concerned with Customer to Service (C2S) interactions, where a person authenticates and is bound to identity information in order to access a service.

More broadly, however, **authentication and binding** occur throughout an identity ecosystem. They are not limited to the interaction between an individual and a service, but exist end to end between all participating entities, systems, and infrastructure components.

For completeness, the trust model therefore considers authentication and binding across the entire ecosystem. While legislation and regulation appropriately focus on C2S Authentication and Binding, the trust model additionally includes:

* **Business to Business (B2B) Authentication and Binding**
* **Machine or Device to Machine or Device (M2M) Authentication and Binding**
* **Trust-level Authentication and Binding**, where cryptographic keys act as roots and chains of trust, and are bound through cryptographic trust registers. This enables decentralised verification of data, provenance, and levels of assurance.

Throughout this section, the terms *authentication* and *binding* are therefore used to describe this broader, ecosystem-wide concept, rather than only the regulated Authentication Service or Binding Service as defined under the Trust Framework.


### 7.3 Services and Functions Architecture Dictionary

The following sections provide a high-level overview and definition of the services and functions as defined by the TMRA.

> [!NOTE]
> For each of the primary services defined by the Trust Framework (Information Service, Credential Service, Facilitation Service), this architecture describes an instance of authentication and binding relevant to that service.

As outlined in Section 7.2.1, authentication and binding are used in the TMRA in a broader sense than the specific Trust Framework services.

* **Binding Services under the DISTF** are defined as digital identity services that bind a person and or organisation (entities) to their entity information. In a verifiable credential ecosystem, binding also refers to the cryptographic trust fabric that ensures participating products, infrastructure, and entities provide non-repudiation that they are who and what they claim to be. All components must be able to assert and verify trust through cryptography, which is why these functions are defined within the TMRA.

* **Authentication Services under the DISTF** are defined as digital identity services that enable a person to use an authenticator to access a service. The TMRA extends this concept to include all authentication events within the trust fabric of the identity ecosystem. Each authentication point represents a potential attack vector, and weaknesses at any point can compromise the integrity of the system as a whole.

In summary, the DISTF Authentication and Binding Services are focused on how a holder is authenticated and bound, primarily through the facilitation service. The TMRA takes a system-wide view, examining how binding and authentication occur across the entire digital credential ecosystem in order to support end-to-end trust, resilience, and secure credential lifecycle management.

#### 7.3.1 Information Service

![](/media/info-service.png)

Purpose: the Information Service primary purpose is to be the root of trust from a cryptographic trust anchor for a credential as well as the source of data that populates the credential and the attestations of identity and other attributions.  
Cryptographically, the information service must also sign the attributes and attestations with its signer to ensure the data can provide non-repudiation both online and offline.

**1.1 System of Record**

This is the root source of the data/attributes and attestation for an issuers credential.  This data source is used to produce mobile Document (mDoc) + Mobile Security Object (MSO).  The system of record can also contain biographic data including images (encoded for example in Base 64).

**1.2 Biometric Service** (Optional)

This is the service that captures and manages the biometric data and generates the biometric templates (which are often unique to each platform due to the proprietary algorithms applied by each vendor).  

**1.3 App/Website for customers**

The Information Service Provider may have an app or website used in the update of data and biographic information (e.g. offering the ability to update address details). This app or website will include some level of authentication to access that service. 

**Authenticating**

**1.4 Service Integration**

An Information Service may choose to integrate and orchestrate its services through a service integration layer. This can be in the form of Restful API’s, event triggered containerised Micro Services and other forms (The TMRA is not prescriptive on types of integration).  

This layer would have varying levels of authentication between internal and externally exposed end points to systems, platforms and managed services.

**1.5 Authentication and Authorisation (Authn and Authz)**

This specific authentication connects the Information Service with the Credential Service.  

There may be in certain circumstances where the information service procured has also a credential service capability built into it but would normally be separated from an administrative purpose.  

Under separation of duty requirements in several security standards some level of separation of roles and responsibilities are required between those who manage the information system proper and the actual generation of credentials. This is to minimise the risk of internal actors having access end to end of the enrolment and issuance of credentials and then able to hide logs and audit trails because of their administrative access.

These Authentication and Authorisation process may be a combination of:
-	Machine to Machine Authentication through certificates via mutual Transport Layer Certificate (mTLS)
-	OIDC Connections between platforms.
-	Internal authentication to the system of record versus access to users need to have separated authentication and roles. Refer to the NZISM to understand the minimum-security controls that need to be applied.   This should be at a protected level.

**1.6 Passkeys and Credential Authentication**
This is specific authentication to online websites by the customer/user and in some cases, these could include service centre kiosks. A Service Kiosk connected to an online service allows customers or holders of a verifiable credential to update or manage in some way the data and attestation when onsite. (Kiosks are either an App directly connected to the system of record platform or are rendered version of existing online self-services but provided as a convenience for customers at a service centre)

It would be recommended that these kiosks that use a rendered online service enable either:
-	ISO/IEC 18013-7 with a reverse QR Code (which uses CTAP and Passkeys)
-	Biometric Authentication bound to source
-	Or a combination of the above for high assurance transactions

**Binding**

These binding services refer specifically to cryptographic bound services.  The Information Service uses their cryptographic signatures to confirm the data attributes and attestations in credentials (each data attribute and attestation is digitally signed in ISO/IEC 18013 and 23220 to allow minimum data disclosure).  

Whilst the credential service may undertake the document preparation it is the information service that uses its signature to attest that the data comes from their source of truth.  This is a particularly important distinction if there is a credential broker that generates multiple document types. 

**1.7 Issuing Authority Certificate Authority (IACA) Certificate**

This is the verifiable credentials root of trust and can only be issued by those who can confirm the data sealed in a credential is true and accurate.   The private keys corresponding with the IACA Certificates are used to sign.
-	(2.7) Document Signer Certificates that will be used to sign the mDocs and Mobile Security Object (MSO)
-	(2.8) MSO Revocation List (MRL) Signers which in turn are used to sign the MSO Revocation Lists

Additionally, the public keys of the IACA Certificates are hosted on the (5.3) Issuer Trust list, known in ISO/IEC 18013-5 as the Verified Issuer Certificate Authority List (VICAL).

**1.8 ISO/IEC Certificate Authority Service**

This Certificate Authority Service includes the physical Hardware Security Module (HSM) that stores and manages the digital keys.  The private keys used for signing are stored within the HSM that is tamper resistant.

**1.9 Mutual Transport Layer Security (mTLS) Signer**

To protect the connection between systems/platforms the connection must be encrypted, and industry best practice is the use of TLS.  The mTLS signer generates the necessary cryptographic keys and certificates to support that authentication.

#### 7.3.2 Credential Service

**Purpose**

The credential service primary purpose is the lifecycle management of the credential proper.  This includes managing the instantiation, storage, revocation and final disposal of the verifiable credential. 

The credential service has also a significant role in acting as the gateway between the facilitation service and the information service.  Where traditionally federated systems would also keep attributes and be an identity provider (IDP) in its own right, its primary role is to package the data in the MSO and ensure all the relevant document preparation and digitally signing occurs to ensure binding an entity to its attributes.

![](/media/cred-service.png)

**2.1 Data matching**

The role of the Credential Service as part of enrolment and issuance of a credential will be required to do the data matching as part of the Identity Proofing requirements also know in NIST as Identity Assurance Levels (IAL).  

Data matching is where the holder provides details they have (usually data attributes contained in an existing physical document) and the credential service matches/compares that to the system of record to prove they have at least had the same information on what is on the physical credential.  A positive match allows the holder to support the identity proofing/ IAL process.

**2.2 Biometric Matching**

This is where the Credential Service provides a current image from the Facilitation Service and uses this to match that with the issuing authority source image.  Biometric matching is a probabilistic test.  This is used at the point of enrolment to provide higher authentication confirmation that the holder of the documents are who they say they are.

**2.3 Credential Management**

Whilst many of the other subdomains would traditionally also fall under credential management, in the RA, this refers to the larger system/platform that undertakes the overall lifecycle management of the credential.  

This includes the management of enrolment/issuance, revocation as well administrative functions like auditing, establishing roles and controlling access to the credentials.  The credential management function should also provide data protection of the credential data through the various processes it supports and may have automated functions like error handling and orchestration of data as it manages credentials through its various life stages.

**2.4 Administrative Portal and/API management for the Issuer**

This is the online administrative capability that gives the issuer access to 2.3, the Credential Management Service, which may also give the issuer the ability to change the workflow of the credential management and/or update API’s back to the System of Record to manage the change/map to new data types and data sources.

**2.5 The mDoc and MSO**

This function produces mdocs + MSOs according to the applicable doctype(s) and namespace(s) using the data of the 1.1 System of Record, the deviceKey, and the Document Signer.

**2.6 Document preparation**

This is the preparation work that creates 2.5 the mDoc and MSO after the user has undertaken the relevant level of identity proofing and authentication through the credential management.  It works with the Document Signer that signs the MSO and ensures the device public key is accompanied by key attestations and attributes to prove that the private key is protected by the secure area of the wallet (creating the device binding).

**Authentication**

2.10 Authentication and Authorisation 
This specific Authentication and Authorisation service allows the Credential Service Provider to connect to the Information and Facilitation Service primarily to undertake to support the following:
-	Data matching
-	Biometric Matching to source
-	Retrieve data for document management
-	Exchange of Certificates
-	Enable Signing
-	Revocation
-	Binding the device key and the IACA to the MSO to finalise document preparation

These Authentication and Authorisation process may be a combination of:
-	Machine to Machine Authentication through certificates via mutual Transport Layer Certificate (mTLS)
-	OIDC Connections between platforms

**2.11 Service Integration**

A Credential Service may choose to integrate and orchestrate its services through a service integration layer.  This can be in the form of Restful API’s, event triggered containerized Micro Services and other forms.  This layer would have varying levels of Authentication between internal and externally exposed end points to systems, platforms and managed services.

**2.12 Authentication and Authorisation Services**

This specific authentication connects the Credential Service with the Facilitation Service. There may be in certain circumstances where the Credential service procured has, as part of the same platform, Facilitation Service capability.  There would still be some level of separation of roles and responsibilities between those who manage the information system proper and the actual generation of credentials to minimise the risk of internal actors having access end to end of the enrolment and issuance of credentials.

These Authentication and Authorisation processes may be a combination of:
-	Machine to Machine Authentication through certificates via mutual Transport Layer Certificate (mTLS)
-	OIDC Connections between platforms.  Note under New Zealand DISTF requirements, no server retrieval can be employed. This means no OIDC or Data integration exists between the Verification Service/Relying Party and the Information or Credential Service to prevent tracking. 

Refer to the NZISM to understand the minimum-security controls that need to be applied to these services. This should be at a protected level.

**Binding**

**2.7 Document Signer**

The use of the private keys that correspond the Document Signer Certificates that are issued by the IACA of the Issuing Authorities to sign the MSOs.  The MSOs are used for issuer authentication on behalf of the Issuing Authority.

**2.8 mTLS Signer**

To protect the connection between systems/platforms the connection must be encrypted, and industry best practice is the use of TLS.  The mTLS signer generates the necessary cryptographic keys and certificates to support that authentication.

**2.9 MSO Revocation Certificate**

When data is changed or a certificate is revoked it transitions to an MSO Revocation Certificate.  These MSO Certificates are listed on the MSO Revocation List by the Trust Service and provide relying parties’ notification that the verifiable credential has either been updated or revoked.

#### 7.3.3 Facilitation Service

**Purpose**

The facilitation service purpose is to hosts the mDoc/MSO and is the go-between of the Credential Service and the Verifying Service.  It works together with the Credential Service to use its capabilities to facilitate enrolment and following ISO/IEC 18013-5 have special privacy and security protections that include:
-	Secure element storage of the mDoc/MSO
-	Stopping screen scraping/capture
-	Inability to see data within the credential
-	Selective disclosure

In many ways the facilitation service primary role is to act as the front-end for users and a conduit between services to support the lifecycle management for on device/server credential management.  The Facilitation service must not be able to interrogate, leak or change any part of the credential, digital certificates or data attributes contained within the MSO.

![](/media/fac-service.png)

**3.1 Biometric Capture and Matching**

The Facilitation Service can capture on device biometrics of the individual.  In the case of a wallet, that is device generated biometrics that uses the devices camera or fingerprint scanner to establish the baseline biometric for on-device verification of a person.  

This access is then used to access the facilitation service functions and provide the holder to use the verifiable credential.   This same service can be used to also capture a biometric and test for liveness before sending that metadata and device source images back to the credential service who will undertake the matching back to issuers source image.

**3.2 Client Side Transaction Log**

Under ISO/IEC 18013-5 the Facilitation Service has a client only transaction log which allows the holder to “view an audit trail of their interactions with mDL readers. To accomplish This, mDLs should, at the mDL holder's choice, log information about each transaction in a form that can be reviewed by the mDL holder. The mDL should not make the transaction log available to anyone other than the mDL holder, except at the mDL holder's direction.”

**3.3 Selective Disclosure**

The facilitation service must provide selective disclosure of data attributes and attestations, contained within the mDoc, for the holder to provide to the verifying service. As each attestation and data attribute is individually signed and cryptographically bound with the issuer, there is no need to share Personal Information (PI) for disclosures like Age.  

This is an inherent capability of any facilitation service that requires their customer to share or provide data to a verifying service.

**3.4 Wallet App**

The Wallet App itself can contain several functions.  The above capability may all be functions within a Wallet App.  However, the Wallet App needs to comply with ISO/IEC 18013-5 and there are controls that need to be further considered.

**3.5 Administration Portal (User)**

A Wallet provider may provide in App and sometimes online capability to manage the credentials they are responsible for.  This capability may for example provide the capability to revoke the credential from a lost phone for instance.  This needs to be managed within a secure element and only in the same native App environment the credential was originally issued in (e.g. Not an external website) owing to its device bound requirements.  

**3.6 Wallet Software Development Kit (SDK)**

Wallet/Facilitation providers my require Credential Service providers to install their specific SDK into their App to provide secure and tighten the integration between services and platforms.  This may be provided also by OEM Wallet providers to ensure closed connectivity to their on device secure elements. 

**3.7 Wallet Certificate Signer**

In a mobile phone there is a chip that forms the secure element/enclave for a digital wallet.  This can be used to generate and store keys.  The Wallet Certificate signer sends data to the secure element that uses the stored private key to generate a digital signature.

**3.8 Service Integration**

A Facilitation Service may choose to integrate and orchestrate its services through a service integration layer that connects to the Credential Service provider.  This can be in the form of Restful API’s, event triggered containerized Micro Services and other forms.  This layer would have varying levels of Authentication between internal and externally exposed end points to systems, platforms and managed services.

**3.9 Authentication and Authorisation**
Refer to Section 5.8 Authentication Service for more details and a list of authenticators

This specific Authentication and Authorisation service allows the Facilitation Service Provider to connect to the Credential Service primarily to do five things:
-	Data matching
-	Biometric Matching to source
-	Retrieve data for document management
-	Exchange of Certificates
-	Enable Device based signing

These Authentication and Authorisation process may be a combination of:
-	Machine to Machine Authentication through certificates via mutual Transport Layer Certificate (mTLS)
-	OIDC Connections between the facilitation and the credential service

Security controls need to comply with the NZISM and meet protected requirements.  

**3.12 Device Key**

This is a cryptographically generated key that is used for mdoc authentication and shall be used to create a DeviceMac or DeviceSignature. The public key of the Device Key shall be sent to the Credential Service so that it can bind this to the information service attributes and IACA as part of the creation and document preparation of the mDoc/mSO.

#### 7.3.4 Verifying Service

>[!NOTE]
>Under the DISTF, a verifying service isn't defined or an accreditable service. However, we're open to feedback on whether this should change and whether verifying services see value in accreditation under the DISTF

**Purpose**

The purpose of a Verifying Service is substantially to support the relying party verify and where required store and lifecycle managed the stored credential as part of providing a product or service.  

As part of that reliance, they may request and store data and compare the biometrics on the credential with what is captured at the point of verification (just in-time) or captured previously on their system (which in turn can make them an information service provider).  As such they should have controls in how they store, capture and undertake matching of data and biometrics.

![](/media/ver-service.png)

**4.1  Reader or verifier**

A device or capability that allows either in person or online verification of a verifiable credential.  This can request just an attestation or seek further information stored in the mDoc.  This reader can authenticate the wallet to confirm the authenticity of the device and relying party.  Authentication is only necessary if there is a request for personal identifying information (PII).

**4.2 Data Repository**

This is the repository of where meta data and selectively disclosed PII will be held.  This will be required to comply to relying party privacy requirements and PII data requirements under the New Zealand Privacy Act.

**4.3 Biometric Capture and Match**

This is where the relying party stores its own biometrics for the purposes of matching with a verifiable credential.  This may include storing the biographic data and images of an individual temporarily or for a period in the Data Repository.

**4.4  Reader and relying party signer**

This is used to store and generate keys for the verifying device and the relying party.  This generates a digitally signed certificate as part of the PII data request.  This signs each individual data attribute provided by the verifying service to the digital wallet Apps 3.2 Client Transaction Log.  This provides a level of immutability and non-repudiation of any data and privacy commitments/attestations provided by the verifying service.

**4.5  Relying Party CA Certificate**

This is the device/reader root certificate used to verify the authenticity and identity of a device used to verify a credential.  This is used to provide non-repudiation of device or system requesting the data attributions and claims.

**4.6  Reader Signer**

The use of the private keys that correspond the Reader CA Certificates that are issued by the relying party to ensure that the device (online or in person) is a device registered by the relying party.  

### 7.3.5 Trust Services

>[!NOTE]
>Under the DISTF, a trust service isn't defined or an accreditable service. We don't expect this to change, as the **Trust Framework Authority** is the only regulator in New Zealand and is solely responsible for maintaining the list of accredited (or trusted) services.

**Purpose**

The trust service purpose is to provide the verifiable credential ecosystem confidence that the products and actors withing a digital identity ecosystem can be trusted and the attestations and data provided can also be trusted. 

The trust service does this by hosting the public keys of the various providers in the systems chain of trust so that providers, products, devices, data and attestations can be cryptographically proofed and provide non repudiation of the claims made within the ecosystem.

![](/media/trust-service.png)

**5.1 Trust List Signer**

Any Trust List that holds public certificates should be signed to provide authenticity that the list has been provided by an accredited Trust Service Provider.  Whilst the public certificates can be easily copied and circulated by others, the primary threat to a trust list is the injection of keys from bad actors.  The Trust List signer ensures that each of the trust lists provided by the trust service provider can be cryptographically proven.

**5.2  MSO Revocation List**

Under ISO18013-5 there are two types of revocation lists:
-	Attestation Revocation List (ARL) which provides a list of identifiers for attestations that have been revoked.
-	Attestation Status List (ASL) which provides a bit string (or a group of them) that represents the status of a specific attestation.  This provides more granular checking of the status and attestation.
In short, this list provides relying parties/verifying services an easy way to check whether the verifiable credentials or the attestations presented have been revoked or updated.

**5.3 Issuer Trust List**

Under ISO/IEC 18013-5 this is known as the Verified Issuer Certificate Authority List (VICAL) where the issuer hosts its IACA public keys to allow verifiers/relying parties to confirm that the credential was issued by a truster issuer.

**5.4 Wallet Trust List**

This is not currently proposed for the New Zealand Context as it will only choose to put accredited credentials in trust wallets.  However, if there is a Wallet Accreditation service the trust list could contain Wallet public keys of Wallet providers.

**5.5 Reader Trust List**

This lists the signed device reader public certificate to provide confidence to users that the reader can be identified and trusted as part of the larger verifiable credential ecosystem.

**5.6 Trust List Portal**

A Trust list provider might have an intermediate area for service providers to upload their public keys.  This should not be an immediate upload to a public site, but a holding location that will have a proper key ceremony to determine the authenticity of the key being provided and those providing it are legitimate administrators and owners of those keys.
