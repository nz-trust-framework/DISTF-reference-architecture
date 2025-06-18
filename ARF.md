# New Zealand Digital Identity Services Trust Framework

![Architecture and Reference Framework](media/arf-masthead.png)

## 1 Introduction

### 1.1 Context

In 2023 the New Zealand Parliament passed the [Digital Identity Services Trust Framework Act 2023](https://legislation.govt.nz/act/public/2023/0013/latest/LMS459583.html) (herein, the Act). The purpose of the Act, was to "establish a legal framework for the provision of secure and trusted digital identity services for individuals and organisations".

Following the passage of the Act, the Prime Minister designated the Department of Internal Affairs to host two of the statutory entities created by the Act: the Trust Framework Board and the Trust Framework Authority. Since 2023, those statutory entities have developed the accreditation processes, including the regulations and rules, and the Trust Framework Authority can now accredited providers and the digital identity services they provide.

### 1.2 Purpose

The Act, together with its secondary legislation, lays down the requirements for a modern digital identity ecosystem in Aotearoa New Zealand. These instruments explain the *what* and *why*, but they do not spell out how to put those requirements into practice.

The *how* is the role of this **Architecture and Reference Framework** (herein, the ARF). It sets out the practical blueprint for operating a contemporary digital identity ecosystem in New Zealand and offers guidance to every participant, not just the providers and services accredited under the Trust Framework. By aligning with international standards, it also promotes cross-border interoperability, allowing New Zealand’s digital identity services to work seamlessly with those of other jurisdictions. This is crucial for a nation that relies on trade, tourism and the global mobility of its people.

### 1.3 Definitions

The definitions in this document can be found in [Annex 1](annexes/Annex-1-Definitions.md).

> :warning: While care has been taken to ensure consistent use of language throughout this document, it is inevitable language will contradict or confuse when considered alongside other documents, legislation, standards, or even within this document. In the first instance, check alignment with the provided definitions. However, if there is clear ambiguity or error, please make a change request.

### 1.4 Scope

### 1.5 Disclaimers

Where there are discrepencies or contradictions, the following is the order of precedence of documents.

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

### 2.4 Use Cases

#### 2.4.1 Overview

#### 2.4.2 In person age verification

#### 2.4.3 Mobile Driver Licence

#### 2.4.4 Online customer due diligence

#### 2.4.5 Caregiver holding minor's vaccination records

#### 2.4.6 Other use cases

## 3 Ecosystem Roles

### 3.1 Overview

### 3.2 Users

### 3.2 Information Services

### 3.3 Binding Services

### 3.4 Credential Services

#### 3.4.1 All of Government Credential Issuance Service

### 3.5 Authentication Services

#### 3.5.1 Authenticators

The DISTF Rules define an authenticator as:

> **Authenticator** means information or another thing, for example a password, a personal identification number, or a fingerprint, that-
> -  is known to, or possessed or controlled by, a person; and
> -  is bound or otherwise linked to the person during an interaction with a service; and
> -  can be used by the person during subsequent interactions with the service to prove that they are the same person.

The [New Zealand Identification Standards](https://www.digital.govt.nz/standards-and-guidance/identity/identification-management/guidance/guide-to-authenticator-types) classify authenticators into three groups:

-  **Knowledge factor**: something you know. Examples include a password, a PIN code, or a shared secret.
-  **Posession factor**: something you possess. Examples include a credential, a passkey, or a one-time code generator.
-  **Biometric factor**: something you are or do. Examples include facial, fingerprint, or iris recognition.

The choice of authenticator is an important design decision when implementing a facilitation service (for instance, digital wallet) given the level of assurance it provides to both credential services issuing credentials, and to relying parties needing to trust that the user of the credential is the person the credential was issued to.

For instance, an online website that allows age verification through the remote presentation of a trusted credential will place far greater reliance on that presentation in the knowledge that the credential was secured using a biometric factor authenticator (and therefore near impossible for anyone but the user to present) than they will over a knowledge factor authenticator (where, for instance, the child of a parent knows the PIN).

##### 3.5.1.1 Smartdevice on-device authenticators

Both iOS and Android include two main categories of on-device authenticators that can be utilised by an authentication service: knowledge-based (PIN, passcode or pattern) and biometrics. It is recommended that developers of faciliation services (digital wallets) on devices running iOS and Android consider utilising these in-built authenticators given: (1) users' existing use and configuration of these authenticators; (2) the well-established security and privacy of these authenticators; and (3) that both knowledge based and biometric based authenticators are available.

> :warning: Developers creating facilitation services (digital wallets) will need to carefully consider whether to support devices that do not support biometric authenticators. This entails a trade off; not supporting older or cheaper devices without biometric authenticators risks exasperating digital inclusion and excluding certain users, but devices that only offer knowledge based authenticators don't provide the same level of assurance to relying parties that the genuine user is the one authorising an online/remote presentation.

#### 3.5.2 RealMe Login Service

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
