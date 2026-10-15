
Version: NAFATH-V1
Track: Cybersecurity

## Overview
A national digital identity service must provide secure, interoperable access to government platforms through web and mobile channels. Software architecture should distinguish OpenID Connect for identity authentication from OAuth 2.0 for delegated resource access, ensuring correct token handling and trust boundaries. AI-based anomaly detection may support suspicious-login monitoring, but requires risk assessment, validation, human oversight, and protection against unfair decisions. Android runtime permissions should enforce least-privilege access to sensitive device capabilities. DNS over HTTPS can protect DNS queries in transit without replacing end-to-end application security. Strong authentication and effective account recovery are essential to protecting citizen accounts. Finally, data governance must address the collection, storage, processing, and lawful handling of personal information under applicable Omani legislation. Together, these disciplines form a layered security architecture for reliable digital government services.


## Software
OpenID Connect (OIDC) is an identity layer built on OAuth 2.0 that enables applications to verify a user's authentication through an identity provider. It introduces an ID Token containing claims about the authentication event and user identity. For a national digital identity service, OIDC can support consistent sign-in across participating government applications. Implementations must validate token signatures, issuer, audience, and expiry to prevent acceptance of invalid authentication assertions.

Resource: OpenID Connect Core 1.0 - https://openid.net/specs/openid-connect-core-1_0.html

## AI
Artificial intelligence can help a national digital identity service identify unusual login patterns, such as unexpected locations or repeated failed authentication attempts. However, AI-generated alerts may produce false positives and should not automatically determine whether a citizen can access essential services. The NIST AI Risk Management Framework provides four functions—Govern, Map, Measure, and Manage—to support responsible AI deployment. The authority should assess model accuracy, privacy risks, human oversight, and ongoing performance.

Resource: NIST AI Risk Management Framework - https://airc.nist.gov/airmf-resources/airmf/

## Mobile
Android runtime permissions protect sensitive device resources by requiring user approval for certain access requests. A national digital identity application should request permissions only when a specific feature needs them, explain their purpose, and check whether access has been granted. If a citizen denies an optional permission, the application should preserve other available functionality. This approach supports data minimization, user control, and privacy-conscious mobile authentication.

Resource: Request runtime permissions - https://developer.android.com/training/permissions/requesting

## Networking
DNS over HTTPS (DoH), standardized in RFC 8484, transmits DNS queries and responses through encrypted HTTPS connections. This reduces exposure of DNS traffic to interception or modification while in transit. For a national digital identity service, DoH can strengthen the privacy of domain-name resolution. However, it does not encrypt all network traffic or guarantee that a website is trustworthy. Administrators must also consider resolver trust, logging practices, and operational visibility.

Resource: RFC 8484 - DNS Queries over HTTPS - https://www.rfc-editor.org/rfc/rfc8484


## Cybersecurity
Phishing-resistant authentication prevents attackers from reusing authentication credentials captured through fraudulent websites. It relies on cryptographic mechanisms that bind authentication to the legitimate service. FIDO2/WebAuthn authenticators can provide phishing resistance through verifier-name binding. In contrast, passwords combined with SMS codes or manually entered one-time passwords are not phishing-resistant because attackers can relay those codes. A national digital identity authority should prioritize phishing-resistant authentication for sensitive government services and establish secure account recovery procedures.

Resource: NIST SP 800-63B - Authentication and Authenticator Management - https://pages.nist.gov/800-63-4/sp800-63b.html


## Data
Oman's Personal Data Protection Law, issued under Royal Decree 6/2022 and amended by Royal Decree 68/2026, establishes requirements for handling personal information. The 2026 amendments clarify the law's scope, exemptions, consent requirements, and automated processing. A national digital identity authority should classify citizen information, apply appropriate security safeguards, establish lawful processing grounds, and define retention procedures. It must also determine which statutory provisions apply to its government functions rather than assuming every processing activity follows identical requirements.

Resource: Royal Decree 68/2026 - Amendment to the Personal Data Protection Law - https://www.mtcit.gov.om/library-3/legislations-policies-8/laws-75/royal-decree-68-2026-amending-some-provisions-of-the-personal-data-protection-law-1481

## Misconception in My Track
A common misconception in cybersecurity is that enabling any form of multi-factor authentication automatically prevents phishing attacks. This is incorrect because attackers may trick users into entering passwords and one-time codes on fraudulent websites and relay them to the legitimate service. NIST SP 800-63B explains that phishing resistance requires mechanisms such as verifier-name binding, which links authentication to the legitimate service. FIDO2/WebAuthn can provide this protection, whereas manually entered one-time passwords cannot. Therefore, a national digital identity authority should evaluate authentication methods for phishing resistance rather than assuming all MFA methods offer equal protection.

Resource: NIST SP 800-63B - Authentication and Authenticator Management - https://pages.nist.gov/800-63-4/sp800-63b.html

## Open Question
How can a national digital identity authority provide secure and accessible account recovery for citizens who lose their phishing-resistant authenticator without introducing weaker authentication methods that attackers could exploit?
