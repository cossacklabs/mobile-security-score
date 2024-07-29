# 4. Authentication and Session Management

Mobile app authentication can be assessed from two perspectives: local authentication, which includes biometric checks performed on the device, and remote authentication, which occurs on the backend. CL MSS focuses on mobile application security, so it doesn't cover authentication and session management on the backend side as good as OWASP ASVS does. CL MSS covers client-server communication and configuration details, addressing common issues.

This section also highlights general application security recommendations for authentication and session management. These recommendations may apply even if the app doesn't rely on a remote server for authentication. Mobile applications processing highly sensitive data or adhering to a specific threat model may require an additional level of protection for authentication. Therefore, the checklist includes not only L2 requirements but also a series of Multi-Factor Authentication (MFA) and related recommendations.

## General	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 4.1 |	Password is never stored on the client side unless explicitly required for app functionality.	| L1 |
| 4.2 |	Session data and cached user sensitive data is cleaned after user logs out or when the session expires. It may include data cached in memory, in Keychain, network and Webview cache, etc.	| L1 |
| 4.3 |	Users can view a list of devices with active session, contextual information (IP address, location, etc.), and to block specific devices.	| L2 |
| 4.4 |	The app informs the user of sensitive activities with their account, e.g. on password change.	| L2 |
| 4.5 |	Security controls of reset password flow should be as strong as for login flow authentication process.	| L2 |
| 4.6 |	Sensitive transactions are replay resistant.	| L1 |

## Remote authentication	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 4.7 |	If the app provides users access to a remote service, some form of authentication is performed at the remote endpoint.	| L1 |
| 4.8 |	When using password as authentication factor, a password policy should exist, and remote endoint should enforce it.	| L1 |
| 4.9 |	Passwords are hashed before being sent over the network even if the connection is protected with TLS.	| L2 |
| 4.10 |	Insecure channel, e.g. SMS, is never used as a main authentication factor.	| L1 |
| 4.11 |	If stateful session management is used, the remote endpoint uses randomly generated session identifiers to authenticate client requests without sending the user's credentials.	| L1 |
| 4.12 |	If stateless token-based authentication is used, the server provides a token that has been signed using a secure algorithm.	| L1 |
| 4.13 |	Sensitive data is not included into the payload of authentication token.	| L1 |
| 4.14 |	The remote endpoint implements a mechanism to protect against the submission of credentials an excessive number of times.	| L1 |
| 4.15 |	Sessions are invalidated at the remote endpoint after a predefined period of inactivity and access tokens expire.	| L1 |
| 4.16 |	Session tokens, refresh tokens, OTPs, and other types of authentication tokens have predefined reasonable expirations time.	| L2 |
| 4.17 |	The remote endpoint terminates the existing session when the user logs out.	| L1 |

## Local authentication	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 4.18 |	The app implements applications-level passcode/password to secure access to locally stored data.	| L2 |
| 4.19 |	Application-level passcode/password, if any, is involved in the encryption scheme of store sensitive data it is meant to protect.	| L2 |
| 4.20 |	A passcode/password policy exists and weak passcodes/passwords are not allowed.	| L1 |
| 4.21 |	Biometric authentication, if any, is not event-bound (i.e. using an API that simply returns "true" or "false"). Instead, it is based on unlocking the keychain/keystore.	| L2 |
| 4.22 |	The app detects if system-level biometry settings are updated (i.e. new fingerprint added) and executes a fallback action (i.e. requests passcode).	| L2 |
| 4.23 |	The app implements a mechanism to protect against the submission of credentials an excessive number of times.	| L1 |
| 4.24 |	The app’s local storage should be wiped after an excessive number of failed authentication attempts.	| L2 |

## Multifactor and step-up authentication	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 4.25 |	A second factor of authentication exists and the 2FA requirement is consistently enforced.	| L2 |
| 4.26 |	If the app authenticates to a remote endpoint, all authentication factors should be enforced by a remote endpoint.	| L2 |
| 4.27 |	Sensitive transactions require step-up authentication.	| L2 |
| 4.28 |	If sensitive transaction is performed at the remote endpoint, step-up authentication should be enforced at the remote endpoint.	| L2 |
| 4.29 |	The app uses passwordless authentication, e.g. WebAuthen, as one of authentication factors if app's architecture allows it.	| L2 |
