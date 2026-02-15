# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 4.0 Privacy
As digital identity infrastructure evolves, the need for a secure, privacy-preserving, and interoperable ecosystem becomes more critical. The Reference Architecture (RA) is therefore grounded in the Privacy Act 2020 and Trust Framework Authority (TFA) guidance.

Under the Digital Identity Services Trust Framework (DISTF), providers are expected to demonstrate that privacy is embedded in service design and operations. Independent privacy evaluation supports this by assessing whether providers meet:
- the Digital Identity Services Trust Framework Act,
- the Digital Identity Services Trust Framework Regulations,
- the Digital Identity Services Trust Framework Rules, and
- the Privacy Act 2020.

The sections below summarise the core privacy expectations and how they align with the Privacy Act and TFA evaluation requirements.

### 4.1 Privacy Impact Assessment
Each accredited service should have a completed Privacy Impact Assessment (PIA). At minimum, the PIA should include:
- a detailed service description;
- information already held and information to be collected;
- the purpose of collection;
- information-flow mapping (including third parties);
- how information is stored, accessed, used, and disposed of;
- assessment against applicable Privacy Act obligations (including the Information Privacy Principles);
- mitigation analysis for identified privacy risks; and
- consideration of any relevant privacy code of practice.

The PIA should be formally approved by the provider, with evidence that identified risks have been addressed.

### 4.2 Communicating privacy impacts to credential holders
For credential-based services (including ISO 18013-5 implementations), providers should make privacy implications transparent to users in clear, accessible language.

Where a digital wallet supports local transaction history, the design should ensure that:
- access to the log is controlled by the user;
- sharing is user-directed; and
- records are protected against unauthorised tampering.

Where relying parties collect personal information from credential presentations, they should provide clear statements covering:
- purpose of collection;
- what information is retained;
- disposal/retention period; and
- any onward disclosure or approved secondary use.

### 4.2.1 Selective disclosure
A core privacy benefit of digital credentials is selective disclosure: only the minimum necessary attributes should be presented.

Implementations should ensure users can review requested attributes and authorise release at the point of presentation, including when full disclosure is legally required.

### 4.3 Designated individual
Providers should appoint a designated individual accountable for privacy oversight (which may be the Privacy Officer required under the Privacy Act 2020).

Responsibilities should be formally documented and include:
- PIA governance and review;
- compliance oversight (legislation, rules, and codes);
- privacy policy ownership; and
- privacy risk monitoring and escalation.

### 4.4 Privacy training
Staff (including relevant contractors) should complete privacy training at onboarding and on a recurring basis.

Training should cover:
- lawful collection and use of personal and organisational information;
- access and correction processes;
- storage, use, and disclosure requirements;
- incident and complaint procedures; and
- breach identification and escalation.

Providers should maintain records of completion, follow up overdue training, and communicate policy/process changes in a structured way.

### 4.5 Privacy incident management
Providers should maintain a Privacy Incident Response Plan and a privacy incident register (including near misses).

The response plan should define:
- roles and responsibilities;
- containment, assessment, escalation, and notification steps; and
- reporting pathways (including to the Office of the Privacy Commissioner and TFA where required).

**Privacy Act alignment:** for notifiable privacy breaches, notification obligations under sections 113 and 114 are triggered where it is reasonable to believe a breach has caused, or is likely to cause, serious harm. The Act requires notification **as soon as practicable** after becoming aware of a notifiable breach. The Act does not prescribe a fixed 72-hour deadline.

### 4.6 Privacy statement
Providers should maintain a Privacy Statement (or equivalent notice) aligned with Information Privacy Principle 3.

The statement should explain:
- that information is being collected;
- why it is being collected;
- intended use;
- who will receive it (including third parties, where applicable);
- whether provision is mandatory and consequences if not provided; and
- how individuals can access and correct their information.

The statement should be easy to find (for example, in service interfaces and websites) and reviewed regularly.

### 4.7 Breach reporting
Providers should maintain robust breach-reporting procedures consistent with the Privacy Act 2020 and DISTF Rules.

This includes processes to:
- identify potential breaches;
- assess notifiability (serious harm threshold);
- notify the Office of the Privacy Commissioner and affected individuals when required; and
- retain evidence and records of decisions and actions.

### 4.8 Secondary use
For DISTF-accredited services, information collected for the accredited service should not be used for unrelated secondary purposes unless the user has explicitly authorised that use.

**Privacy Act alignment:** Information Privacy Principle 10 limits use of personal information to the purpose for which it was obtained, subject to statutory exceptions. The DISTF expectation above is a stricter, service-level control and should be implemented in a way that remains consistent with the Act.

### 4.9 Collection from verifiable credentials and user notification
Collection of personal information from verifiable credentials should be addressed in the provider's PIA and reflected in user-facing notices, as outlined in [4.1 Privacy Impact Assessment](#41-privacy-impact-assessment).

[<< 3. Accessibility and Inclusion](3-ACCESSIBILITY.md) | **4. Privacy** | [5. Ecosystem Roles >>](5-ROLES.md)
