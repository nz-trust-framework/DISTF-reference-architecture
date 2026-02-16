# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 9. Data Model

One of the strengths of the ISO/IEC 23220 series is that it supports both interoperability and flexibility. For New Zealand it is important to adopt international data models and attributes wherever feasible to support global interoperability. 

Where international standards do not cover local requirements, New Zealand-based participants should apply namespaces and attributes in a consistent way. 

At the same time, individual issuers must have sufficient flexibility to represent data structures tailored to their specific services or use-cases.

In our interpretation of the ISO 23220 format, each credential is associated with a defined document-type. Each document type may include multiple namespaces, each of which is a collection of defined attributes. Attributes may themselves carry structured data (for example lists, dictionaries or lists of dictionaries). Conceptually a mobile document’s data is modelled as follows:

```
Document Type

	Name Space

		Attribute

		Attribute

			Structured Data

		[…]

	Name Space

		Attribute

		Attribute

		[…]

	[…]
```

Depending on the data an issuer is intending to represent, the following hierarchy of namespaces should be considered. It should also be noted that multiple namespaces may need to be utilised.


| Category | Description |
|---------|-------------|
| Internationally established document types and namespaces for specific use types (for example org.iso.18013.5.1) | Where applicable, issuers should align with internationally recognised and defined document types and namespaces as the basis for their digital credentials. In some areas these are well defined, such as driver licence, vaccine certificate, or motor vehicle certificate. Where additional attributes are required that are not covered by the specific namespace, these should be included in separate namespaces. |
| Internationally established namespace for generic uses (org.iso.23220.1) | When defining a credential that is not covered by a specific use namespace but contains generic attributes of person, place, or organisation, issuers should utilise the org.iso.23220.1 namespace and attributes. Where additional attributes are required that are not covered by this generic namespace, they should be included in separate namespaces. |
| Regional, industry, sector or collectively established namespaces (for example org.iso.18013.5.1.aamva, au.com.connectid.1) | Where an issuer is part of a regional, industry, sector, or other collective that has established a shared namespace, this should be used to ensure interoperability. For example, the banking sector may collectively agree on a document type and namespace for proof of bank account so that all banks are issuing to the same namespace. Where an organisation believes a namespace could be of collective benefit, they should seek agreement rather than creating a specific namespace. |
| New Zealand common namespace (nz.govt.digital.common.1) | Where an issuer wants to utilise attributes not otherwise defined in the above namespaces but common to New Zealand, they should include them in the New Zealand common namespace. |
| Specific namespaces | When attributes are not covered by any of the above namespaces or are specific to an issuer’s data, the issuer should create their own well defined namespace and set of attributes in accordance with ISO 23220 2 requirements. |

### 9.1 Heirarchy of namespaces

#### 9.1.1 Internationally name spaces for specific use types 
In the first instance, issuers should always look to align with internationally recognised and defined doctypes and namespaces as the basis for their digital credentials. The below is a non-exhaustive list of specific document types and their name spaces.

