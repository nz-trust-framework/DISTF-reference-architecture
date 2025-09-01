# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

## Reference Architecture - Plan

### 1 Introduction
-  Provides an introduction and high level overview of the purpose of the reference architecture
-  This includes the scope, and what is out of scope, of the reference architecture
-  It also provides "house keeping", for instance standard disclaimers, link to definitions, change log and anything else required to 'establish' the reference architecture.

### 2 New Zealand's Digital Identity Ecosystem
-  Establishes the basic form of New Zealand's modern digital identity ecosystem and introduces the basic model and key entities in that ecosystem
-  Begins to translate between the Trust Framework and commonly understood concepts (for instance, issuer vs. TF services)
-  Acknowledges the important role of Te ao Māori approaches to identity, noting the differentiation between identity and identification
-  Establishes use cases for the purpose of practically detailing many of the concepts included in the reference architecture (*to discuss*)
-  Details a focus on standards to ensure interoperability

### 3 Ecosystem Roles ("The Roles")
-  A deeper dive into the individual digital identity services covered by the Trust Framework, and the additional services not regulated by the Trust Framework (for instance verifier, trust registers)
-  Draws strong links to the requirements and definitions under the Trust Framework, while offering practical advice and examples of use
-  Goes into greater detail on expected implementation (i.e. how an "issuer" is broken into info, bind, credential services) and how these can be provided by one or many accredited services
-  in credential service establishes supported formats while providing direction (for instance, refering to government's mDocs first approach)
-  Details technology out of scope of Trust Framework regulation, but that is of importance to the ecosystem, importantly "verification services" and how a verifier is differentiated from a relying party
-  Discusses the role of federated/IdP services (principally as "info/bind/auth" services useful for identity proofing)

### 4 Ecosystem Flows ("The Flows")
-  Following on from defining the roles, this section begins explaining the data flows in practice - i.e. identity proofing, credential issuance, credential presentation.
-  Needs to cover both the practical implementation and considerations, but also (through annexes) begin to establish some of the technical specifics (OID4VCI, OID4VP etc.)
-  For presentation, uses the EU model of four types of presentation: proximity attended, proximity unattended, remote same-device, remote cross-device
-  Also cover revocation/suspension

### 5 Data and attributes
-  Provide some guidance in the NZ context that is enabled but not directed through the international standards
-  Needs to focus on interoperability - for instance use of org.iso.23220.photoID.1 as a baseline for relevant credentials - and that sectors are establishing their own, i.e. one banking sector proof of account rather than each individual
-  Covering use of latin1/unicode with particular relevance for international interoperability (tourisms/visitors with non-latin names) and for Māori names using macrons (supported by unicode, not latin1)
-  Alignment with mandated data attributes established by Stats NZ
-  Cover relevant namespaces and which NZ-specific namespaces should be established for joint use

### 6 Trust Model
-  Having established the roles and flows, start to detail how trust is established both from a legal perspective and from a technical perspective
-  Detail the role of accreditation in providing trust
-  Discuss the role of the trust register (X509 certs, credential/attribute metadata incl. LoAs etc)
-  Discuss management prior to trust register (manual management of certs)
-  Levels of Assurance (current under the New Zealand Identification Standards and future under DISTF Regulations - *Prashil's the expert*)
-  Broach current discussions on "trusted" verifiers given no regulation under DISTF

### 7 International
-  Discussion around international interoperability
-  Mutual Recognition and Equivalency between jurisdictions
-  Digital Travel Credentials

### 8 Annexes
- Definitions
