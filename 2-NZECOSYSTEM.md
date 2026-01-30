# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 2 New Zealand's Digital Identity Ecosystem
### 2.1 Introduction 

Throughout history, people have relied on physical methods to share trusted information. Authenticity was verified through face‑to‑face interaction, recognised physical security features, and familiarity built through personal or institutional relationships. 

The emergence of the internet transformed communication, commerce, and access to services, yet it was never designed with an identity layer. As a result, it lacked a secure and consistent way for individuals and organisations to share and verify personal information online. Around the world, significant work has been undertaken to create digital trust mechanisms that operate seamlessly across digital and physical environments. New Zealand is now adopting these technologies to deliver safer, more convenient, and more trustworthy interactions for all New Zealanders. 

As services increasingly move online, confirming that a person is who they claim to be remains a challenge, often requiring physical documents or in‑person verification. Meanwhile, fragmented identity practices, high‑profile data breaches, and inconsistent system designs have elevated the risks of fraud, identity misuse, and privacy harm. 

People are also adopting new technologies such as digital wallets and expect secure, simple ways to prove their identity in both online and real‑world settings. Over time, identity credentials may be hosted across an expanding set of services and devices. It is important that clear guardrails, standards, and guidance are in place before these capabilities become widespread. Digital identity in this decentralised model is being rebuilt to securely anchor a person’s real identity, providing the trust layer the internet was never originally designed to support. 

A secure and trusted digital identity ecosystem is therefore essential. It enables New Zealanders to access services, participate in the economy, and engage with government and business easily, safely, and with confidence. To support this, Parliament enacted the Digital Identity Services Trust Framework Act 2023, which establishes “a legal framework for the provision of secure and trusted digital identity services for individuals and organisations”. 

The Trust Framework is built on core principles including security, privacy, interoperability, user choice, and sustainability. These principles guide how digital identity services should operate and ensure that trust, fairness, and accountability are embedded in the ecosystem from the outset. 

New Zealand also does not hold a social licence for a national identity number or a centralised identity system. The Trust Framework reflects this by promoting a decentralised, choice‑based model that ensures individuals retain control over how their identity information is used and shared. 

Although New Zealand is still in the early stages of this journey, the opportunity to build a modern, resilient, and future‑proofed identity ecosystem is significant. The work underway provides the chance to improve on past approaches and lay a foundation that supports trust, inclusion, interoperability, and innovation for years to come. 

 
>“It is hard to believe we are still using multi-password sign-on and facsimiles of identity proofs in an era where nearly everything we do is online. For those frustrated by the pace of change, it is important to remember we’re building a system for 30 years, of which the past five years has been very much design and build. The next five years will be about driving adoption.” 
> 
>Andy Higgs, Executive Director, Digital Identity New Zealand 

 
### 2.2 Services and Roles 

A screen shot of a computer

AI-generated content may be incorrect. 

The ecosystem envisioned under the Digital Identity Services Trust Framework replicates the widely known "trust triangle" comprising of issuer, holder, verifier often described in the design of self-sovereign identity. The Trust Framework breaks these roles down slightly further, for instance splitting the verifier (the technology that receives a presentation and cryptographically verifies the data) from the relying party (the natural or legal person receiving the information for a given purpose). 
 
The above diagram serves as the basic model. It is not definitive.  For more information regarding the regulated service providers, please refer to 5 Ecosystem Roles that includes the roles and definitions of (As per the DISTF Regulations): 

1.  Information Services 
2.  Credential Services 
3.  Binding Services 
4.  Authentication Services 
5.  Facilitation Services 

The RA also provides two additional services that are part of the ecosystem but not accreditable under the Trust Framework.

6.  Verification Services 
7.  Trust Services 

#### 2.2.1 Roles and Responsibilities 

**Trust Framework Authority (TFA):** Is the regulator responsible for accrediting providers and services under the Digital Identity Services Trust Framework (DISTF).

