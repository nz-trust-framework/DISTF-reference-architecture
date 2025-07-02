# **Digital Identity** in New Zealand
A Brief Overview

## Executive Summary
This paper explores the evolution and application of digital identity in New Zealand, addressing the need for secure, privacy-preserving, and user-centric solutions for sharing personal and organisational information in a digital age. It highlights the limitations of traditional systems reliant on physical documents or centralised digital platforms and introduces decentralised (or self-sovereign) digital identity as a transformative alternative.

Decentralised digital identity empowers individuals and organisations by allowing them to control information about them through digital credentials stored in digital wallets. These credentials can include various data points such as identification, qualifications, and financial details, and they enable users to share information securely and selectively. The paper outlines how this approach enhances privacy and security while reducing the risks of identity fraud, data breaches, and inefficiencies in traditional identity verification processes.

The introduction of the Digital Identity Services Trust Framework Act 2023 marks a significant milestone for New Zealand, providing a formal structure for accrediting digital identity services. This framework establishes trust across a decentralised ecosystem by defining standards for issuers and wallets. Accreditation ensures compliance with stringent security, privacy, and identification management standards, fostering confidence among users and service providers alike.

Through illustrative use cases, such as Sam using a digital driver licence for age verification and Helen streamlining business banking with digital credentials, the paper demonstrates the practical benefits of decentralised digital identity. These examples showcase the flexibility of the system in both online and in-person scenarios, empowering users to interact securely and efficiently across different contexts.

A mature digital identity environment offers significant economic and productivity benefits too, potentially amounting to billions of dollars annually. It enables instant, secure online identity verification—dramatically reducing the time and cost of in-person checks across both public and private sectors—and improves government efficiency, particularly during crises. Digital identity also mitigates fraud and scams through stronger verification protocols, addressing issues that cost New Zealanders an estimated $2.3 billion each year. International modelling reinforces the economic value, with projected gains ranging from $2.1b to over $12b annually based on comparable jurisdictions such as the UK, Australia, and Canada.

Finally, the paper addresses challenges such as misinformation and emphasises the importance of public education on the benefits and safeguards of digital identity services. It underscores that participation is voluntary, user privacy is paramount, and the framework enables greater control and convenience for individuals.

The development of decentralised digital identity in New Zealand represents a significant step towards a more secure, interoperable, and user-centric identity ecosystem, aligning with global standards and technology and consumer expectations for modern, digital-first solutions.

## Digital Identity in New Zealand

### Background

Sharing information in a variety of forms has been commonplace for hundreds if not thousands of years. From tribal tattoos and markings, through letters of introduction, to official certificates of birth marriage or qualification. All these approaches, and many others, have methods built in to allow the recipient to identify who created the information and decide if they would trust it. 

All these methods have one thing in common: they need to be physically inspected by someone who knows what they are looking for to determine their authenticity. While internet technology has advanced across many areas of society in recent years, it did not provide an alternative approach to trusted information sharing in its initial design.

> "The internet was built without an identity layer"
> 
> *Kim Cameron, former Chief Architect of Identity, Microsoft*

Through the boom of dotnet companies and the rise of more transactional services (often referred to as Web 2.0), many organisations looked to the internet to provide faster, easier, more cost-effective ways to reach their customers. While accessing services over the internet for existing customers was relatively easy, onboarding new customers was challenging as it still required people to visit a physical location to have documents and additional evidence viewed and recorded.

For over two decades, tech giants, entrepreneurs, standards bodies, and governments across the globe have been trying to replicate the trust mechanisms of physical documents in the digital world. This has produced a wide range of commercial solutions based on proprietary technology that have pushed for market dominance. In recent years, standards bodies such as ISO, NIST, IETF, W3C, and the Open ID Foundation have been developing new, open standards to codify the technology and processes of trusted information sharing in a digital world.

At the same time there has been an arms race between cyber security professionals and hackers. The current processes of gathering identification documents and other evidence and recording this digitally creates a treasure trove for hackers to trawl through if they get access. The security of information can never be completely assured.

This issue is exacerbated by poor identification practice. Organisations offering digital onboarding processes may do a reasonable job of verifying that the information they receive during onboarding is correct and has come from a legitimate source. However, they often do a poor job of verifying the information belongs to the actual person sitting behind the keyboard. This creates a gap for hackers to steal someone else’s legitimate identification information and use it to create new accounts elsewhere, often for financial gain.

As a result, people find it hard to share information about themselves online in a secure, trusted, and efficient manner. This can be attributed to two key reasons: lack of access to their information in a digitised format, and lack of suitable solutions to manage and share their information. For example, much personal information is held by public and private organisations, with specific control, access, and use requirements. It can often be reused, but the processes are not user centric. 

