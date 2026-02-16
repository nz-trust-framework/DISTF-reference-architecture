# Annex 2: Glossary

About this glossary: Definitions are concise and grounded in the content of the Reference Architecture draft. They are intended for consistent use across the document and related artefacts.

## A
**Accessibility**: Design requirement that solutions be usable by all people, aligning to WCAG 2.2 Level AA, work with assistive technologies, and provide non-digital pathways, multilingual support, and plain language.

**Age Attestation (age_over_NN)**: Boolean attributes (e.g., age_over_18, age_over_20) enabling privacy-preserving proof of being at least a specified age without disclosing date of birth.

**Anti-Spoofing** / Presentation Attack Detection (PAD): Controls used with biometrics (e.g., liveness detection) to reduce deepfake/spoof risks; biometrics remain probabilistic and should complement other factors.

**Authentication**: Process of proving an entity is who/what it claims using authenticators; ecosystem uses multi-factor, phishing-resistant methods (e.g., passkeys).

**Authentication Factors (Something You Know/Have/Are)**: Categories of authenticators: knowledge (password/PIN), possession (device/token/OTP), inherence (biometrics).

**Authentication Service**: A digital identity service that enables a person to use one or more authenticators and manages the authenticator lifecycle.

**Authorisation**: The process of granting access or permissions after a user or system has been successfully authenticated and relevant policies have been applied. It is used between services as part of the overall trust fabric. Under the Digital Identity Services Trust Framework, ‘authorisation’ specifically refers to the individual’s consent for a service to be carried out.

## B
**Binding**: Linking a person/organisation (entity) to verified information and authenticators. This can be biometric, credential, smart-chip, or device-credential binding.

**Binding Assurance**: Confidence in the strength and controls applied when binding entities to attributes and authenticators.

**Binding Service**: A digital identity service that links a person/organisation to their verified entity information; may occur multiple times across a credential’s lifecycle.

**Biographic Data**: Personal attributes (e.g., name, birth date, address) used for identity proofing or credential attributes.

**Biometric Binding**: Cryptographically binding a confirmed biometric match to an identity/credential so the match event contributes to trust in the bound attributes.

**Biometric Matching**: Comparing a live capture (e.g., selfie) to a trusted source image from an issuer to establish a probabilistic match.

**Broker (Credential Broker)**: A technology solution or platform that issues/updates/revokes credentials on behalf of one or more primary issuers.

## C
**Certificate Authority (CA):** Service that issues and signs digital certificates forming the PKI trust chain (e.g., IACA, Reader CA).

**Client‑Side Transaction Log:** Wallet‑only log of interactions with verifiers; reviewable by the user and not shared unless the user chooses.

**Credential:** Cryptographically secured data representing an entity or attribute set that can be selectively disclosed and verified.

**Credential Binding:** Binding an issued credential and its attributes to the verified entity and, in a credential, to the device key for non‑repudiation.

**Credential Broker:** See Broker-issues or manages multiple credentials on behalf of primary issuers.

**Credential Management:** Lifecycle processes for enrolment, issuance, update, revocation, audit, and secure handling of credentials.

**Credential Service:** Service that creates and lifecycle‑manages reusable credentials (including mDoc/MSO signing) and interacts with information and facilitation services.

**Cryptographic Key:** Key pairs (public/private) used for signatures, encryption, device keys, and session keys throughout the ecosystem.

**Cryptographic Pairing:** Use of key pairs and certificates to mutually authenticate and encrypt between issuer, wallet, verifiers, and services within PKI.

**Cryptographically Signed Attributes:** Issuer‑signed attributes and attestations within the MSO/credential enabling selective disclosure with non‑repudiation.

**Cybersecurity:** Security controls across services (zero‑trust, mTLS, secure elements, revocation, monitoring) to counter fraud and attacks.

## D

**Data Matching:** Matching user‑provided data from an existing credential to issuer's system of record to support identity proofing.

**Data Minimisation:** Sharing only the minimum necessary attributes (e.g., age attestations instead of date of birth).

**Data Model:** The structured representation of attributes in document types and namespaces (ISO/IEC 23220 family).

**Data Repository:** Store for verifier‑retained metadata/PII, subject to privacy obligations and signed data treatment.

**Delegated Authority:** Authorising another party to act on behalf of an entity (person/business) with traceable, privacy‑aware controls.

**Derived Credential:** A verifiable credential created from another trusted credential, potentially at different assurance depending on binding.

**Device Binding:** Binding a credential instance to a device's secure element/enclave with a unique device key per device instance.

**Device Key:** Key pair generated/stored in the device secure element; public key is bound into the MSO during document preparation.

**Digital Credential:** See Credential --- cryptographically verifiable and privacy‑preserving digital representation of identity/attributes.

**Digital Identity:** Ecosystem of services and credentials enabling people or organisations to prove their identity and share verified attributes online and in person.

**Digital Wallet:** User‑controlled software that stores credentials/MSOs, enforces selective disclosure, blocks screen scraping, and uses security functions.

