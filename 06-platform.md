# 6. Platform Interaction

What makes mobile app security unique is its dependence on multiple factors: the mobile application platform, development frameworks, mobile OS, and device vendor, all at the same time. Inter-process communication can vary between different devices, requiring extra attention and care.

One example of sensitive IPC is the use of WebView. While it is a common application component, it acts as a bridge between web and mobile, introducing web-like attacks to mobile applications.

Different UI components may leak sensitive data, requiring additional security controls to prevent such exposure. These security controls can help prevent accidental data leaks during shoulder surfing, screen sharing, or when the app takes a screenshot for multitasking view.

## Vendor-provided features	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 6.1  |	The app doesn't support OS versions known for critical vulnerabilities.	| L1 |
| 6.2 |	The app supports only two latest major versions of iOS and only three latest major versions of Android.	| L1 |
| 6.3 |	The app only requests the minimum set of permissions necessary.	| L1 |
| 6.4 |	The app is signed and provisioned with a valid certificate, of which the private key is properly protected.	| L1 |
| 6.5 |	For Android, the app doesn't use v1 signature scheme unless it is explicitly required to support old versions of Android.	| L1 |
| 6.6 |	Free security features offered by the toolchain, such as byte-code minification, stack protection, PIE support and automatic reference counting, are activated.	| L1 |
| 6.7 |	The app does not export sensitive functionality or data via custom IPC (intents, deeplinks, etc), unless these mechanisms are properly protected.	| L2 |

## WebViews	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 6.8 |	The app uses more secure alternatives to WebViews when possible, e.g. browser-like tabs or browser apps.	| L1 |
| 6.9 |	JavaScript is disabled in WebViews unless explicitly required.	| L1 |
| 6.10 |	WebViews are configured to allow only the minimum set of protocol handlers required (ideally, only https is supported). Potentially dangerous handlers, such as file, tel and app-id, are disabled.	| L1 |
| 6.11 |	WebViews are allowed to access only a specified list of domains.	| L2 |
| 6.12 |	If native methods of the app are exposed to a WebView, verify that the WebView strictly renders JavaScript contained within the app package. Alternatively, implement security controls to prevent exposure of native methods. | L1 |
| 6.13 |	A WebView's cache, storage, and loaded resources (JavaScript, etc.) should be cleared before the WebView is destroyed.	| L2 |
	
## Secure UI	

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 6.14 |	The app uses masked input fields for passwords, pins and other user secrets.	| L1 |
| 6.15 |	On Android, the app protects itself against screen overlay attacks.	| L2 |
| 6.16 |	On Android, the app protects itself against accessibility feature abuse.	| L2 |
| 6.17 |	Push notifications do not expose sensitive data.	| L1 |
| 6.18 |	Third-party keyboards should not be allowed on fields with sensitive data. A custom keyboard can be used instead of system-provided one, e.g. for fields with PIN, SSN, CVV, etc.	| L2 |
| 6.19 |	The app removes sensitive data from views when moved to the background.	| L2 |
| 6.20 |	Screenshots are not allowed on screens with sensitive data.	| L2 |
| 6.21 |	The app educates the user about the types of personally identifiable information processed, as well as security best practices the user should follow in using the app.	| L1 |
