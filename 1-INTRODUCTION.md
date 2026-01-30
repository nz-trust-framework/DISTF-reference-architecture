# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 1 Introduction 
 
### 1.1 Context 
In 2023, the [Digital Identity Services Trust Framework Act 2023]() (the Act) was enacted. The Act establishes a legal framework for the provision of secure, privacy-preserving, and trusted digital identity services for individuals and organisations. 

Following the enactment of the Act, the Prime Minister designated the Department of Internal Affairs to host two statutory entities created under the legislation: the Trust Framework Board and the Trust Framework Authority. Since 2023, these entities have developed the accreditation framework, including the associated regulations and rules. As a result, the Trust Framework Authority is now able to accredit providers and the digital identity services they offer.
 
### 1.2 Purpose 
The Act, together with its secondary legislation, establishes the requirements for a modern, secure, and privacy-preserving digital identity ecosystem in Aotearoa New Zealand. These instruments articulate the policy intent and objectives, but do not prescribe in detail how the requirements are to be implemented in practice.

This Reference Architecture addresses that implementation. It provides a practical blueprint for the operation of a contemporary digital identity ecosystem in New Zealand and offers guidance for all ecosystem participants, including but not limited to providers and services accredited under the Trust Framework.

By aligning with relevant international standards, the Reference Architecture supports cross-border interoperability, enabling New Zealand’s digital identity services to operate effectively with those of other jurisdictions. This is particularly important for New Zealand as a country that depends on trade, tourism, and the global mobility of its people.

The scope of the Reference Architecture also includes extensions to international standards where necessary to address New Zealand-specific requirements and ensure fitness for purpose for New Zealanders. This may require alignment with domestic legislation, regulations, and standards, including the New Zealand Information Security Manual (NZISM), the Protective Security Requirements (PSR), and relevant identification standards. 

While the Reference Architecture provides implementation guidance and direction, alignment with it does not, of itself, guarantee accreditation under the Trust Framework, nor does it ensure compliance with the Digital Identity Services Trust Framework Act 2023, associated regulations, or rules. Accreditation and compliance remain subject to the formal assessment processes and determinations of the Trust Framework Authority. 
 
### 1.3 Definitions 
The abbreviation and definitions in this document can be found in [Annex A: Abbreviations and Glossary]().
 
### 1.4 Scope 
This Reference Architecture (RA) defines the technical and operational design of New Zealand’s digital identity ecosystem under the Trust Framework. It sets out the architecture principles, core components, system roles, and operational patterns required to support trusted digital identity services across government and the private sector. 

The RA covers end‑to‑end processes and data flows associated with identity proofing and enrolment, authentication, credential issuance, binding, revocation, and the ongoing management of trust. It also describes the trust and governance mechanisms, such as trust lists, together with the security, privacy, and assurance controls required for compliance with the Trust Framework rules. Where relevant, the RA provides guidance on the application of international standards in a New Zealand context.

The architecture will illustrate how an individual or entity obtains a digital credential, stores it in a facilitation service (e.g., a digital wallet), and presents it to a relying party. It will describe all associated trust, assurance, and compliance steps, drawing on established patterns already in use in comparable jurisdictions. At the same time, the RA will reflect New Zealand’s distinct cultural, regulatory, and legislative context.

This document is intended as a guide for implementers across both the public and private sectors, on how to build or align their systems with the Trust Framework. It provides a reference architecture rather than a detailed solution design, offering adaptable templates and guidelines to support interoperability across diverse providers and technologies. The RA accommodates multiple implementation models, balancing flexibility with the need for common standards.

The RA is based on current legislative and regulatory settings and will reference the requirements in force at the time of publication. It will also help identify areas for future legislative refinement, including informing rules development to ensure issues surfaced through RA development can be addressed in subsequent iterations.

Interoperability with international ecosystems, such as those of the European Union and Australia, is a core design constraint. Where other jurisdictions mandate standards or approaches, the RA will consider compatibility where appropriate to support cross‑border trust and seamless user experiences.

The RA remains technology‑agnostic to the greatest extent possible, while leveraging open standards to ensure longevity as technologies evolve. As Artificial Intelligence (AI), including Agentic AI, becomes increasingly embedded in digital identity systems, the RA will emphasise transparent and enforceable accountability. Future iterations will further strengthen requirements to ensure that decision‑making autonomy and actions (including by agentic AI systems) can be reliably attributed back to an identified individual or organisation.

### 1.5 Out of Scope 

To maintain focus and avoid overlap with other regulatory or operational regimes, several areas are outside the scope of this Reference Architecture. The RA does not design, prescribe, or redefine the detailed operation of parallel or adjacent systems such as federated identity schemes, payment infrastructures, financial transaction networks, consumer data rights arrangements, or broader data‑sharing initiatives that operate under their own frameworks and standards. 

The architecture may reference how the digital identity ecosystem interacts with these systems, but it does not describe or mandate how those systems operate. For example, while a digital identity service may authenticate a person accessing a payment platform, the RA does not specify how payments are executed or settled. Similarly, privacy legislation, including the Privacy Act, already sets compliance obligations. The RA does not rewrite or reinterpret these requirements; instead, it assumes full adherence and refers to them where appropriate. 

The RA focuses on the practical implementation of established technologies and patterns that support the Trust Framework. It does not extend into speculative, emerging, or experimental concepts that sit outside current policy settings or technology maturity. These future‑oriented considerations may be explored in other work programmes but are not part of this architecture. 

The RA also does not prescribe specific implementation choices such as vendor products, proprietary tools, programming frameworks, or technology stacks. It provides principles, models, and standards that implementers must align with while allowing flexibility in how those requirements are met in practice. 

[< Contents]() | **1. Introduction** | [2. NZ's Digital Identity Ecosystem]()
