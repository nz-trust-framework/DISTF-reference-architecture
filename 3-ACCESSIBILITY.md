# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 3. Accessibility, Inclusion, and Te ao Māori Considerations
The development of any Digital Identity and verifiable credential product should ensure that it is inclusive so that as many people can use it.  As identity serves as a gateway to services, this is even more paramount.
Not all people have or want access to technology.  Some people do want to use digital technologies but cannot because of their skill levels or because the technologies were not designed to accommodate their disability, language, culture, or other socioeconomic or demographic circumstances.
To address these concerns the RA recommends that Digital Identity and Verifiable Credentials adopt a range of principles.

### 3.1 Accessibility and Inclusion Principles 
#### 3.1.1 Apply Accessibility Standards
Any digital identity solution should be accessible, that is, usable by those with disabilities. 
The Reference Architecture (RA) acknowledges that:
-	New Zealand’s Human Rights Act 1993 prohibits discrimination based on disability in the provision of goods and services.
-	New Zealand’s Bill of Rights Act 1990 legally compels the Government to adhere to the anti-discrimination requirements defined by the Human Rights Act in all its operations, policies, and legislation.
-	New Zealand signed and ratified the United Nation’s Convention on the Rights of Persons with Disabilities (CRPD) in 2008 which obligates it to take appropriate measures to ensure and promote access for disabled people, on an equal basis with others, to information and communications technologies and systems.
To meet the above obligations, digital hardware, software and interfaces should conform to:
-	Web Content Accessibility Guidelines (WCAG) 2.2 at Level AA .

#### 3.1.2 Ensure compatibility with Assistive Technologies
Assistive technologies are tools that help disabled people access and interact with information and environments. Examples include screen readers, voice recognition software, alternative keyboards, and hearing aids. 
WCAG addresses many of the issues with digital access that disabled people experience. However, to ensure real-world interoperability with assistive technologies: 
-	Enable accessibility features in web-based and native mobile apps and ensure that any digital identity solution does not lock out people who use assistive technologies. 

#### 3.1.3 Support Non-Digital Pathway
New Zealanders need an option to communicate and access services that are non-digital in nature where digital identities are required.  
What that means, is that all accredited parties must ensure:
-	Enrolling, verifying, revoking digital identities have a non-digital pathway available to potential and existing users.  Those options need to be able to be communicated to users at the point the digital functions are made available by the issuer of the credential and/or facilitation services provider.
-	Customer feedback loops should also include non-digital, over the counter options from the issuer.  This should also be displayed by the facilitation service in UI presented for the customer, where opportunities are given for customer feedback in digital form.  Please also note:
    -	Email and SMS are discouraged as a primary form of engagement to provide or remove services of digital identities as Phishing uses these channels as a primary mechanism of fraud.
    - Preferences are ensuring that the feedback loops are provided through In-App messaging where there some level of authentication to ensure both the service provider and the user have the relevant authentication and identity proofing.  However non digital forms, like over the counter and voice (with also the appropriate level of security controls) should be made available. 
-	As per the legislation, digital identity is opt-in and not mandatory to adopt

#### 3.1.4 No Data Collected on Channel Preference or Personal Characteristics
To ensure there is no bias in the way services engage with parties without a digital identity, there will be no data and metadata collected on:
-	Information related to personal characteristics such as sex, age, language, ethnicity, or disability bound to an identity unless it is directed under an existing legal, legislative or regulatory requirement e.g. Disability parking credential, NZ Super eligibility etc. 
-	Choices or preferences to have a digital or non-digital credential unless legally permissible.

#### 3.1.5 Provide Multilingual Support
Language barriers can create significant issues. Supporting multiple languages ensures equitable access for culturally and linguistically diverse communities. To account for this:
-	Provide interfaces, customer engagement, guidance and help resources in multiple languages, including NZ’s official languages (te reo Māori, NZSL) and other commonly used community languages.

#### 3.1.6 Physical Equivalents of Digital Credentials
Inclusion also means accommodating people without reliable internet, devices, or digital literacy. Physical options prevent exclusion from essential services:
-	Offer secure, physical alternatives of digital credentials (e.g., ISO/IEC compliant smart chips that do not require power or the use of a mobile phone) for individuals who cannot or choose not to use digital channels.