**Document Signer Certificate (DSC):** Certificate whose private key signs the MSO (issuer‑signed digests of attributes) for credential authenticity.

**Document Type (doctype):** Reverse‑domain formatted identifier for a credential type; versioned for evolution, used with one or more namespaces.

## E

**Electronic Signatures (VC‑based):** Use of credential cryptography to sign legal documents or transactions as a next step beyond identity verification.

**Enrolment:** Process by which a user is identity‑proofed, and a credential is prepared, signed, bound, and provisioned to a wallet.

**Ephemeral Credential:** Short‑lived credential (e.g., ticket or temporary access) derived or issued for limited transactions.

**Ephemeral Keys (Device / Reader):** Short‑lived keys used between wallet and reader to establish session encryption and confidentiality.

**Evidence Sources:** Authoritative data (e.g., system of record, biometrics) used during identity proofing and document preparation.

## F

**Facilitation Service:** Enables presentation of credentials (often a wallet), provides selective disclosure, client‑side logs, and device‑key generation.

**Federated Identity:** Context where account‑based identity providers assert attributes; RA focuses on verifiable credentials with minimal server retrieval.

**Fraud Recovery (Out-of-Band Recovery):** User support paths (e.g., over‑the‑counter) to recover from fraud or lost authenticators/credentials.

## G

**Governance:** Rules, roles, and oversight (e.g., Trust Framework Board/Authority) underpinning accreditation and compliance.

## H

**Holder (User):** Individual who holds credentials and selectively discloses attributes to relying parties.

## I

**Identity Proofing (IP):** Process of verifying identity through data or biometric matching against authoritative sources to achieve a required assurance level.

**Inclusion:** Ensuring participation across digital divide via non‑digital options, accessibility, multilingual support, and plain language.

**Information Service:** Service that provides personal/organisational information and a level of assurance as to its accuracy, often the system of record.

**Interoperability:** The ability for of digital identity systems to work across different platforms, technologies, and jurisdictions so that credentials issued in one environment can be securely recognised, trusted, and validated in another.

**Issuer:** Participant that verifies source information and issues digitally signed credentials to users.

**Issuing Authority Certificate Authority (IACA):** Issuer‑managed root/signing CA used to sign Document Signer Certificates and MSO Revocation List signers; public keys published on trust lists.

## K

**Key Ceremony:** Controlled process to generate, rotate, and manage cryptographic keys/certificates with separation of duties and audit.

**Key Management:** Practices and systems (e.g., HSMs) for generating, storing, rotating, and retiring keys across services.

**Kiosk (Service Centre Access):** On‑site channel using passkeys/QR and biometrics to access issuer portals for updates/enrolment with high assurance.

## L

**Level of Assurance (LoA):** Strength levels reflecting information assurance, binding assurance, and authenticator strength for an attribute.

**Lifecycle Management (LCM):** End‑to‑end control of credential/authenticator/key lifecycles, including issuance, update, revocation, and disposal.

## M

**Machine-to-Machine Authentication (M2M):** Mutual authentication between systems/devices (e.g., mTLS, certificates) as part of the trust fabric.

**Matching (Biometric & Credential):** Use of biometric comparison and data attribute matching to support identity proofing and binding.

**mDL (Mobile Driver Licence):** Digital driver licence compliant with ISO/IEC 18013‑5 document type/namespace for international interoperability.

**mDoc (Mobile Document):** Mobile credential data structure containing attributes and namespaces; presented with the MSO for verification.

**Metadata:** Transaction and system data generated/retained around credential operations, subject to minimisation and privacy controls.

**Mobile Security Object (MSO):** Issuer‑signed object containing digests of issuer‑signed items to prove attribute integrity and origin (non‑repudiation).

**Multilingual Support:** Providing UI/help in NZ official languages (te reo Māori, NZSL) and common community languages.

**Mutual TLS (mTLS):** Mutual certificate‑based authentication to secure service‑to‑service connections.

**Māori Data Sovereignty:** Principle recognising Māori data as taonga with governance and tino rangatiratanga considerations in identity solutions.

## N

**Namespace:** Named collection of attributes for a given document type; use ISO/IEC 23220.1 or specific namespaces and NZ common namespace as needed.

**New Zealand Common Namespace (`nz.govt.digital.common.1`):** Proposed shared namespace for NZ‑specific common attributes (e.g., preferred names, gender).

**Non-Digital Pathway:** Option to enrol/verify/revoke or seek support without relying solely on digital channels (e.g., over‑the‑counter/voice).

## O

**Online Verification:** Remote verification digital credentials with reader authentication as needed.

**Operational Controls:** Controls across trust services, revocation, logging, and security to ensure resilient, compliant operations.

**Out-of-Band Authentication:** Use of a separate channel/device (e.g., phone call, SMS OTP, authenticator push, hardware token) to complete authentication.

## P

**Passkey:** Phishing‑resistant multi‑factor cryptographic authenticator protected by on‑device biometrics or PIN.

**Personal Information (PI):** Information about an identifiable individual; collection/handling governed by Privacy Act and privacy rules.