| Document Type | Description |
|---------------|-------------|
| Photo ID (photoID) | ISO/IEC 23220-4 Annex C establishes a specific Photo ID profile (`org.iso.23220.photoID.1`) for credentials intended to be used as photo IDs. This includes attributes from the generic namespace but introduces stricter requirements around mandatory attributes. For example, the portrait attribute (photo) is mandatory for a photo ID. Issuers defining credentials that are a photo ID should utilise the Photo ID profile in ISO 23220-4 to ensure maximum interoperability. Where additional attributes are required that are not covered by the Photo ID namespace, these should be included in separate namespaces. Document types that do not include all mandatory attributes required by the Photo ID template should instead use attributes from the generic `org.iso.23220.1` namespace. In addition, where credentials are defined that are similar to a photo ID, issuers should create a custom document type but include the Photo ID namespace. |
| Mobile Driver Licence (mDL) | Where an issuing agency is producing a digital version of a driver licence, it should utilise the `org.iso.18013.5.1.mDL` document type and conform to the `org.iso.18013.5.1` namespace. This is essential to ensure international interoperability. Any attributes outside of that namespace should be included in a separate namespace. In practice, this applies mainly to the New Zealand Transport Agency as the sole issuer of driver licences in New Zealand. However, relying parties will need to verify mDLs issued internationally. |
| Motor Vehicle Registration Certificate (mVRC) | Where an issuing agency is producing a digital version of a motor vehicle certificate or registration, it should utilise the `org.iso.7367.1.mVRC` document type and conform to the `org.iso.7367.1` and `org.iso.23220.1` namespaces. This is essential to ensure international interoperability. Any attributes outside those namespaces should be included in a separate namespace. In practice, this mainly applies to the New Zealand Transport Agency as the issuer of motor vehicle registration certificates in New Zealand. However, relying parties may need to verify mVRCs issued internationally. |
| Mobile International Certificate of Vaccination (MICOV) | The mobile International Certificate of Vaccination is a digital version of the traditional yellow vaccination card, allowing travellers to show verified vaccine records on their phone for border checks or health requirements. Issuing agencies producing a mobile vaccination certificate should utilise the `org.micov.1` document type and conform to at least one of the following namespaces: `org.micov.vtr.1`, `org.micov.attestation.1`, or `org.micov.fhir.1`. This is essential to ensure international interoperability. Any attributes outside these namespaces should be included in a separate namespace. |
| EU Person Identification Data (EU PID) | The EU Personal Identity Data is the core set of verified attributes every EU Digital Identity Wallet must provide. EU Member States will generally be the issuers, so it is unlikely a New Zealand issuer will need to utilise this document type or namespace. However, relying parties that wish to support international interoperability may want to support the EU PID document type (`eu.europa.ec.eudi.pid.1`) and namespace (`eu.europa.ec.eudi.pid.1`) for credential holders using it as identification. While the EU PID has limited legal recognition in New Zealand today, this may evolve through mutual recognition of digital identity services or for use cases without specific legal requirements (for example hotel check-in). Relying parties and verifiers in New Zealand wishing to support the EU PID should refer to the EUDI Wallet Reference Architecture: PID Rulebook. They should prefer the ISO/IEC 18013-5-compliant encoding of PID over the SD-JWT VC-based alternative to align with New Zealand’s mDoc-first approach. |

#### 9.1.2 Internationally established namespace for generic uses (org.iso.23220.1)
The org.iso.23220.1 namespace provides a set of data elements to express personal attributes for describing a natural or legal person. These data elements can be used in combination to create a wide range of credentials utilising common attributes.
These data elements are detailed in Table 2 of ISO/IEC 23220-4.
Credential issuers seeking to create their own document types, should seek to utilise the org.iso.23220.1 namespace and attributes as much as possible. Unless using an existing document type, the issuer should establish their own document type in line with the reverse domain naming convention.
For instance:
The Utopia Tennis and Squash Club wants to establish a digital credential for their membership cards. This is not a credential akin to a photo ID and does not contain a portrait attribute. 
Therefore, they utilise their own document type, attributes from the org.iso.23220.1 namespace, and a custom namespace for attributes specific to this document.
```
doctype: ut.co.tennisandsquash.membership.1

namespace: org.iso.23220.1

		family_name

		given_name

		birth_date

		issuing_authority

		[…]

namespace: ut.co.tennisandsquash.membership.1

		membership_type

  tennis_grade

  squash_grade

  […]
```

#### 9.1.3 Regional, industry, sector or collectively established namespaces
Where common data or attributes exist across a regional, industry, sector or collective grouping, then a common established namespace is preferable to ensure interoperability and remove the risk of duplication.

Some examples include the shared namespace for members of the American Association of Motor Vehicle Administrators (AAMVA) to ensure alignment across US and Canadian jurisdictions for the issuance of American-specific driver licencing attributes.

#### 9.1.4 New Zealand Common Namespace
This reference architecture proposes the following `nz.govt.digital.common.1` namespace and attributes. 

The intention is for this namespace to be used by any issuer in New Zealand to represent commonly used attributes to ensure interoperability within New Zealand and clarify for any international entity wishing to support New Zealand specific attributes.

