# 7. Code Quality

The Code Quality section includes recommendations that align with secure coding best practices across various platforms and languages. These include validating input from external sources, securely handling errors and exceptions, and maintaining clean and simple source code.

Proper build and environment configuration helps separate testing data from production data and prevent potential data leaks. Applications are often tested on testing builds and environments. But the production variants sometimes are not verified to ensure they are free from debugging artifacts or testing backdoors.

Using third-party resources introduces the risk of supply chain attacks. Keeping dependencies up to date and using analysis tools to detect known vulnerabilities can help prevent such threats.

## Mobile secure coding	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 7.1 |	The app validates input data (see 7.2 - 7.6) that can be locally executed or affect application behavior, for example, URLs, executable code or files, configuration options, etc. 	| L1 |
| 7.2 |	All user input via UI should be validated before being processed further.	| L2 |
| 7.3 |	All data coming from network sources should be validated and if necessary sanitised.	| L2 |
| 7.4 |	All input from IPC mechanisms such as intents, deeplinks, custom URL schemes, universal links, etc. should be validated and if necessary sanitised.	| L2 |
| 7.5 |	Object deserialization, if any, is implemented using data validation and safe serialization APIs.	| L2 |
| 7.6 |	Input data from external resources is validated before being processed, stored or sent to the remote endpoint.	| L2 |
| 7.7 |	The app catches and handles possible exceptions.	| L1 |
| 7.8 |	The app handles unexpected error messages from network communication, e.g. wrong error codes, poor internet connection etc.	| L1 |
| 7.9 |	The app handles corner cases and unexpected error messages from device hardware, e.g. biometry sensors, hardware-backed encryption modules, NFC reader, etc.	| L2 |
| 7.10 |	The app doesn't expose non-user-friendly error messages to the user.	| L1 |
| 7.11 |	In the app, error handling logic denies access by default.	| L1 |
| 7.12 |	In unmanaged code, memory is allocated, freed and used securely.	| L2 |
| 7.13 |	There are no dead coded. Feature flags are used instead of commenting out the features.	| L2 |
| 7.14 |	The source code doesn't contain misleading or wrong comments.	| L2 |
| 7.15 |	The app doesn't use deprecated APIs.	| L1 |

## Mobile backend secure coding	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 7.16 |	Data coming from the mobile app should be validated and if necessary sanitised.	| L1 |
| 7.17 |	The backend sends generic error messages to the app, potentially with a unique ID which support personnel can use to investigate.	| L2 |
| 7.18 |	Exception handling is used on the backend to account for expected and unexpected error conditions; the backend doesn't reply with stack traces.	| L1 |
| 7.19 |	In the app's backend side, the error handling logic denies access by default.	| L1 |

## Proper production configuration	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 7.20 |	The distributed production app has been built in release mode, with settings appropriate for a release build (e.g. non-debuggable).	| L1 |
| 7.21 |	Debugging symbols have been removed from native binaries.	| L1 |
| 7.22 |	Debugging code and developer assistance code (e.g. test code, backdoors, hidden settings) have been removed. The app does not log verbose errors or debugging messages.	| L1 |
| 7.23 |	Debugging logs or developer assistance logs are removed from the production build to prevent unintentional disclose of application internal logic.	| L1 |
| 7.24 |	Non-production environment data, e.g. URLs, credentials and API-key, is removed from the production app.	| L1 |

## Supply chain	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 7.25 |	Third-party components used by the mobile app, such as libraries and frameworks, are identified.	| L1 |
| 7.26 |	Third-party components should have no known vulnerabilities, unless risks caused by each particular vulnerability was explicitly accepted and documented.	| L1 |
| 7.27 |	Third-party components are regularly checked for known vulnerabilities, e.g. adding a dependency checker into CI/CD pipeline.	| L2 |
| 7.28 |	The app relies on up-to-date third-party libraries.	| L2 |
| 7.29 |	The app relies on well supported libraries that are aligned with platform updates.	| L2 |
| 7.30 |	The app doesn't communicate with insecure or potentially harmful third-party endpoints or services.	| L2 |
| 7.31 |	The app follows coding best practices by using linter at least on each code push to the repository.	| L2 |
| 7.32 |	The application source code is tested with SAST tool on regular basis, for example by adding it to the CI/CD pipeline.	| L2 |
| 7.33 |	The application is tested with DAST tool on regular basis.	| L2 |
| 7.34 |	The app supports MAM/MDM solutions in case its distribution should be controlled, limited and monitored.	| L2 |
| 7.35 |	Security controls have reasonable test coverage.	| L2 |
