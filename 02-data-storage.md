# 2. Data Storage and Privacy

Every security assessment includes an evaluation of secure data storage and protection measures for data-at-rest. Mobile device operating systems and specific development frameworks offer various tools for secure data storage. The role of a security engineer is to determine the optimal secure configuration of system-provided storage that can be used within the app. This choice depends on the sensitivity of assets, desired usability and the nature of the data, recognising that security controls for small pieces of data differ from those for large files.

Developing a mobile application for multiple platforms, such as iOS and Android, should consider variations in the implementation of local data storage for different operating systems. Security engineers must ensure that implementations on both platforms are equally secure. Otherwise, attackers may target and exploit the weaker one.

## Data storage business logic	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 2.1 |	The app follows data minimization principle and stores minimum amount of data that is required for app functionality by design. | L1 |
| 2.2 |	No sensitive data, e.g. user credentials, private keys or other secrets are hardcoded into the app. |	L1 |
| 2.3 |	The app keeps sensitive data in memory no longer than it is required for app's functionality. |	L2 |
| 2.4 |	The app doesn't store sensitive data in a local storage unless it is required for app's functionality. | L2 |
| 2.5 |	If sensitive data needs to be stored in the local storage, the app keeps it in local storage no longer than it is required for app's functionality. | L2 |
| 2.6 |	Sensitive data should not be stored in external storage unless it is required for app specific features. | L2 |
| 2.7 |	The app clears sensitive data on app reinstall unless it is required for anti-abuse mechanisms. | L1 |

## System-provided storage	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 2.8 |	Sensitive data, e.g. user credentials and access tokens, is stored encrypted in an internal storage, e.g. iOS Keychain or Android Encrypted Shared Preferences. | L1 | 
| 2.9 |	If encryption keys are not meant to leave the device, they should be generated in a hardware-backed cryptographic storage, e.g. Android hardware-backed Keystore or iOS Secure Enclave.	| L2 |
| 2.10 | If the app doesn't support outdated devices, do not allow using alternatives to hardware-backed encryption, e.g. verify that Android Keystore uses hardware-backed encryption and perform key attestation. |	L2 |
| 2.11 | When storing highly sensitive data, the app should use an advanced level of encryption, encrypting the data with system-provided encryption and a 3rd-party encryption library. |	L2 |
| 2.12 | The app uses the most strict access policy for local data and keys storages as app functionality allows, such as requiring the user to set a device passcode. | L2 |

## Device and application-level configuration	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 2.13 | Sensitive data is not included in application backups. | L2 |
| 2.14 | Sensitive data is not written to application logs. | L1 |
| 2.15 | Keyboard cache is disabled on fields with sensitive data, e.g. passwords. | L1 |
| 2.16 | Copying text from fields with sensitive data, e.g. password fields, is disabled except it's required by app funcationality. | L1 |