>[!TIP]
>Refer to [5. Ecosystem Roles]() for a more detailed list of services and functions within New Zealand's digital identity ecosystem.

A quick summary of some of these roles and functions are: 

**Issuer:** The term issuer refers to the ecosystem participant responsible for creating and issuing a digital credential. An issuer verifies the underlying information, packages it into a secure, digitally signed credential, and provides it to the user. 

**User:** A person that holds credentials. Specifically, the Act defines a user as "an individual who shares personal or organisational information, in a transaction with a relying party and does so for themselves or on behalf of another individual or an organisation." 

**Relying Party:** the participant who relies on the information asserted by an issuer and presented by a user.  

**Digital Wallet:** A piece of software, in the control of the user, that permits the redemption, holding, and presentation of digital credentials.

A digital wallet generally comprises:
-  Secure, encrypted storage for credential data.
-  A requirement for the user to authenticate on the device before accessing that data.
-  Selective disclosure, allowing the user to determine which data is shared in any interaction.
-  Technical controls that prevent the wallet provider from accessing, reading, or extracting credential data without the user’s knowledge or consent (including prevention of screen scraping or unauthorised data leakage).

**Presentation:** the process of a user providing information to a relying party through the presentation of information encoded in a way that allows for a process of cryptographic verification. Presentation is broadly categorised into in-person/proximity or online/remote presentation. 

**Verifier:** the technological means by which a relying party receives and verifies information from the presentation of a credential and/or identity. A verifier might be an app, standalone hardware, embedded into existing hardware (an payment terminal or Point of Sale kiosk), or a via an online service (e.g Web, mobile App) 

**Trust Register:** a publicly available register of accredited services under the DISTF that also contains the necessary cryptographic keys for participants to ensure the validity of an accredited or trusted service (whether it be a credential, issuer, wallet, or verifier service). A Trust Register may also be replaced by a relying party manually managing public keys supplied by trusted issuers on their own internal trust list. 

### 2.3 Other references and considerations 

Throughout this document, references are made also to the following New Zealand legislation, regulation, standards and guidelines. These include: 

The [Digital Identity Services Trust Framework Act 2023]()

The Digital Identity Services Trust Framework (DISTF) or trust framework is the legal framework established in New Zealand to regulate the provision of digital identity services for transactions between individuals and organisations. 

Section 9: Tiriti o Waitangi/Treaty of Waitangi, that recognises and respect the Crown’s responsibility to give effect to the principles of te Tiriti o Waitangi/the Treaty of Waitangi. 

New Zealand Identification Standards 

A set of standards that underpin the DISTF that provide clarity on the services, functions and the rules to assure that organisations have the right information about the right entities to minimise rises in identity fraud.  These standards are aimed at private and public sector organisations who perform the role of relying party and/or credential provider.  Under this broader standard are: 

Levels of Assurance:  Which outlines the robust identification processes to assure the right Entity information, Authenticators and the connections between these and an Entity, are in place.   

Information Assurance Standard 

Binding Assurance Standard 

Authentication Assurance Standard 

Federation Assurance Standard 

New Zealand Privacy Act 2020 

This is the legislated privacy rights and principles that govern the collection, storage, use, sharing and overall management of personal information by organisations and government.  It contains 13 privacy principles and is focused in ensuring that information and data are effectively protected by law. 

Biometric Processing Privacy Code 2025 

This provision under the Privacy Act, sets out the privacy rules for organisations and businesses who collect and use people’s biometric information in biometric processing.  This includes the use of facial recognition technology. 

New Zealand Meta Data Standards 

This describes mandated data standards, their importance and proposed mandates.  This also includes key terms. 

New Zealand Information Security Manual (NZISM) 

This is the New Zealand Government’s manual on information assurance and information systems security designed for information security executives and practitioners and those vendors, contractors and consultants providing security services to government agencies. 

 
