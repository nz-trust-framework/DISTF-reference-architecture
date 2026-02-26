# Annex 3: New Zealand Common Namespace

This reference architecture proposes the following `nz.govt.digital.common.1` namespace and attributes. 

The intention is for this namespace to be used by any issuer in New Zealand to represent commonly used attributes to ensure interoperability within New Zealand and clarify for any international entity wishing to support New Zealand specific attributes.

This namespace uses the recommended reverse domain name format as this namespace will be governed by the Trust Framework Board within the Government Chief Digital officer role (who also manage the digital.govt.nz domain)

This namespace can be used in any document type.

## `nz.govt.digital.common.1` namespace

| Data Element | Identifier | Description | Encoding* |
|--------------|------------|-------------|----------|
| Preferred Family Name | preferred_family_name | The preferred last name, surname, or primary identifier of the holder where this differs from the official or `family_name` attribute. | **tstr** |
|  | preferred_family_name_latin1 | The preferred last name, surname, or primary identifier of the holder where this differs from the official or `family_name` attribute, encoded in Latin1 characters. | **tstr** |
| Preferred Given Name | preferred_given_name | The preferred first name(s), other name(s), or secondary identifier of the holder where this differs from the official or `given_name` attribute. | **tstr** |
|  | preferred_given_name_latin1 | The preferred first name(s), other name(s), or secondary identifier of the holder where this differs from the official or `given_name` attribute, encoded in Latin1 characters. | **tstr** |
| Gender† | gender | Gender refers to a person’s social and personal identity as male, female, or another gender or genders that may be non-binary. It may include gender identity and gender expression. A person’s gender may differ from the sex recorded at birth and from what is shown on current legal documents. Gender may change over time, and some people may not identify with any gender. Classification is self-defined. | **uint** 1 = Male / Tāne; 2 = Female / Wahine; 3 = Another gender / He ira kē anō.|

\* refer [ISO/IEC 23220-2: Data objects and encoding rules for generic eID systems, 6.2 Data format and encoding rules](https://www.iso.org/standard/86782.html)

† refer [9.2.2 Sex, Gender, Ethnicity and other sensitive attributes](../9-DATA.md#922-sex-gender-ethnicity-and-other-sensitive-attributes)

The inclusion of a middle name attribute is deliberately excluded to ensure alignment with other relevant standards (for instance ICAO 9303), the New Zealand mandated data standards, and technology systems already in use that focus on two-name structures.

## Future Attributes

-  **Address**: Address is defined in New Zealand against ISO 19160-1, which doesn’t map neatly against the 23220 namespace attributes. Therefore, there may be utility in mapping the existing work into the New Zealand common namespace.

-  **Ethnicity**: Not currently defined but will be implemented following Stats NZ’s development of these mandated data standards.

-  **Iwi Affiliation**: Not currently defined but will be implemented following Stats NZ’s development of these mandated data standards.

-  **Māori descent**: Not currently defined but will be implemented following Stats NZ’s development of these mandated data standards.

-  **Māori business**: Not currently defined but will be implemented following Stats NZ’s development of these mandated data standards.
