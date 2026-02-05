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