A third reason it is not easy to share information and the systems that support sharing between organisations, and between government and the private sector do not currently easily support interoperability and reusability.

At the same time, the proliferation of contactless pay and digital payment wallets has led to changing consumer preferences. Increasingly, consumers want the option to go “wallet-less” and rely instead on digital wallets on their smartphone or smartwatch. Just as digital payments have eased the online process, so too are consumers finding digital payments are easing in-person transactions. This is creating a growing expectation that forms of digital identity are made available on smart devices that work just as easily for in-person transactions as they do for online ones.

People need to share their information, but the lack of easy, safe, and secure ways to do that online and in-person can lead to greater risks of privacy breaches, identity fraud and cybercrime as well as frustration and friction for users and the relying parties with whom they wish to share their information.

### Decentralised (or Self-Soverign) Digital Identity

Technological advancements, inspired by blockchain and other distributed ledger technologies, led to the emergence of new forms of digital identity during the mid-2010s. These innovations eliminate the need for a central or federated identity provider (like RealMe) to act as a constant intermediary.

Decentralised (or Self-Sovereign) Digital Identity empowers individuals by giving them exclusive control over their identity documents and personal data. Instead of relying on a central authority to manage this information, individuals can securely store digital credentials in a digital wallet. These credentials may include identity data such as a driving licence, qualifications, employment history, or financial details.

With this approach, individuals decide when and with whom to share their data, enhancing privacy and security. This flexibility applies to both in-person and online interactions, such as signing up for services or making age-verified purchases. Importantly, decentralised systems ensure that issuers cannot track when or where a user presents their digital credential, a significant improvement over centralised or federated systems. At the same time, the relying party can be assured that the credential was issued by the legitimate issuer and has not been tampered with.

Importantly, a digital credential is verifiable, enabling the relying party to independently confirm a credential's authenticity without involving the issuer.

In essence, decentralised digital identity with digital credentials is a "back to the future" approach, replicating the trusted credential model of physical documents but with enhanced features in a digital format.

