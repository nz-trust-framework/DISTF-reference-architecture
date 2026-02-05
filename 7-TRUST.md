# New Zealand Digital Identity Services Trust Framework

![DISTF Reference Architecture](media/reference-architecture.jpg)

>[!CAUTION]
>You are viewing the Reference Architecture **Exposure Draft**. It is intended for consultation only and does not represent government policy or endorsement by the Trust Framework Board.

## 7. Trust Model

The purpose of the Trust Model is to define how the services enable trust in the identity and verifiable credential ecosystem.  

>[!NOTE]
>This trust model discusses broader authentication and binding. This broader usage shouldn't be confused with the narrower and more specific definitions of authentication service and binding service detailed in [5.0 Ecosystem Roles]().

### 7.1 Scope
![](/media/trust-scope.png)

The scope of the Trust Model is based on the services defined under the DISTF. Each of these services plays a role in the management of verifiable credentials and identity. Some of these roles are:
-	Issuance
-	Currency/Updating
-	Verification 
-	Revocation of Verifiable Credentials and the identity attested by them
-	Managing the data at rest
-	Protecting and managing the cryptographic keys that support authentication and binding; and
-	Authentication and authorisation of their services and functions that protect the perimeter of their system access and controls to their systems.

This section defines the overall architecture in-scope of the Trust Model that includes the services and functions that enable the overall capability to deliver trusted verifiable credentials.