This namespace uses the recommended reverse domain name format as this namespace will be governed by the Trust Framework Board within the Department of Internal Affairs (who also manage the digital.govt.nz domain)

#### 9.1.5 Specific Namespaces
Finally, there will be a need for specific namespaces to be created for sets of attributes where none of the options above apply. This might be in the instance of where an issuer is the only issuer of that specific information, where the issuer is tightly coupled with the relying parties, where the attributes are only relevant to the issuer’s own service, or where interoperability across issuers is less of a consideration.

For instance, a public hospital issues patient visitation passes as an ISO/IEC 23220 compliant mobile document. It includes attributes unique to the hospital like ward code, bed number, visitor category, temporary access token, and internal case reference. These fields are created for the hospital’s own operational system. They have no national model, no clinical interoperability requirement, they do not map readily against other hospitals, and no other issuer would ever need to interpret them. In this case it would be appropriate to define a custom namespace with custom attributes.

This also applies where a specific namespace is used to extend another namespace as noted above. For instance, where the Government of Testopia issues photo IDs for its citizens it uses the Photo ID template for most of the attributes but includes an additional specific namespace with custom attributes to include the attributes unique to it as an issuer.

### 9.2 Data Models, Types, and Attributes

#### 9.2.1 Photo IDs derived from ICAO 9303 compliant ePassports and eIDs
When a photo ID is derived from an ICAO 9303 compliant ePassport (or ICAO 9303 compliant eID), the original document data can be represented using the ISO/IEC 23220-4 Photo ID template. This allows a relying party to independently verify the underlying information issued by the authority that produced the source credential from which the new credential was derived.

Issuers intending to derive credentials from these documents should include the underlying ICAO data in the relevant attribute fields of the derived credential as defined in ISO/IEC 23220-4 Annex C.

This enables two distinct sources of trust for a relying party:
-  accreditation under the DISTF ensures confirmation that the attributes have been correctly derived from the source credential and are accurately represented; and
-  inclusion of the underlying ICAO data which allows for the verification of the authenticity of the source credential and is particularly useful where DISTF accreditation may be less relevant (for example in another jurisdiction).

>[!WARNING]
>Presentation of the machine-readable zone (MRZ) and security object data (SOD) attributes allows verification of the original issuer, but releases all data contained in those documents as selective disclosure is not supported. Users and relying parties should consider whether separate verification of the underlying document is strictly necessary, especially where Trust Framework accreditation may already provide assurance that the attributes are correctly derived.

>[!TIP]
>As an example, the Bank of Testopia issues a “Bank ID” digital credential derived from the Government of Testopia ICAO 9303 compliant passport. The Bank ID includes the MRZ and SOD data from the passport as attributes alongside the full set of derived attributes for a photo ID. A relying party can trust the Bank ID by verifying the credential’s mobile security object (MSO) against the Bank of Testopia’s public key and because the bank’s credential is accredited under the Trust Framework. If the relying party requires further assurance, for example because they do not recognise New Zealand’s Trust Framework, they could verify the SOD against the Government of Testopia passport public key from the ICAO master list.

#### 9.2.2 Sex, Gender, Ethnicity and other sensitive attributes
Certain attributes are inherently sensitive, or risk stigmatisation, and issuers should carefully consider whether the utility of a user having these attributes included within a credential outweighs the risk of collecting and including these attributes. Given that sex, gender, and ethnicity are almost always self-asserted attributes there is arguably less utility in their inclusion in a credential of these attributes.

Where an issuer is considering the inclusion of sex or gender as an attribute, they should consult Stats NZ’s guide to determining if and how to collect and output gender, sex, and variations of sex characteristics data.

Equally, ethnicity is generally always self-asserted and there are few use cases where it may be required in a credential. In other jurisdictions, the inclusion of an ethnicity attribute is prohibited. Careful consideration should be given to the inclusion of ethnicity.

Where an issuer determines that the sex and/or gender attribute(s) should be included, this reference architecture provides guidance on how to include those.

