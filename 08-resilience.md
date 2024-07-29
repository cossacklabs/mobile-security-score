# 8. Resilience Against Reverse Engineering and Tampering

Resilience security controls can prevent attempts at reverse engineering and tampering, whether an attacker has physical access to the device or a comprehensive remote attack has compromised it.

The mobile app can implement platform-specific measures or rely on vendor-provided mechanisms for device and app attestation. Be cautious when writing custom checks for device and app integrity. These checks might give false positives when the OS version is updated or when running on devices from less popular vendors.

Obfuscation is another defense-in-depth security control that makes reverse engineering more difficult. However, can easily become a never-ending task. Implementing obfuscation security controls can happen at multiple levels within the app, and maintaining them can become very complex and time-consuming. A balanced approach is needed to keep the source code both readable and debuggable.

When resilience security controls are implemented, the mobile application should respond to detected security events either by closing down, wiping locally stored data, displaying a warning to the user, or sending an analytics event to a remote endpoint. These analytics events can contribute to a fraud score for the user or device, preventing them from performing sensitive actions within the app.

## Runtime Application Self-Protection	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 8.1 |	The app detects, and responds to, the presence of a rooted or jailbroken device either by alerting the user or terminating the app.	| R1 |
| 8.2 |	The app prevents debugging and/or detects, and responds to, a debugger being attached. All available debugging protocols must be covered.	| R1 |
| 8.3 |	The app detects, and responds to, tampering with executable files and critical data within its own sandbox.	| R1 |
| 8.4 |	The app detects, and responds to, the presence of widely used reverse engineering tools and frameworks on the device.	| R1 |
| 8.5 |	The app detects, and responds to, being run in an emulator.	| R1 |
| 8.6 |	The app detects, and responds to, tampering the code and data in its own memory space.	| R1 |
| 8.7 |	The detection mechanisms trigger responses of different types, including delayed and stealthy responses.	| R2 |
| 8.8 |	The app performs device attestation using vendor-provided tools, e.g. Google Play Integrity API.	| R1 |
| 8.9 |	The app performs application attestation using vendor-provided tools, e.g. Google Play Integrity API and Apple App Attest.	| R1 |
| 8.10 |	The app verifies application signature data.	| R1 |
| 8.11 |	The app performs integrity checks for local executables and files in application bundle by rather encrypting them or verifying the signature.	| R2 |

## Obfuscation	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 8.12 |	Free-to-use vendor-provided obfuscation tools, e.g. Android Proguard, are in applied with as strong obfuscation rules as app architecture allows.	| R1 |
| 8.13 |	In-app static secrets, e.g. API-keys and client IDs, are obfuscated in the sources code. Static code analysis do not reveal hardcoded secrets.	| R1 |
| 8.14 |	In-app static strings are obfuscated. Static code analysis do not reveal meaningful hardcoded strings.	| R2 |
| 8.15 |	Methods that are associated with sensitive actions or data, have their names obfuscated.	| R1 |
| 8.16 |	All methods names are obfuscated throughout the application, as much as the app architecture allows.	| R1 |
| 8.17 |	If obfuscation goal is to obscure internal app logic or internal logic of a particular algorithm, control flow flattening is applied.	| R2 |
| 8.18 |	When using local key-value storage, key values should have obfuscated names.	| R2 |
| 8.19 |	Sensitive executable files or important parts of algorithm are obfuscated on the file level. Trivial static analysis does not reveal important code.	| R2 |
| 8.20 |	Obfuscation should be robust against manual and automated de-obfuscation methods, considering currently published research. The effectiveness of the obfuscation scheme must be verified through manual testing.	| R2 |

## Anti-fraud and monitoring	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 8.21 |	Security events related to the app's resilience mechanisms, such as root or jailbreak detection events, are tracked and monitored in the app's analytics.	| R1 |
| 8.22 |	Security events related to sensitive data, like failed authentication attempts, are tracked and monitored in app analytics.	| R1 |
| 8.23 |	The app implements a 'device binding' functionality using a device fingerprint derived from multiple properties unique to the device.	| R2 |
