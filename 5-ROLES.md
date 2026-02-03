# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 5. Digital Identity Ecosystem Roles

### 5.1 Overview

The Digital Identity Ecosystem in New Zealand is underpinned by the Digital Identity Services Trust Framework Act 2023. The legislation identifies two administering bodies:

-  **Trust Framework Board (TFB)**: Drafts the rules and regulation for Ministerial consideration.  The TF Board is support by the Ministerially appointed Māori Advisory Group to:
    - Advise the TF Board on Māori interests and knowledge as it relates to the operation of the trust framework.
      
- **Trust Framework Authority (TFA)**: That is responsible for enforcing the Digital Identity Services Trust Framework (DISTF). The Authority may also seek advice from Privacy Commissioner on:
    - Whether the applicant for accreditation is or has been the subject of a formal investigation or proceeding by or taken by the Privacy Commissioner; and
    - the status or outcome of any such investigation or proceeding.
      
The TFA is considered the regulator in this Reference Architecture (RA).

The DISTF outlines in section 17 that nothing in the Act overrides the Privacy Act 2020 and therefore the Act and its participants are subject to the Privacy Act and three of the key enforcement bodies identified as roles in that Act.
  - Office of the Privacy Commissioner (OPC)
  - Director of Human Rights Proceedings
  - Human Rights Tribunal

The DISTF outlines three participants:
-  Users
-  Trust Framework (TF) providers; and
-  Relying Parties

### 5.2 Users

Under the DISTF a **user** means an individual who:
-  shares personal or organisational information, in a transaction with a relying party, through one or more accredited digital identity services; and
-  does so for themselves or on behalf of another individual or an organisation.

Sections of the RA that are focused in supporting the user are:
-  Section 3.0 Accessibility and Inclusion
-  Section 3.2 Te ao Māori Approaches to Identity
-  Section 4.0 Privacy
-  Section 4.2.1 Selective Disclosure
-  Section 4.7 Breach Reporting
-  Section 6.0 Level of Assurance

### 5.3 Trust Framework Providers

The **TF Providers** may provide both accredited and not accredited services. The [Digital Identity Services Trust Framework Regulations 2024](), identifies the following service types:
-  Information services
-  Binding services
-  Authentication services
- Credential services
- Facilitation services

![Services defined under the Trust Framework](media/distf-services.png)

These service types are referenced through this reference architecture and are detailed below.

### 5.4 Relying Party

Under the DISTF Regulations, a relying party is an individual or an organisation that relies on personal or organisational information shared, in a transaction with a user, through one or more accredited digital identity services.

Additionally under the RA, where relying parties seek Personally Identifiable Information (PII) and storing this for any purpose, they will require the Verifying Service being utilised to provide the user a privacy statement that:
-  Authenticates they (the relying party) are who they say they are.
-  States why they are collecting the information
-  States what PII they are stored
-  States what is Shared with a third party
-  The retention period required for the data
-  If the data is shared with any other third parties (and whom)


## 5.5 Digital Identity Service Types

### 5.5.1 Information Services
Under the DISTF Rules an information service means a digital identity service that provides:
-  personal or oganisational information; and
-  a level of assurance as to the accuracy of that information

Examples of Information service providers can be (but not exclusively):
-	Government
-	Private sector organisations
-	Iwi
-	Individuals

An information service provider generally holds the source of information (e.g. System of Record) or master data of the digital credential holder/user. This may also include biometric and biographic sources.  They may already have existing information management, security and other regulatory requirements in the protection and management of the personal information.  An information service can be used to provide attributes to multiple credentials, with a level of information assurance to indicate the level of confidence the relying party can consume the information as.

### 5.5.2 Binding Services
A binding service, under the DISTF Regulations, is a digital identity service that links a person or organisation to their verified entity information. Binding is not a one‑off process, it can occur multiple times throughout the life of a digital credential.

Binding confirms that the data and attributes associated with an entity are accurate and trusted because they are cryptographically signed by the Issuing Authority and linked to the device presenting the credential via the device key.

Binding may be applied at enrolment and re‑applied as needed, for example when:
-	Entity information becomes “orphaned” (e.g., loss of all authenticators, or an enrolment where no initial binding occurred such as a birth record or unassigned stored‑value card)
-	New authenticators are added
-	The level of assurance needs to be increased
-	Entity information is suspected to be compromised

This ensures the entity’s data remains trustworthy and properly anchored throughout the credential’s lifecycle.

Binding has specific controls to ensure assurance of data integrity, and these are further specified in the Binding Assurance Standards .  Note that binding services need to apply cryptographic requirements to ensure the biometric data and bound data elements can provide non-repudiation.

