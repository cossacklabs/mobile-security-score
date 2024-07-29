# 3. Cryptography

The evaluation of cryptographic code in mobile applications typically involves a few steps: ensuring that the application uses suitable cryptographic primitives tailored to its needs, verifying the presence of an adequate key management process, including key exchange (e.g., between the mobile app and the server), and confirming that the overall cryptographic scheme is suitable for its intended purpose and meets security requirements.

## Cryptographic primitives	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 3.1 |	The app doesn't implement non-standard cryptography unless it is a direct goal of the app.	| L1 |
| 3.2 |	Encoding, e.g. with Base64, is not used to protect the data instead of encryption.	| L1 |
| 3.3 |	The app uses modern hash functions, e.g. SHA256 or SHA512 or BLAKE3, instead of weak ones, e.g. MD5.	| L1 |
| 3.4 |	Encryption keys are derived from a secret value or a passphrase using a key derivation functions, e.g. Argon2 or PBKDF2.	| L1 |
| 3.5 |	Key derivation functions should have sufficient parameters (number of rounds, threads, memory cost, etc).	| L1 |
| 3.6 |	For symmetric cryptography, the app uses AEAD encryption algorithms, e.g. AES-GCM, instead of weak ones, e.g. AES-ECB or AES-CBC.	| L1 |
| 3.7 |	Random values for cryptographic operations are generated using cryptographically secure pseudo-random number generator.	| L1 |
| 3.8 |	Nonce, IV and salt should be random and unique for each encrypted or derived value.	| L1 |
| 3.9 |	Cryptographic primitives should be configured with parameters that adhere to industry best practices.	| L1 |
| 3.10 |	Non-trivial cryptographic operations are covered with unit tests.	| L2 |
| 3.11 |	Cryptographic secrets are compared in constant time.	| L2 |

## Key management	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 3.12 |	The app does not rely on symmetric cryptography with hardcoded keys as a sole method of encryption.	| L1 |
| 3.13 |	Each cryptographic key is used for a particular purpose. The same key is not reused for multiple purposes.	| L2 |
| 3.14 |	Private keys are not transferred over the network unless it is required by the app's architecture.	| L1 |
| 3.15 |	If transferring private keys over the network is required for app's architecture, they are not transferred in a plaintext.	| L1 |
| 3.16 |	Symmetric keys are not transferred over the network in a plaintext.	| L1 |
| 3.17 |	The app implements key rotation, expiration, revocation mechanisms.	| L2 |
| 3.18 |	System resources (memory, file descriptors, FFI objects, etc) are correctly managed during cryptographic operations for secrets and keys.	| L2 |
| 3.19 |	Cryptographic secrets are cleared from memory after use, if it is possible for application language and platform.	| L1 |

## Cryptography in business logic	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 3.20 |	For data integrity and authenticity, the app should use digital signature or HMAC instead of simple hash functions (SHA).	| L1 |
| 3.21 |	For data integrity, authenticity and non-repudiation, the app should use digital signature. HMAC can be used for non-repudiation if key exchange algorithm guarantees non-repudiation.	| L2 |
| 3.22 |	The app uses application level encryption for storing or transferring highly sensitive data.	| L2 |
| 3.23 |	For application level encryption, the app uses key derivation algorithm (like Diffie-Hellman Key Exchange) to generate a shared secret without exposing it to the network.	| L2 |
| 3.24 |	The app complies with encryption export and import regulations if distributed outside the U.S. or Canada.	| L2 |