**Personally Identifiable Information (PII):** Subset of PI used to uniquely identify a person; subject to minimisation and explicit user consent when stored.

**Photo ID:** A credential profile with mandatory portrait and core attributes; typically aligns with ISO/IEC 23220‑4 Photo ID profile.

**Public Key Infrastructure (PKI):** Certificates, keys, and trust lists enabling signatures, encryption, and non‑repudiation across roles/services.

**Plain Language:** Use of clear, non‑technical language to explain rights, obligations, and processes to users.

**Portrait Image:** Credential portrait used for attended match and/or automated face recognition; size/quality balanced for performance and privacy.

**Presentation:** Process where a user provides selectively disclosed information in a digital credential to a relying party for cryptographic verification.

**Pre-Authori[s]ed (Pre-Auth) Flow:** Issuer‑initiated code/QR flow with additional factors to bind a previously authenticated user to a new wallet/device.

**Privacy Impact Assessment (PIA):** Comprehensive assessment documenting service description, data flows, storage/access/disposal, risks and mitigations, and stakeholder consultation.

**Privacy Statement:** User‑facing notice of collection purpose, recipients, storage/retention, and credential‑specific considerations (e.g., selective disclosure).

**Proofing (Identity):** See Identity Proofing - verifying identity attributes to required assurance.

## QR

**QR Presentation Protocols (Rotating QR with Bluetooth):** In‑person channel using rotating QR and Bluetooth/NFC/Wi‑Fi Aware for secure nearby presentation without server retrieval.

## R

**Reader / Verifier:** Device/service that receives a presentation, may perform reader authentication, and verifies signatures/revocation status.

**Reader Authentication Certificate:** Certificate/key used by a verifier device to sign the session transcript so a wallet can trust the reader.

**Regulated Credential:** Credential issued under specific legislation/regulation (e.g., driver licence), often with separate certification process for the confirmation of status or privileges.

**Relying Party:** Individual/organisation relying on presented information to deliver a service to the user.

**Revocation:** Process and status management to update or invalidate credentials/attributes, published via MSO revocation lists.

**Risk Profile:** Summary of key risks (CX, inclusion, privacy, security, operational, legal) and recommended mitigations for VC deployments.

## S

**Secure Element / Secure Enclave:** Hardware‑protected area on device for keys/credentials to prevent extraction and support device binding.

**Selective Disclosure:** User's ability to disclose only needed attributes/attestations (e.g., age_over_18) rather than full PI.

**Smart Chip Binding:** Over‑the‑counter issuance and key rotation for physical smart‑card credentials with biometric binding and HSM‑managed keys.

**Standards (ISO/IEC 18013, 23220, OID4VC etc...):** International specifications governing credentials, data objects/encoding, and verification protocols used for interoperability.

**System of Record (SoR):** Authoritative data source for issuer attributes and biographic information used to produce credentials or an MSO and for matching.

## T

**Transaction Log (Client-Side):** See Client‑Side Transaction Log - user‑only record of interactions.

**Trust Fabric:** End‑to‑end cryptographic bindings, keys, and certificates across all services/devices enabling non‑repudiation and secure exchanges.

**Trust Framework Authority (TFA):** Regulator accrediting and enforcing the Digital Identity Services Trust Framework.

**Trust Framework Board:** Body that recommends rules/regulations for Ministerial consideration and consults with experts and Māori Advisory Group.

**Trust List:** Signed list of public keys (e.g., VICAL, reader lists, revocation lists) enabling independent verification without phoning home.

**Trust Service:** Service that hosts public keys and revocation lists (e.g., VICAL, MSO revocation) so verifiers/users can validate credentials and devices.

**Trusted Referee:** Additional binding method where a trusted human actor helps bind identity when higher assurance is required.

**U**

**User (Holder):** See Holder - individual controlling and presenting their credentials.

**User****‑****Centric Design:** Design that gives people control over disclosure, clear privacy information, and inclusive access across channels.

**V**

**Verifiable Credential (VC):** Credential with cryptographic proofs (signatures, MSO) allowing selective disclosure and verifier validation without issuer call‑back.

**Verifiable Presentation (VP):** Package of disclosed attributes/attestations sent to a verifier, typically with reader authentication and session security.

**Verification Service:** (Proposed) Service supporting relying parties to verify/store disclosures, authenticate readers, and sign data treatment in client logs.

**Verifier:** Technology that receives and cryptographically verifies a presentation; may be app, hardware reader, or online service.

**VICAL (Verified Issuer CA List):** Trust list publishing issuer IACA public keys so verifiers can validate signatures on attributes/MSOs.

**W**

**Wallet (Digital Wallet / Facilitation Service):** See Digital Wallet/Facilitation Service---user‑controlled app enabling issuance, storage, and presentation with selective disclosure.

**Wallet Certificate Signer:** Secure element operation producing signatures using keys stored on device for wallet operations.

**Wallet SDK:** Software kit provided to integrate wallet/facilitation capabilities with credential services and secure elements.