All these binding elements are focused on ensuring the entity (e.g. individual, business, assets) and their attributions maintain integrity can be trusted.  

#### 5.5.2.1 Biometric Matching and Binding

Biometric matching refers to the process of matching stored physical characteristics with those presented either online or in person at a point in time.  This could be for instance comparing your image just taken to a stored image by either the digital credential and/or biometrics stored by the Information Service provider.

Biometric binding is when there is a positive match to the biometric matching and that confirmation is cryptographically linked to an identity and connected attributes of the same individuals.  

For the purposes of this RA, biometric binding will refer to binding of an individual’s image and where applicable the tests of the liveness of the image taken as part of the proofing process.  As the other biometrics become standardised for binding the RA will include these.

Note also that Biometric matching can also be used as a factor of authentication (Refer to 5.8 Authentication Service).

New Zealand has an existing Biometric Processing Privacy Code (2025) and this covers, collection, use, disclosure, requests by owner, storage, security, retention and disposal.

#### 5.5.2.2 Credential Matching and Binding

>[!WARNING]
>[Editor's note] This section needs work to better align it with the NZIS section on using authenticators for binding.

Credential matching is based on a user matching the data they have from an existing credential and providing that data to match with either a credential service provider or Issuer’s Information Service, system of record.  The matching provides evidence that the user has the data available to conduct the match.

Credential binding occurs when there is a positive match of the data provided by the user to the Information Service, system of record (either directly or by the credential service provider) and that confirmation is cryptographically linked between the credential being issued or updated with the data from the issuer’s system of record.

#### 5.5.2.3 Smart Chip Binding

>[!WARNING]
>[Editor's note] We need to fill this out in order to reflect the current status.

### 5.5.3 Credential Services
A credential service under the DISTF Regulations is a digital identity service that creates a standards-based, reusable credential. 

The creation of a reusable credential for the purposes of this RA refers to services that creates verifiable credential and derived credentials that complies with the ISO/IEC 18013-5 Personal Identification - ISO Compliant Driving Licence and ISO/IEC 23220-2 Data objects and encoding rules for generic eID Systems.

A credential service may utilise shared technology, such as a credential broker or issuance platform, to allow for the issuing, updating, and revokation of their own digital credentials. The All of Government Credential Issuance platform is a clear example of where multiple credential services (with seperate cryptographic keys) utilise shared infrastructure.

In this RA, a credential refers to a verifiable credential which is cryptographically secured data that represents an entity, individual or object and other relevant data for the purpose of verification and transacting. This can represent trusted digital instances of a physical documents like a driver licence or Photo ID and assets (Vehicle Registration) or financial products (Grants and rebates). They can be cryptographically verified and bound to the Issuer/Information Service and Credential service provider.  Examples of other verifiable credentials are:
-  Micro-credentials: Where a Primary Issuer of a credential provides a subset of credentials such as course certificates or awards.  Seen primarily in the education sector where short courses or part qualifications can be earned without completing or receiving full course/certificate or degree.
-  Ephemeral credentials: These are short lived credentials, either derived or issued to provide temporary access or to complete a minimum set of transactions.  Examples could be tickets to an event, or temporary access to a rental vehicle.
-  Derived credentials: Where a credential is derived from another credential and retains some of the security features of the original credential. That primary credential can be used as a trust anchor to either create a copy (though can lead to a lower assurance subject to how the binding to the original source is undertaken) or spawn a Micro of Ephemeral credential without necessarily undertaking the necessary Pre-Auth enrolment a Primary issuer would undertake. For an example, see [9.X.X ICAO 9303 Derived Credentials]()

>[!WARNING]
>[Editor's note] Definition of derived credential to come.

### 5.5.3.1 Device-Credential Binding
Under the ISO/IEC Standards, Credentials established in a Digital Wallet are device bound.  This typically means the digital credential stored in one wallet cannot be transferred by the user or any other service provider into another device and/or wallet.  Each instance of that digital credential is unique per device.

An issuer may choose to allow a credential for a user to exist in multiple devices, for instance, a smartphone, smartwatch, table or other wearable smart device. However, each instance of that credential is cryptographically uniquely identified per device.  

Device-credential binding occurs at enrolment following entity binding and the mDoc (mobile Document) and the Mobile Security Object (MSO) are being prepared (known as document preparation). The credential is bound when it is cryptographically linked to the device that the credential was enrolled into, in conjunction with the Issuing Authority cryptographic signature.

Note, device binding is only available on mobile devices that have secure elements/enclaves. This means that there may be issues on older phones and operating systems and devices that don't contain these secure elements, like tablets.

![Device-Credential Binding](media/device-binding.png)

### 5.5.4 Authentication Service

An **authentication service** is a digital identity service that enables a person to use an authenticator to access a service.

Importantly, an authentication service requires both:
-  use of one or more authenticators; and
-  management of the authenticator lifecycle.

For example, an authentication service might utilise a PIN code as the authenticator to restrict access to a digital wallet. But the service, in managing the authenticator lifecycle, also needs to consider and manage factors like:
-  how often the PIN code needs to be changed.
-  the minimum length and complexity of the PIN code.
-  how to manage repeated incorrect attempts at the PIN code; and
-  ensuring the user is aware of their responsibilities regarding managing the authenticator.

For implementation advice for an authentication service, refer to the [New Zealand Identification Standards: Implementing the Authentication Assurance Standard]().

#### 5.5.4.1 Recommended Sets of Authenticators

There are practical reasons why you may use a set of Authenticators, some of which may be the limitations and access to technologies an organisation may have.   Other reasons are that some authenticators cause inclusion or accessibility issues.   So, the use of Authenticators needs to consider:
-	Risk and security postures (as the stronger these are, usability and accessibility will form part of the compromise)
-	Use case and the customer experience required
-	Existing technologies employed (as the best authenticators may be compromised if back-end systems are poor)
-	Overall level assurance required to deliver a service.

However, there are global trends that indicate certain types of authenticators are a vector and focus for fraudulent activities:
-	Password and pin-based systems
-	Use of SMS and Email as out of band additional authenticators (Primary target for Phishing)
-	Facial Biometrics (where your face is your password but is also on your social media accounts).  Noting the biometrics is not generally considered an authenticator because it is also probabilistic.

Each of the above systems have mitigations and facial biometrics with liveness and other capabilities can mitigate some of that risk.  However, with the combination of AI and deepfakes occurring, Authenticators will need to continually evolve.

As such the RA recommends a combination of several methods as authenticators:
-	Cryptographic Multifactor One Time Password (OTP) (Section 5.8.5 Multi-Factor OTP Authenticators)
    -	Hardware protected Authenticator with activation factor
    -	Use of Passkeys as a primary authenticator, access to which is protected by an on-device authenticator or biometric verification bound to the key.
-	Use of a verifiable credential as part of that Authentication (but this is subject of course to the adoption of this in the first place).
-	Any out of band authenticators use in App messaging and authentication, on the proviso the App itself has a minimum level of authentication and biometric verification to access it and binding to the user.
-	Over the counter recovery processes to provide out of band fraud recovery

#### 5.5.4.2 Passwords

_Something you know_

A secret value chosen or memorised by the user. There are minimum password standards to provide strength, but they are not phishing-resistant. This could be in the way of Personal Identification Number (PIN), passphrase or combination of. Passwords employ matching previous phrases/pins agreed and stored by your identity provider per transaction.

#### 5.5.4.3 Look-up Secrets

_Something you have_

A pre-generated set of secret values that are issued to the subscriber at enrolment or transaction with the issuer (known as Credential Service Provider [CSP] in NIST standards), to be used by the user to authenticate.

The two roles involved are:
•	Look-up secret Authenticators: There are two parties involved in this. The issuer of the look-up secret that provides the range of one-off secrets and the presenter of that secret (user).
•	Look-up Secret Verifiers: These are those who prompt the user for a one-off secret and ensure that the one use secret is no longer reusable.

#### 5.5.4.4 Out-of-band Devices

_Something you have_

This is where the user has a physical device that communicates with the verifier over a second/independent channel than the one used to authenticate (primary channel).  Out of band (OoB) authentication uses short-term secret generated by the verifier.  

The use of the physical device is to generate a short term, one-time-use secret in the secondary channel.  When that secret is presented and successfully verified in the primary channel, it provides a bind that or the primary and secondary channels.

Four primary examples of Out-of-band devices are:
-	Phone call verification: Where the secret/pin is entered on the phone (sometimes with a # to indicate completion)
-	SMS One Time Password (OTP):  Where a one-time code is sent to the user via text.  Then that one-time password is entered into a verifier
-	Push Notification to Authenticator App:  An example is where your actual Authenticator or App seeks to approve or confirm that you have instigated or completed a transaction, and you seek to approve or deny.  Please note this is not the actual cryptographic secret provided by the Authenticator App itself.
-	Hardware Token (on a separate channel e.g not on the mobile that is being used to authenticate): This where there is a dedicate token that generate a random code or cryptographic response.

| Example                   | Primary Channel   | Out of Band Secondary |
|---------------------------|-------------------|------------------------|
| SMS OTP                   | Internet          | Cellular network       |
| Voice call verification   | Internet          | Telephone network      |
| Authenticator app push    | Browser session   | Secure app connection  |
| Hardware token            | Computer          | Physical device        |
| Mobile app challenge      | Web               | Mobile device          |

**Multifactor Out-of-Band Authenticators**

_Something you have + another presentation factor_

Is where another presentation factor (e.g. biometric matching, password) occurs before completing a transaction with an Out-of-band authenticator on the verification of that presentation factor.  None of the presentation factors are stored after the authentication is complete.

#### 5.5.4.5 Single-Factor One-Time-Password (OTP)
_Something you have_
This is where either hardware or software generates a one-time randomly generated password. These authenticators have an embedded secret that is used to generate the OTP.  There is no other second factor that is used to activate the OTP (unlike that Multifactor OoB). Whilst the presentation is like the look-up secret authenticators, they are different in that the secret is developed independently of either the authenticator, or issuer/verifier through a cryptographic method.  OTP authentication is also not considered phishing resistant.

#### 5.5.4.6 Multi-Factor OTP Authenticators
_Something you have + Presentation of another activation factor_
Recommended:  Multi-Factor Cryptographic Authentication using Passkeys
This is in the inclusion of an OTP but there is a presentation as an activation factor (e.g. Biometric, Password) prior to obtaining the OTP from the authenticator. Two other requirements are:
-  A symmetric key that persists for the authenticator’s lifetime; and
-  A nonce that is changed each time the authenticator is used or seeded by a real-time clock.
The following are examples of other activation factors:

| Category                   | Factors               | Key Storage                     | Typical Use                 | Phishing Resistance                                            |
|----------------------------|------------------------|----------------------------------|-----------------------------|----------------------------------------------------------------|
| Single-Factor Cryptographic | “Something you have”   | Local or hardware-protected      | Device key, hardware token  | Yes, if it meets NIST SP800-63B-4 (Sec 3.2.5)                 |
| Multi-Factor Cryptographic  | “Have” + “Know/Are”    | Hardware-protected with activation factor | Passkey, smart card, wallet | Yes (if signed and bound)                                     |
| Subscriber Wallets          | “Have” + “Know/Are”    | Local wallet on device           | Digital ID wallets          | Yes (if audience-restricted)                                  |
| Syncable Authenticators     | “Have” (optional extra) | Syncable via cloud               | Passkeys synced across devices | Conditional, per NIST SP800-63B-4 Appendix B                 |

#### 5.5.4.7 Biometric Authenticators

_Something you are_

Biometrics is the automated recognition of individuals based on biological and behavioural characteristics. While the most common are facial and fingerprints, other cases of biometric matching include:
-	Voice patterns
-	Gait
-	Iris scanning
-	Retina scanning
-	Typing speed
-	Keystroke patterns, screen pressure

While biometrics are considered an authentication factor under the New Zealand Identification Standards, in some jurisdictions it is not considered a seperate factor because the “secret” (such as a person’s face) is publicly observable, and advances in AI‑driven cloning significantly increase the risk of misuse. While Presentation Attack Detection (PAD) technologies can reduce these risks, they remain probabilistic and therefore only add assurance when combined with other authentication factors. Biometrics themselves are inherently probabilistic rather than deterministic.

Biometrics may also be applied actively, where the user is explicitly aware that biometric collection and matching are occurring, or passively, where the user is not aware. The Trust Framework does not support the passive use or collection of biometric information.

Under the Trust Framework's proposed Levels of Assurance (which are provisional and subject to regulatory change) a “plus” can be added to an existing Level of Assurance to indicate enhanced biometric assurance. For example, if a credential is issued at a "Standard" level of assurance, undertaking biometric matching at the point of binding can increase it to "Standard+".

#### 5.5.4.8 Pre-Authorisation (Pre-Auth)
Often in the digital credential space, a user is redeeming a credential that has already been authorised. The pre-authorisation flow, as defined in OpenID 4 Verifiable Credential Issuance, allows a user to redeem a generated credential following authorisation (for instance, because this has been done in person).

Typically, this is:
-	Initiated by the issuer who generates a pre-authorisation code after identity proofing
-	This is shared via an online link or QR Code that the user scans or clicks
-	This method then is accompanied by some level of authentication, “out-of-band” using one of the above authentication methods
-	When confirmed a new verifiable credential is enrolled and instantiated in the new wallet or facilitation service

If there is an airgap between the pre-authorisation sessions, there are potential risks.

>[!WARNING]
>[Editor's note] Awaiting some clarity around treatment of Pre-Auth for Levels of Assurance.

### 5.5.5	Facilitation Service
Under the Digital Identity Service Regulation, a facilitation services means a digital identity service that enables a person to present a credential to a relying party either online or in person. This typically takes the form of a digital wallet. With Agentic AI in the future, “vaults" that contain digital credentials may also be possible.

Under the Trust Framework, a federated identity "hub" or "IdP" that provides an account-based authentication service as its primary means to represent a digital identity is not a facilitation service, but may be an authentication service.

A digital wallet can be presented both online and in-person and a facilitation service can support one or both methods. (Preferably for inclusion).


## 5.6 The role of the Government App/Digital Wallet

The Government Chief Digital Officer has developed an app that will improve the way New Zealanders interact with government. The government app will provide a:  
-    secure way for agencies to communicate with New Zealanders
-    safe digital wallet to hold accredited digital credentials
-    a direct way to access government services and make payments. 
 
The app will prioritise usability, security and privacy for all users and will always be optional to use.
  
The app will hold digital credentials accredited under the Digital Identity Services Trust Framework. This will include credentials from government agencies and accredited private sector providers – for example, a digital driver’s licence.

The app will seek accreditation under the DISTF as an authentication service and as a facilitation service.  

As such, it is expected that the Government App, and its digital wallet functionality, will play an important role in the development of New Zealand's digital identity ecosystem.


>[!IMPORTANT]
>Note: The introduction of an accredited digital wallet by the government does not preclude the ability for other digital wallet providers to enter the market, seek accreditation, and hold accredited credentials including those issued by government.


## 5.7 The central role of Cryptography
Cryptography is the underlying trust fabric of the decentralized ecosystem. The building blocks of cryptographic trust are based on:

-	**Digital Certificates** that are provided by the issuer of the credential and are signed by the Issuing Authority.

-	**Cryptographic keys** where the:
        -	Public key is distributed by the Digital Certificate.
        - Relying parties/verifiers and wallets can also use cryptographic keys (e.g TLS) to secure channel at the point of data exchange between the holder and verifier.
        - The cryptographic pairing of keys are used as a means of authentication between devices, actors and products in a Public Key Infrastructure (PKI) ecosystem.

-	A **Digital Signature** is used to sign the certificate and bind the issuer to credentials and the attributes within the certificate. 

The combination of these products enable encryption, secure binding of data to issuers and authentication.  

Each service provider in the PKI Ecosystem has a role to play in the digital identity and verifiable credential ecosystem. 

-    The **Information Service**:  Is the primary assurance provider, that uses the cryptographic platform capability to provide to devices, wallets, credential holder or relying party, keys and signatures. These keys form the root trust of the credential and the identity inherently proved within it.
  
-    The **Credential Service**: This provides the document preparation for the verifiable credential and ensures that the data attributes and the credential itself are signed by the appropriate providers.  They are therefore also inherently also critical in managing the binding service for a credential.

-    The **Facilitation Service**: Is the provider of the device cryptographic keys that is bound to the document and from an interaction between the credential service provider and relying party are those that provide the capability for customers to selectively disclose signed data as well as ensure the receipt of those in the customer transaction log is protected and digitally signed.

-	**Relying Party/Verification Service**:  Will have devices whether physically or online that will have digital signatures to prove their devices can be trusted to relying parties.  Those signatures when Personal Information is collected are used to sign the data collected, to ensure accountability and protection of privacy.

-	**Trust Service** provider:  Hosts the public keys of all those participating in the PKI system allowing relying parties and users to match the public keys of all players in the ecosystem.

-	The **Authentication Service**: Depending on the architecture (centralised and decentralised) will have encrypted tokens sent between different providers.  Also, they will encrypt and sign the transport layer using Mutual Transport Layer Security (mTLS).

-	**Binding Service**:  In a verifiable credential architecture, the binding service is undertaken primarily through the credential service.   However, in a hybrid or Federated ecosystem, an Identity Service Provider (IDP) may through a Pre-Auth flow or enrolment also sign the JWT and attributes instantiated in the IDP or Single Sign On (SSO) Platform.

This is why PKI provides the end-to-end trust fabric of a digital identity and verifiable credential ecosystem. How those keys are instantiated to disposed (lifecycle managed) will determine the levels of assurance depending on the practice (People, Process, Technology) applied in their roles.  Refer to Section 7.0 Trust Model for more details.
Those providing these cryptographic services are required to undertake a Certificate Practice Statement to be defined by later versions of the RA.

[<< 4. Privacy](3-PRIVACY.md) | **5. Ecosystem Roles** | [6. Levels of Assurance >>](6-LOA.md)
