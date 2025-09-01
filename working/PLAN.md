# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](../media/reference-architecture.jpg)

## Reference Architecture - Plan

### 1 IntroductionProvides an introduction and high-level overview of the purpose of the reference architecture.
-  This section defines the scope of the document and clarifies what falls outside of scope.
-  It also includes essential housekeeping elements such as standard disclaimers, references to definitions, a change log, and other material needed to formally establish the reference architecture.

### 2 New Zealand's Digital Identity Ecosystem
- Establishes the foundational form of New Zealand’s modern digital identity ecosystem, introducing the core model and key entities within it.  
- Provides translation between the Trust Framework and commonly understood concepts (e.g. issuer vs. Trust Framework services).  
- Recognises the important role of Te ao Māori approaches to identity, highlighting the distinction between *identity* and *identification*.  
- Introduces use cases to practically illustrate and detail many of the concepts within the reference architecture (*for discussion*).  
- Emphasises the importance of standards to ensure vendor-agnostic interoperability across the ecosystem.  

### 3 Ecosystem Roles ("The Roles")
- Provides a deeper dive into the individual digital identity services covered by the Trust Framework, as well as additional services not regulated under it (e.g. verifiers, trust registers).  
- Draws strong links to the requirements and definitions within the Trust Framework, while offering practical advice and illustrative examples of use.  
- Explains expected implementation in greater detail (e.g. how an “issuer” function is composed of information, binding, and credential services) and how these may be delivered by one or multiple accredited services.  
- In the context of credential services, establishes supported formats while providing direction (e.g. government’s *mDocs-first* approach).  
- Identifies technology outside the scope of Trust Framework regulation but important to the ecosystem, particularly verification services, and clarifies how a verifier differs from a relying party.  
- Discusses the role of federated/IdP services, principally as information, binding, and authentication services useful for identity proofing.  

### 4 Ecosystem Flows ("The Flows")
- Building on the definition of roles, this section explains the data flows in practice — including identity proofing, credential issuance, and credential presentation.  
- Covers both practical implementation and key considerations, while also (through annexes) introducing technical specifics such as OID4VCI and OID4VP.  
- For credential presentation, adopts the EU model of four types: proximity attended, proximity unattended, remote same-device, and remote cross-device.  
- Addresses revocation and suspension processes, referencing relevant standards such as the IETF Token Status List.

### 5 Data and attributes
- Provides guidance specific to the New Zealand context that is enabled, but not strictly directed, through international standards.  
- Focuses on interoperability — for example, adopting `org.iso.23220.photoID.1` as a baseline for relevant credentials — and encourages sector-level approaches (e.g. a single banking sector proof of account, rather than multiple individual implementations).  
- Addresses encoding considerations, particularly the use of Latin-1 vs Unicode, with emphasis on international interoperability (e.g. tourism/visitors with non-Latin names) and correct representation of Māori names using macrons (supported by Unicode but not Latin-1).  
- Ensures alignment with mandated data attributes established by Stats NZ.  
- Defines relevant namespaces, including which New Zealand–specific namespaces should be established for shared use.  

### 6 Trust Model
- Having established the roles and flows, this section details how trust is created and maintained, from both legal and technical perspectives.  
- Explains the role of accreditation in providing a foundation of trust.  
- Discusses the function of the trust register, including public keys, credential and attribute metadata, and Levels of Assurance.  
- Describes trust management approaches prior to the establishment of a trust register (e.g. manual certificate management).  
- Covers Levels of Assurance as currently defined under the New Zealand Identification Standards, and anticipates their future treatment under DISTF regulations. 
- Introduces current discussions on “trusted” verifiers, given their lack of regulation under the DISTF.  

### 7 International
- Discusses international interoperability, with particular emphasis on the Single Economic Market with Australia.  
- Explores mutual recognition and equivalency between jurisdictions, including the potential for “trust” interoperability through trust registers.  
- Highlights Digital Travel Credentials as a specific example of a cross-border digital credential.

### 8 Annexes
- Definitions