An ethnicity attribute is not defined in the 23220 namespace and is not yet defined as a mandated standard. When the mandated standard is established, this will be reflected in the proposed common New Zealand namespace. 

#### 9.2.3 Single Names
Under the mDL (`org.iso.18013.5.1`) and Photo ID (`org.iso.23220.photoID.1`) namespaces both given_name and family_name are mandatory attributes. However, New Zealand permits a person having one name.

To align with the namespace requirements and New Zealand law, issuers should:
-  record the single name in the family_name attribute
-  enter `*` in the given_name attribute

Relying parties and verifiers that encounter `*` in the given_name attribute should treat it as null and disregard it when interpreting the person’s name. 

Technically, a blank or empty string could be used for the given_name attribute. However, this is not recommended, as it may be misinterpreted as human error, an encoding issue, or ambiguity. Using “*” avoids these risks and provides a clear and consistent signal to relying parties and verifiers.

#### 9.2.4 Document Types
The ISO/IEC 23220 series requires each credential to specify a document type (doctype). While the standard does not prescribe a specific format, it recommends the following convention to reduce the risk of collisions: `[Reverse Domain].[Domain-Specific Extension]`

A version number is also recommended in case the document type changes over time. Therefore the following convention should be used: `[Reverse Domain].[Domain-Specific Extension].[Version Number]`

When designing document types, broader definitions are preferable to narrow ones. A single document type should cover a range of use cases, with attributes used to distinguish specific privileges, classes, or endorsements. For example:
-  instead of separate document types from the same issuer (or class of issuers) for a boat licence, jet ski licence, and hovercraft licence, a single marine licence document type should be used with attributes to define endorsements.
-  similarly, diplomatic photo ID and standard photo ID should be expressed as one document type (for example photoID), with a boolean attribute such as diplomatic_status

This approach promotes interoperability, reduces unnecessary variation, and supports future extensibility.

#### 9.2.5 Unicode/Latin1
Text string attributes in an mDoc may be encoded using either Unicode or the Latin-1 character set (ISO/IEC 8859-1). Some attributes, particularly names, allow both formats to be included. For example, the given name attribute in the photo ID profile includes:
-  given_name (Unicode)
-  given_name_latin1 (Latin-1)

Issuers should provide both encodings wherever possible. This supports international interoperability by ensuring names are readable in the Latin alphabet while still allowing representation in native scripts, such as Greek, Japanese, Korean, or Arabic. The mobile driver licence namespace, for instance, requires both encodings for this precise reason.

Including Unicode is especially important in the New Zealand context, as it enables the correct use of macrons in Māori names.

Where the Unicode and Latin-1 encodings are identical, both should still be included for consistency.

Verifiers may decide whether to request and display the Unicode version, the Latin-1 version, or both. Each approach has trade-offs:
-  Latin-1 only ensures basic readability but does not support macrons in Māori names
-  Unicode only supports macrons and native scripts but may render names in non-Latin scripts that a relying party cannot read
-  Displaying both improves accessibility but may introduce duplication

The displaying both approach should therefore be chosen based on the context of use and the needs of the relying party.

