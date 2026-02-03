# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 4.0 Privacy
As digital identity infrastructure continues to evolve, the need for secure, private and operable digital identity ecosystem becomes critical. To effectively address these needs, development of the RA has prioritised active consideration of New Zealand's Privacy Act 2020 as well as guidance established by the Trust Framework Authority (TFA). By grounding the Reference Architecture around these aspects, we can build a foundation which enables secure digital service delivery, while protecting the rights and interests of New Zealanders. 

As per guidance established by the TFA, all service providers within the Digital Services Trust Framework (as defined in Section 3), will require consideration and independent assessment of privacy practices and policies. The requirement focuses on ensuring that service providers comply with the privacy rules outlined by TFA, along with core principles within the NZ Privacy Act. 

This independent evaluation of privacy for a service provider will involve undertaking a privacy impact assessment and evaluating the effectiveness of key privacy requirements and expectations. The following sections will seek to summarise the core ‘rules’ for identity service providers to consider when supporting compliance with the evaluation criteria. 

### 4.1 Privacy Impact Assessment
TFA guidelines specify that the service provider is required to complete a Privacy Impact Assessment (PIA) for the accredited service. To comply with relevant obligations as part of the Privacy Act, service providers must complete a comprehensive PIA that provides a detailed service description, information data flows across systems and third parties with respect to storage, access and disposal processes. 

The PIA should also ensure it has clearly assessed how the service provider meets its obligations against the 13 principles outlined within the Privacy Act, specifically on how it handles the privacy of information across the credential lifecycle. 

Confirmation that appropriate governance is in place within the service provider should be undertaken within the PIA, which confirms that controls are in place to effectively manage the privacy risks and issues identified. Note that industry specific Codes of Practice (e.g. when handling health or financial information), must be adequately considered as part of the PIA. 

### 4.2 Communicating the Privacy Impact to the Customer in a Verifiable Credential
Under PV.1.3 the privacy impact assessment MUST include the following:
-  detailed service description.
-  information already held and new information to be collected.
-  the purpose for which the information is collected.
-  a map of the information flows.
-  how information will be stored, accessed, and disposed of by the accredited provider.
-  an analysis of mitigations for all risks identified.
-  consultation with relevant stakeholders.  

In an ISO 18013‑5 compliant verifiable credential stored in a digital wallet, it is recommended that the digital wallet maintain a client‑side transaction log that the holder can review. This log records interactions with verifiers and, per the ISO standard, is only accessible to the user in the digital wallet and cannot be shared unless the user explicitly chooses to do so. This was created for the purpose of collecting relying party information and registering how Personal Information (PI) data is used.   

The following is a proposal for future verifying services

That those relying parties that collect PI from the customer, provide statements of:
-	Purpose for collection
-	Information that was stored
-	When the collected PI will be disposed 
-	Any third parties or secondary use of their data being agreed to

Note that the record of these statements will be digitally signed in the client transaction log to provide non-repudiation of the privacy agreement of collection.

#### 4.2.1 Selective Disclosure
A traditional physical credential has no ability to protect the data on it once it is handed over to be copied.  One of the primary benefits of digital credentials and a requirement under standards, and the DISTF, is the ability to allow the user to selectively disclose the data.

This is particularly important as a digital credential can be used not only for regulated purposes, but the proofing undertaken to prove the data and the representations about a person can be trusted, means a credential can function as a trusted, reusable source of verified identity and personal information.

Once the user has a digital credential on their wallet or as part of their facilitation service, all disclosure of data to third parties must be at the discretion of the user.  In cases where all the data is required to be provided for legislative and regulatory purposes, the user will still be provided a prompt to choose whether to disclose the data requested.

### 4.3 Designated Individual

Service providers must appoint a designated individual who is responsible for privacy oversight. This may be through the appointment of a Privacy Officer as required in the Privacy Act 2020. Appointment of this individual should be supported by formal documentation of:
-  Their position description, which clearly outlines their responsibilities overseeing the PIA process,
-  ensuring compliance with applicable privacy obligations,
-  managing privacy policies; and
-  monitoring ongoing privacy risks. 

### 4.4 Privacy Training
Confirmation will be required that the service providers’ staff, including contractors with access to personal or organisational information, must receive comprehensive privacy awareness training when joining and on an ongoing basis. Training should appropriately capture details on lawful purposes of collecting and holding PI, processes for amending and disclosing PI, as well as practices for identifying and managing privacy breaches. The service provider must ensure their privacy policies are readily accessible to staff, while ensuring robust processes are in place to handle changes to privacy policies (i.e. communication and application of changes). 

### 4.5 Privacy Incident Management
Service providers must ensure that an approved Privacy Incident Response Plan is in place which defines roles and responsibilities for managing suspected privacy incidents. The plan will be required to capture detailed escalation and notification processes, assessment procedures and reporting timeframes (in compliance with the Office of the Privacy Commissioner expectations of 72 hours of breach awareness). 

Service providers will also be required to maintain a privacy incident register which maintains a record of all incidents, including ‘near-misses’. This should be supported by associated governance arrangements, including regular review and reporting guidance. 

### 4.6 Privacy Statement
Service providers must maintain a Privacy Statement or an appropriate alternative which complies with Principle 3 of the Privacy Act. The statement should clearly inform users that their personal information is collected, why collection is necessary and identify who will receive the information. For digital identity services, statements must address credential-specific considerations (e.g. selective disclosure capabilities, presentation logging etc.). Privacy statements must be readily available to users through prominent placement on websites or within digital wallets, which is reviewed at least annually. 

### 4.7 Breach Reporting
Service providers will be required to implement robust processes to ensure compliance with reporting requirements as per Privacy Act 2020. This incorporates formal processes for assessing breaches to determine if they meet specific thresholds for being ‘notifiable’ (i.e. potentially causing serious harm to affected individuals), timelines for reporting notifiable breaches and documentation requirements for breach notifications. 

### 4.8 Secondary Use
Service providers collecting PII for digital identity services must not use that information for any other purpose, unless explicitly authorised by the user. Service providers are required to confirm that the secondary use of PI is explicitly prohibited, or that a formal process is in place to manage requests to use PI for secondary purposes including explicit authorisation from the user (prior to non-primary purpose use). Secondary use of information may include services using transaction metadata to support commercial analytics or marketing activities. 

### 4.9 Collection of PI from a Verifiable Credential and Informing the Customer
This should be communicated via the privacy impact assessment as outlined in 2.4.1 Privacy Impact Assessment.

[<< 3. Accessibility and Inclusion](3-ACCESSIBILITY.md) | **4. Privacy** | [5. Ecosystem Roles >>](5-ROLES.md)