![Diagram 1: The Trust Triangle](https://github.com/jameslittlenz/nz-trustframework-arf/blob/main/media/ecosystem-diagram.png)
*Diagram 1: the “trust triangle” showing an issuer providing a credential to a user, who then chooses who and when to share it with a relying party.*

The above diagram demonstrates the basic model on which a user enrols with an issuer, an issuer creates and issues a digital credential to the user, and then the user can present the information from that credential to a relying party who can rely on the validity of the information.

Consider the example of a digital (or mobile) driver licence in use.

Jane Doe (User) enrols with the state transport agency (Issuer) to prove she is who she proports to be. Jane already has a physical driver licence and uses this to demonstrate to the transport agency that she is Jane. The state transport agency then issues her a copy of her driver licence in a digital form (the Credential Issuance) to a digital wallet she already has installed on her smartphone. She only needs to do this once.

A few days later, Jane wants to rent a car. She logs in to the rental car company’s (Relying Party) website (Verifier) and proves who she is and that she can drive using her digital driver licence. The next day she goes into the rental car company store and again provides her digital driver licence, but this time she presents it in person to the attendee who has a verifier app on their phone.

Both online and in person, the rental car company has verified her digital driver licence by checking it’s correctly signed and was issued by the state transport agency. But at no point was the state transport agency notified or alerted that Jane was using the digital credential they issued to her. Further, Jane can reuse the digital driver licence as often as she likes. She would only need to re-enrol and have the credential re-issued if she lost her phone or when the licence expires.

## New Opportunities

The example above represents just one possibility, based on an existing physical credential. Now imagine a broader scenario where any public agency, private company, iwi, or NGO could act as an issuer of identity and other assured information for users. These credentials could encompass a wide range of possibilities, including but not limited to:

*  **Personal Identification**: Digital versions of government-issued IDs such as passports, driver's licences, and national identity cards.
*  **Educational Qualifications**: Certificates and diplomas from educational institutions, including degrees, professional certifications, and course completions.
*  **Iwi Affiliation**: credentials denoting iwi and hapu affiliation issued by the iwi.
*  **Professional Credentials**: Employment records, professional licences, and memberships in industry associations.
*  **Financial Information**: Bank account details, credit scores, and transaction histories.
*  **Health Records**: Medical histories, vaccination records, and health insurance information.
*  **Proof of Address**: Utility bills or rental agreements serving as verification of residence.
*  **Memberships and Subscriptions**: Digital proofs of membership in clubs, organisations, or subscription services.
*  **Travel Documents**: Digital boarding passes, passports, visas, and frequent traveller memberships.
*  **Delegated Authority**: Authority for a person to act on behalf of another person, whether guardianship, power of attorney, a lawyer or accountant acting on behalf of a client, or delegated authority to act for a business or trust.
*  **Self-Attested**: Information self-attested by the user, for instance a statutory declaration, self-certification, or tax code declaration.
*  **Custom Attributes**: Any other verifiable, assured or attested information.

The opportunities and potential number of issuers is nearly limitless as is the assured information they can provide to users. 

However, this flexibility creates one fundamental problem that must be addressed.

## Trust Frameworks
### Addressing the problem

In a digital identity ecosystem with an almost limitless number of potential issuers, relying parties face a fundamental challenge: deciding which issuers and information to trust.

This challenge cannot be solved by technology alone. 

While verifier applications can confirm that a credential was issued by the claimed issuer and that it hasn’t been tampered with, they provide no assurance about the validity of the information used to create the credential in the first place.

For instance, a malicious issuer could produce legitimately signed credentials containing false information, leaving the relying party unaware that the credential is valid, but the information is fraudulent. Similarly, a malicious issuer could issue correct information but to the wrong person, while a negligent issuer might issue legitimate credentials but fail to protect the source information, leading to privacy and security breaches.

In New Zealand, trust in physical credentials typically relies on reputation. We tend to accept credentials from reputable organisations—often large public agencies—and reject those from others. This is then reflected in our legal and regulatory frameworks.

This is problematic for several reasons.

First, it restricts legitimacy to large, well-known government organisations, excluding other potential trustworthy issuers. Second, it forces each relying party to independently determine which issuers they trust, a process that often defaults back to government agencies for simplicity, reinforcing the first issue. Third, reliance on reputation alone does not ensure trustworthiness or assurance of the information provided. It merely assumes trust based on perception rather than rigorous validation.

A trust framework seeks to address this issue.

A trust framework is a formal set of policies, standards, and technical protocols that define how different entities within a decentralised digital identity ecosystem must operate. It provides the foundational rules and guidelines that ensure trust among all participants, by establishing minimum requirements for identity management, security and privacy.

Rather than relying parties only trusting issuers based on reputation, a trust framework establishes which issuers (and wallets) are trustworthy. The trust framework is agnostic to whether the services are from the public or private sector, large organisations, startups or NGOs.

### Digital Identity Services Trust Framework

The Digital Identity Services Trust Framework Act 2023 came into legal effect in 2024 and establishes a trust framework for digital identity services in New Zealand. The trust framework sets out how accredited digital identity providers and their services must work in New Zealand, to ensure that people’s information and privacy is protected.

Accreditation is opt-in. While digital identity service providers do not need to become accredited to deliver a service, there are clearly benefits. Users can be more confident that accredited services are trustworthy and will protect their personal information. Importantly, it addresses the problem of which issuers should be trusted by relying parties and establishes a legal basis on which to define trusted issuers and trusted wallets.

**IMAGE**
*Diagram 2: parties in a decentralised digital identity ecosystem seperated into the services defined by the NZ Trust Framework*

The Trust Framework establishes five digital identity services that can seek accreditation.
*  **Information services** provide personal or organisational information and a level of assurance as to the accuracy of that information. The information service may be the authoritative source of this information or may assess the accuracy of information from a different source.
*  **Binding services** link personal or organisational information to the correct individual or organisation by means of one or more checks that the information relates to that party. This is often completed in combination with an information service.
*  **Authentication services** enable a person to use an authenticator to access a credential or facilitation mechanism (for example, a log-in service or a passkey.)
*  **Credential services** create a reusable standards-based digital credential containing information bound to the user.
*  **Facilitation services** enable a person to store and present a credential to a relying party either online or in person (for example, a digital wallet.)

Under the Trust Framework, providers need to offer one or more of these services to seek accreditation. For some providers, if they provided an “end-to-end” digital identity solution they will seek accreditation for all five services. Other providers may only be accredited for one or two of these services, and then they can make those services available to other providers or to end users as a stand-alone service.

It is also worth discussing who isn’t regulated under the Trust Framework.
*  **Users** are free to use their digital credentials with whom and how they choose. There are no restrictions on their use of their own digital credentials for legal purposes.
*  **Relying parties** are also not regulated under the trust framework. Just as there’s no requirement to be accredited to receive physical credentials, there’s equally no requirement to receive digital credentials. This ensures that any organisation or individual, no matter how big or small, can accept digital credentials and ensures that digital credentials are widely accepted. However, relying parties have clear obligations under New Zealand’s Privacy Act regardless of whether the information they receive comes from digital credentials or not.

Given the evolving nature of digital identity in New Zealand and abroad, the Trust Framework is designed to be flexible to ensure it remains fit-for-purpose as technology, standards, and other jurisdictions evolve and change.

The Trust Framework is in full legal effect and open to accredit digital identity providers and their services. 

For more information about the Trust Framework, visit: [DIA | Trust Framework for Digital Identity](https://www.dia.govt.nz/trust-framework)
