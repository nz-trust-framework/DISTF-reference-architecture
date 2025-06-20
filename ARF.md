# New Zealand Digital Identity Services Trust Framework

![Architecture and Reference Framework](media/arf-masthead.png)

## 1 Introduction

### 1.1 Context

In 2023 the New Zealand Parliament passed the [Digital Identity Services Trust Framework Act 2023](https://legislation.govt.nz/act/public/2023/0013/latest/LMS459583.html) (herein, the Act). The purpose of the Act, was to "establish a legal framework for the provision of secure and trusted digital identity services for individuals and organisations".

Following the passage of the Act, the Prime Minister designated the Department of Internal Affairs to host two of the statutory entities created by the Act: the Trust Framework Board and the Trust Framework Authority. Since 2023, those statutory entities have developed the accreditation processes, including the regulations and rules, and the Trust Framework Authority can now accredited providers and the digital identity services they provide.

### 1.2 Purpose

The Act, together with its secondary legislation, lays down the requirements for a modern digital identity ecosystem in Aotearoa New Zealand. These instruments explain the *what* and *why*, but they do not spell out *how* to put those requirements into practice.

The *how* is the role of this **Architecture and Reference Framework** (herein, the ARF). It sets out the practical blueprint for operating a contemporary digital identity ecosystem in New Zealand and offers guidance to every participant, not just the providers and services accredited under the Trust Framework. By aligning with international standards, it also promotes cross-border interoperability, allowing New Zealand’s digital identity services to work seamlessly with those of other jurisdictions. This is crucial for a nation that relies on trade, tourism and the global mobility of its people.

### 1.3 Definitions

The definitions in this document can be found in [Annex 1](annexes/Annex-1-Definitions.md).

> :warning: While care has been taken to ensure consistent use of language throughout this document, it is inevitable language will contradict or confuse when considered alongside other documents, legislation, standards, or even within this document. In the first instance, check alignment with the provided definitions. However, if there is clear ambiguity or error, please make a change request.

### 1.4 Scope

### 1.5 Disclaimers

Where there are discrepancies or contradictions, the following is the order of precedence of documents.

-  Privacy Act 2020 (as per DISTF Act, s17)
-  Digital Identity Services Trust Framework Act 2023
-  Digital Identity Services Trust Framework Regulations 2024
-  Digital Identity Services Trust Framework Rules 2025
-  Digital Identity Serivces Trust Framework Architecture and Reference Framework (this document)

> :grey_question: Where do Compliance Orders issued under the Act fit in this order of precedence? Below rules but above the ARF?

### 1.5 Additional Topics

### 1.6 Change log

## 2 New Zealand Digital Identity Ecosystem

### 2.1 Introduction

### 2.2 Ecosystem Design

### 2.3 Te ao Māori Approaches to Identity

### 2.4 The role of the Government App

The Department of Internal Affairs has begun work on an app that will improve the way New Zealanders interact with government. The government app will provide a:

- secure way for agencies to communicate with New Zealanders
- safe digital wallet to hold accredited digital credentials 
- direct way to access government services and make payments.

- The app will prioritise usability, security and privacy for all users and will always be optional to use.

The app will hold digital credentials accredited under the Digital Identity Services Trust Framework. This will include credentials from government agencies and accredited private sector providers – for example, a digital driver’s licence.

The app will seek accreditation under the DISTF as an [authentication service](#35-authentication-services) and as a [facilitation service](#36-facilitation-services).

As such, it is expected that the Government App, and its digital wallet functionality, will play an important role in the development of New Zealand's digital identity ecosystem.

Follow progress on the Government App programme on [digital.govt.nz](https://www.digital.govt.nz/digital-government/programmes-and-projects/government-app-programme)

> :warning: the introduction of an accredited digital wallet by the government *does not* preclude the ability for other digital wallet providers to enter the market, seek accreditation, and hold accredited credentials including those issued by government.

### 2.5 Use Cases

#### 2.5.1 Overview

#### 2.5.2 In person age verification

#### 2.5.3 Mobile Driver Licence

#### 2.5.4 Online customer due diligence

#### 2.5.5 Caregiver holding minor's vaccination records

#### 2.5.6 Other use cases

## 3 Ecosystem Roles

### 3.1 Overview

### 3.2 Users

### 3.2 Information Services

### 3.3 Binding Services

### 3.4 Credential Services

#### 3.4.1 All of Government Credential Issuance Service

### 3.5 Authentication Services

An **authentication service** is a digital identity service that enables a person to use an **[authenticator](#351-authenticators)** to access a service.

Importantly, an authentication service requires both:
- use of one or more authenticators; and
- management of the authenticator lifecycle.

For example, an authentication service might utilise a PIN code as the **authenticator** to restrict access to a digital wallet. But the service, in managing the authenticator lifecycle, also needs to consider and manage factors like:
-   how often the PIN code needs to be changed; 
- the minimum length and complexity of the PIN code; 
- how to manage repeated incorrect attempts at the PIN code; and
- ensuring the user is aware of their responsibilities in regard to managing the authenticator.

For implementation advice for an authentication service, refer to the [New Zealand Identification Standards: Implementing the Authentication Assurance Standard](https://www.digital.govt.nz/standards-and-guidance/identity/identification-management/guidance/implementing-the-authentication-assurance-standard).

#### 3.5.1 Authenticators

The DISTF Rules define an authenticator as:

> **Authenticator** means information or another thing, for example a password, a personal identification number, or a fingerprint, that-
> -  is known to, or possessed or controlled by, a person; and
> -  is bound or otherwise linked to the person during an interaction with a service; and
> -  can be used by the person during subsequent interactions with the service to prove that they are the same person.

The [New Zealand Identification Standards](https://www.digital.govt.nz/standards-and-guidance/identity/identification-management/guidance/guide-to-authenticator-types) classify authenticators into three groups:

-  **Knowledge factor**: something you know. Examples include a password, a PIN code, or a shared secret.
-  **Possession factor**: something you possess. Examples include a credential, a passkey, or a one-time code generator.
-  **Biometric factor**: something you are or do. Examples include facial, fingerprint, or iris recognition.

The choice of authentication service (and its authenticators) is an important design consideration for a facilitation service (for instance, digital wallet) given the level of assurance it provides to both credential services issuing credentials, and to relying parties needing to trust that the user of the credential is the person the credential was issued to.

> ##### :laptop: Example – Online Age Verification
>
> An online gambling website wants to restrict access to users over the age of 18. To do this, it implements online age verification, allowing users to present accredited digital credentials as evidence of age.
>
>The website accepts the remote presentation of any accredited digital credential that can demonstrate age eligibility. However, the website will need to consider the strength of the authenticator attached to the credential given the presentation is remote.
>
>- **Accept knowledge based authenticators**  
  This option provides *some* assurance that the credential belongs to the user. However, it is vulnerable to misuse — such as a teenager accessing a parent's wallet using a known PIN and shared device.
>
>- **Require biometric based authenticators**  
  This provides *strong* assurance that the credential is being presented by the legitimate user, as biometric methods like fingerprint or facial recognition are difficult to fake. However, not all wallets or devices support biometrics, which may limit accessibility.
>
>- **Independently match biometric data**  
  The website could request the credential’s portrait during presentation and independently verify it using a real-time online biometric confirmation (e.g., facial match). This provides *very strong* assurance but involves significant technical and privacy overhead, and may create barriers and resistance for users.
>
>Ultimately, the website must balance its regulatory obligations with usability and inclusion, selecting an approach that provides sufficient assurance without unduly excluding legitimate users.


##### 3.5.1.1 Platform authenticators

Platform authenticators, also known as on-device authenticators or native device authenticators, are authenticators that live on a user's device - e.g. iOS ([Local Authentication](https://developer.apple.com/documentation/localauthentication)), Android ([BiometricPrompt](https://developer.android.com/identity/sign-in/biometric-auth)), and Windows ([Windows Hello](https://learn.microsoft.com/en-us/windows/apps/develop/security/windows-hello)). These platform authenticators generally support to categories of authenticator: knowledge-based (PIN, password, or pattern) and biometrics.[^1] 

It is recommended that potential providers of authentication services consider utilising these platform authenticators. The benefits of the authenticators include:
-   users' already utilise and have these authenticators configured; 
- existing well-established security and privacy; and 
- flexibility in that knowledge based and biometric based authenticators are available.

Importantly, incorporation of these robust authenticators is generally easier than developing bespoke authenticators.

> :warning: in designing an authentication service, providers must weigh whether to support devices that lack biometric authentication. 
> 
>Removing support for older or more-affordable handsets that don't support biometric authenticators could deepen digital exclusion, yet devices restricted to knowledge-based authenticators cannot give relying parties the same confidence that the person authorising a remote presentation is the genuine user.

[^1]: Technically, these devices also support possession factor authenticators in the form of passkeys and other stored cryptographic keys. However, given access to these is generally restricted behind a biometric or knowledge factor authenticator, these authenticators aren't as relevant.

#### 3.5.1.2 Passkeys

#### 3.5.1.3 Digital credentials as authenticators

#### 3.5.3 RealMe Login Service

[**RealMe Login Service**](https://developers.realme.govt.nz/how-realme-works/whats-the-realme-login-service) is an authentication service run by the the Department of Internal Affairs and provides a single login, letting citizens use one username and password to access a wide range of services online. It also offers two-factor login where the online service requires a higher level of security. It is available to organisations in the wider government sector, but is not currently offered to commercial organisations.

> :warning: As of June 2025, RealMe Login Service is not accredited as an authentication service under the DISTF.

### 3.6 Facilitation Services

### 3.7 Verification Services

#### 3.7.1 NZ Verify

#### 3.7.2 Reader Authentication

### 3.8 Relying Parties

#### 3.8.1 Privacy Act 2020

### 3.9 Other Digital Identity Services

#### 3.9.1 Trust Registers

#### 3.9.2 Exchange Services

#### 3.9.3 Identity Providers

## 4 High level Architecture

### 4.1 DISTF Principles

### 4.2 Identity Proofing/Enrolment

#### 4.2.1 Stand-alone Information (and Binding) Services

### 4.3 Credential Issuance

### 4.4 Presentation

#### 4.4.1 In person (proximity) presentation

##### 4.4.1.1 Flash pass presentation

#### 4.4.2 Online (remote) presentation

### 4.5 Other processes

#### 4.5.1 Revocation of credentials

## 5 Data and attribute standards

### 5.1 Data and attributes

### 5.2 Mandated data standards

### 5.3 New Zealand-specific namespaces and attributes

#### 5.3.1 Austroads-specific namespace

## 6 Trust Model

### 6.1 Scope

*Need to insert a diagram here replicating the triangle of trust and noting how each actor gains trust etc.*

### 6.2 Accreditation

#### 6.2.1 Overview

#### 6.2.2 Provider Accreditation

#### 6.2.3 Information Management Assessment

#### 6.2.4 Privacy Assessment

#### 6.2.5 Security Assessment

#### 6.2.6 Ongoing Requirements

### 6.3 Trust Register

### 6.4 Levels of Assurance

#### 6.4.1 Regulatory Assurance Levels

#### 6.4.2 New Zealand Identification Standards Levels of Assurance

### 6.4 Trusted Issuers

#### 6.4.1 Issuers as Credential Services

#### 6.4.2 Issuers as standalone information (and binding) services

### 6.5 Trusted Users

### 6.6 Trusted Facilitation Services

### 6.7 Trusted Verifiers and Relying Parties

## 7 Annexes
