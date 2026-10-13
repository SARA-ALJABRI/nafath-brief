Version: NAFATH-V1
Track: Software
## Overview
A national single sign-on service allows citizens to access multiple government services using one account. It must provide a simple user experience while protecting identities and personal data. Software standards define secure sign-in and access to services. AI can help identify suspicious login activity, but it requires testing and monitoring. The mobile application should request only necessary permissions. Network protections can improve privacy, while phishing-resistant authentication helps prevent account theft. Data protection requirements must also be considered. These areas work together to make the service reliable, secure, and trustworthy.
## Software
OAuth 2.0 is an authorization framework that allows applications to obtain limited access to resources. It does not, by itself, define a standard way to authenticate users. OpenID Connect adds an identity layer to OAuth 2.0 and provides an ID Token that the client can validate. For NAFATH-V1, OpenID Connect should support user sign-in, while OAuth access tokens should be used for authorized API requests.
Resource: OpenID Connect Core 1.0
[https://openid.net/specs/openid-connect-core-1_0.html](https://openid.net/specs/openid-connect-core-1_0.html)
## AI
AI can help detect unusual login patterns, but it should not be trusted without evaluation. The NIST AI Risk Management Framework provides four functions: Govern, Map, Measure, and Manage. The project team should define responsibilities, assess risks, test model accuracy, protect personal data, and monitor performance over time. Suspicious activity alerts should support security teams rather than automatically making every decision.
Resource: NIST AI Risk Management Framework
[https://airc.nist.gov/airmf-resources/airmf/5-sec-core/](https://airc.nist.gov/airmf-resources/airmf/5-sec-core/)
## Mobile
Android runtime permissions control access to certain sensitive device features. A government login application should request only permissions necessary for its features and explain why each permission is needed. Users should still be able to sign in when optional permissions are denied. For example, a basic login function should not require access to contacts or location without a clear and justified need.
Resource: Android runtime permissions
[https://developer.android.com/training/permissions/requesting](https://developer.android.com/training/permissions/requesting)
## Networking
DNS over HTTPS (DoH) sends DNS queries through HTTPS, helping protect domain lookups from observation or modification while in transit. This can improve privacy when citizens connect to government services. However, DoH does not protect every part of an internet connection, prevent all tracking, or replace HTTPS on websites. The service must use additional network and application security controls.
Resource: RFC 8484 — DNS Queries over HTTPS
[https://www.rfc-editor.org/rfc/rfc8484.html](https://www.rfc-editor.org/rfc/rfc8484.html)
## Cybersecurity
Phishing-resistant authentication helps prevent attackers from stealing usable login credentials through fake websites. Passkeys and other public-key methods, such as FIDO2/WebAuthn, can bind authentication to the legitimate service. Passwords and manually entered verification codes can still be exposed to phishing. NAFATH-V1 should consider phishing-resistant sign-in and provide a secure account-recovery process.
Resource: NIST Digital Identity Guidelines
[https://pages.nist.gov/800-63-4/sp800-63b.html](https://pages.nist.gov/800-63-4/sp800-63b.html)
## Data
NAFATH-V1 must consider Oman's Personal Data Protection Law and its applicable executive regulations. The authority should determine the lawful basis for processing personal data, explain how information is used, collect only necessary data, and protect it against unauthorized access. It should also confirm applicable requirements for consent, sensitive data, retention, data-subject rights, and transfers before launch.
Resource: Executive Regulations of the Personal Data Protection Law
[https://www.mtcit.gov.om/library-3/legislations-policies-8/regulations-72/executive-regulations-of-the-personal-data-protection-law-1035](https://www.mtcit.gov.om/library-3/legislations-policies-8/regulations-72/executive-regulations-of-the-personal-data-protection-law-1035)
## Misconception in My Track
A common misconception is that OAuth 2.0 alone is a complete login protocol. OAuth 2.0 primarily handles authorization, so an access token should not automatically be treated as proof of a user's identity. OpenID Connect adds a standard authentication layer and an ID Token for the client to validate. Understanding this distinction helps prevent incorrect authentication designs.
Resource: OpenID Connect Core 1.0
[https://openid.net/specs/openid-connect-core-1_0.html](https://openid.net/specs/openid-connect-core-1_0.html)
## Open Question
Which OpenID Connect flow and client architecture would best support both the public website and Android application while keeping tokens secure and making account recovery accessible to citizens?