#### 3.1.7 Plain Language
This may seem straightforward, but in the digital space we often rely on language that is technical, legal, or subject specific. Plain language helps ensure that everyone can understand how a service works and what is required of them. Situations where plain language must be used and industry jargon avoided include:

- Explaining the rights and obligations of the user. For example, in a privacy statement or privacy impact assessment, it must be clear:
  - what the user is expected to do  
  - how their data will be used  
  - what rights they have in relation to their data  
  - what data will be collected and how long it will be retained  
- Providing clear eligibility criteria for enrolling in, revoking, or accessing a service.
- Ensuring that any images provided are supported with text alternatives so that non visual users and assistive technologies can understand and interpret the instructions.
- Giving simple, direct guidance when issues occur, including how to get support.
- Offering alternative approaches when mobility is required during onboarding. For example, biometric liveness testing should include audio or text instructions, and accessible alternatives must be available for people who cannot complete the required movement due to disability or other reasons.

Technology is not perfect and can contain biases. It is important that all participants in the ecosystem understand these limitations in clear and easy terms as part of an accessibility and inclusion by design approach. The business processes that support people engaging with the digital identity ecosystem are equally important to ensure an inclusive, fair, safe, and accessible environment.


#### 3.1.8 Continual Testing, Improvement and Monitoring
Inclusion and accessibility cannot be fully achieved without lived experience informing decisions. Standards and technologies evolve, and user needs change over time. To ensure that digital identity solutions will continue to meet the needs of real people over time:
-	Involve people from different communities, especially the disability community and different age, cultural and linguistic groups in design, testing, and governance.
-	Establish ongoing accessibility and usability audits and feedback loops.

### 3.2 Te ao Māori Approaches to Identity
The Te Ao Māori approach to identity is holistic, collective, and deeply interconnected with whakapapa (genealogy), whenua (land), and whanaungatanga (relationships). Identity in Te Ao Māori is not simply about individual attributes; it reflects a person's connection to their ancestors, their iwi and hapū, and the land from which they originate. This worldview positions identity as relational and inherently collective, with individuals seen as custodians rather than sole owners of personal data, which is viewed as taonga; a treasure deserving careful stewardship.

Incorporating these principles into New Zealand’s digital identity ecosystem means actively upholding Māori sovereignty and enabling tino rangatiratanga (self-determination). This involves ensuring Māori communities have genuine control over their own data (recognising data as taonga) and are empowered to decide how their identity information is collected, managed, and shared. Practices should include designing digital identity solutions in genuine partnership with Māori, embedding culturally responsive processes, and respecting iwi and hapū governance structures.

Furthermore, embedding Te Ao Māori principles in digital identity can enhance trust and inclusivity across the wider ecosystem. Acknowledging data sovereignty, prioritising transparency, and promoting active consent align with broader digital identity principles such as user-centricity, privacy, and self-sovereignty. Ultimately, integrating Māori values into New Zealand’s digital identity ecosystem presents an opportunity not just to uphold Māori approaches to identity, but to ensure the best possible practice for all users.

These considerations are embedded into the Digital Identity Services Trust Framework legislation including, but not limited to, requirements for:

-  the Trust Framework to incorporate te ao Māori approaches to identity (DISTF Act, s3)
-  the Crown to give effect to the principles of te Tiriti o Waitangi/the Treaty of Waitangi (DISTF Act, s9);
-  the Trust Framework Board to consult with tikanga experts with knowledge of te ao Māori approaches to identity in the development of rules (DISTF Act, s21);
-  the Trust Framework Board to include representation from people who have expert knowledge on both te Tiriti and in engaging with Māori (DISTF Act, s47);
-  the establishment of a Māori Advisory Group to provide advice to the Trust Framework Board (DISTF Act, s53);
-	 the Trust Framework Authority to be guided by principles of tikanga Māori in handling complains (DISTF Act, s68);

>[!TIP]
>We welcome feedback on this Reference Architecture from those with experience in te ao Māori approaches to identity and how those approaches are best converted into technical and architecture practices.

[<< 2. New Zealand's Digital Identity Ecosystem](2-ECOSYSTEM.md) | **3. Accessibility and Inclusion** | [4. XXX >>](4-XXX.md)
