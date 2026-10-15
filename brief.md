
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


## Cybersecurity


## Data

## Misconception in My Track

## Open Question