#### 9.2.6 Age Over NN
>[!NOTE]
>Refer to [ISO/IEC 18013-5: 9.2.5 Age attestation: nearest "true" attestation above request](https://www.iso.org/standard/69084.html) for context on `age_over_NN` attributes.

It is recommended that New Zealand issuers include, at a minimum, the following age_over_NN attributes:

 Attribute | Examples of What It Allows |
|-----------|-----------------------------|
| `age_over_16` | Apply for a driver licence, work full-time, leave school, join a trade union, apply for a passport, apply for some government assistance |
| `age_over_18` | Vote, purchase most age-restricted goods, enter legal contracts |
| `age_over_20` | Enter certain venues |
| `age_over_21` | Included to support interoperability with the United States |
| `age_over_25` | Rent a car, other qualifications |
| `age_over_65` | Apply for superannuation, eligible for concessions |

#### 9.2.7 Portrait Image
_Guidance adopted from [AAMVA mDL Implementation Guidelines](https://www.aamva.org/assets/best-practices,-guides,-standards,-manuals,-whitepapers/mobile-driver-s-license-implementation-guidelines-1-2)_

The portrait image is the primary means by which an mDL, Photo ID, or other photo-enabled credential is matched to the person presenting the credential in an attended transaction. The portrait image therefore needs to be of suitable quality for this purpose.

The mDL and Photo ID profiles require the portrait to comply with Annex D of ISO/IEC 18013-2:2020, which in turn requires the portrait image to be at least 192 pixels wide and 240 pixels high. In addition, ISO/IEC 18013-2 requires portrait images intended for automated face recognition to comply with ISO/IEC 19794-5, which among other requirements requires 90 pixels between the centres of the eyes. However, it should be noted that these requirements were created in the context of storage on a physical card and in machine-readable formats with limited storage capacity compared to an mDL.

It would therefore be possible to include a portrait image of much higher resolution in an mDL. Arguments for going this route include higher accuracy when using the portrait image as a probe image in 1:n biometric searching and making it easier for a human to compare the portrait image with the mDL holder. 

Arguments against going this route include the following:
-  A larger portrait image can negatively affect presentation transaction times.
-  A better-quality portrait image could arguably be less privacy preserving than a smaller portrait image.
-  The primary purpose of the portrait image is a 1:1 match with the mDL holder. If this match is performed biometrically, the smaller portrait size should be sufficient.

Issuers should carefully consider all these points when deciding on a portrait image size. 

It is recommended that issuers opt for a smaller rather than for a larger portrait image.

### 9.3 Other Consideration
#### 9.3.1 Stats NZ’s mandated standards
Data standards establish a common approach to the collection, management, and use of data. Mandated data standards must be used by New Zealand’s Public Service Departments and Departmental Agencies when collecting, publishing, or sharing data on a particular topic.

The Government Chief Data Steward (GCDS) has the power to make standards mandatory. This does not mean that agencies must collect information on a mandated topic. It means that, if they collect, publish, or share information on a topic related to a mandated standard, they must use the standard.

The authority to set mandated standards for use across government lies with the Government Chief Data Steward (GCDS). These standards only apply to the public sector.

The following guidance provides recommendations for public sector organisations seeking to adhere to, or for private sector organisations seeking to align to, the mandated standards.

| Category | Standard | Details / Compliance Notes |
|--------|----------|-----------------------------|
| Date of Birth | ISO 8601-1 | Both the mandated standard and the ISO 23220 series require date of birth to be formatted using ISO 8601. Using the `date_of_birth` attribute in the ISO 23220 namespace therefore satisfies the mandated standard. |
| Person Name | NZ Government OASIS CIQ Name Profile | Compliance with both the mandated standard and the ISO 23220 namespace can be achieved by: using the `family_name` attribute for the family name or primary identifier; using the `given_name` attribute for all first names, other names, or secondary identifiers. Guidance is provided at 9.2.3 Single Names where a user has only one name. |
| Street Address | ISO 19160-1 | To be drafted. |
| Gender and Sex | Stats NZ Data Standard for Gender, Sex, and Variations of Sex Characteristics | Under the mandated standard, sex is a flat classification with two categories: 1 = Male / Tāne, 2 = Female / Wahine. Using the `sex` attribute in the ISO 23220 namespace therefore satisfies the mandated standard. |

>[!NOTE]
>Gender is not defined in the ISO 23220 series. It is therefore included in the proposed `nz.govt.digital.common.1` namespace, which aligns with Stats NZ's mandated standard.

**Future mandated data standards**
Stats NZ is currently undertaking work on mandated data standards for the following attributes. These attributes will be included in future versions of the nz.govt.digital.common.1 namespace once published:
•	Ethnicity
•	Iwi Affiliation
•	Māori descent
•	Māori business

For more information about Stats NZ’s mandated data standards see: [Stats NZ: Mandated Data Standards](https://data.govt.nz/toolkit/data-standards/mandated-data-standards)

[<< 8. Use Cases](8-USECASES.md) | **9. Data Model** | [Annex 1. Abbreviations >>](annexes/1-ABBREVIATIONS.md)
