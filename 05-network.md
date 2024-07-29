# 5. Network Communication

Mobile operating systems handle many network security configuration tasks. This includes things like supporting the latest TLS versions and validating TLS certificates for remote endpoints. The Network Communication section of CL MSS addresses mobile app network requests settings and customisations to network communication that can be made from the mobile app, such as allowing plaintext HTTP traffic.

This section also covers advanced security controls like TLS certificate pinning and mutual TLS (mTLS). Implementing these controls requires cross-team commitment, complex design decisions, and cooperation.

## Remote configuration	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 5.1 |	Data is encrypted on the network using TLS for all endpoints used by the app.	| L1 |
| 5.2 |	The TLS settings are in line with current best practices, or as close as possible if the mobile operating system does not support the recommended standards.	| L1 |
| 5.3 |	Application backend uses appropriate HTTP security headers.	| L1 |

## Local configuration	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 5.4 |	TLS is used consistently and enforced throughout the app. The app doesn't turn off TLS for any specific domain.	| L1 |
| 5.5 |	The app verifies the X.509 certificate of the remote endpoint when the secure channel is established. Only certificates signed by a trusted CA are accepted.	| L1 |
| 5.6 |	The app handles no internet connection error in a secure manner.	| L1 |

## Communication protection	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 5.7 |	The app either uses its own certificate store, or pins the endpoint certificate or public key, and subsequently does not establish connections with endpoints that offer a different certificate or key, even if signed by a trusted CA.	| L2 |
| 5.8 |	When pinning endpoint certificate or public key, the process of endpoint certificate/private key rotation is defined and application logic is updated accordingly.	| L2 |
| 5.9 |	Mutual TLS mechanism is used for the client and the server to verify identity of each other before establishing a connection.	| L2 |
