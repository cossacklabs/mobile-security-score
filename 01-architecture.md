# 1. Architecture and Design

In mature organizations security considerations are tackled at various levels. It all starts with identifying sensitive assets and conducting risk assessments. This focus on security goes all the way down to each individual process. A Secure Software Development Life Cycle (SDLC), including scheduled periodic risk assessment and threat modeling, is expected from mature organisations. Addressing these procedures typically falls outside the scope of standard external security assessments and demands a more thorough examination. Organisations that follow these best practices tend to have more robust security posture.

Privacy regulations have emerged as a prominent topic of discussion in recent years. Both the Apple App Store and Google Play Market regularly update their store policies and guidelines annually to align with global trends. While security engineers cannot offer legal advice, they can recommend application developers to seek legal guidance whenever privacy-related questions arise.

## Risks and Threats

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 1.1 | Data considered sensitive in the context of the mobile app is clearly identified. | L1 |
| 1.2 | Risk assessment, threat modeling and associated countermeasures documentation was created. | L2 |
| 1.3 | There is an established process for revisiting and maintaining risk assessment, threat modeling and associated countermeasures documentation. | L2 |

## Documentation and processes

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 1.4 | Major app components are identified, documented and known to be needed in terms of business logic. | L2 |
| 1.5 | Security is addressed within all parts of the software development lifecycle. | L2 |
| 1.6 | The app has a mechanism for enforcing app updates. | L2 |
| 1.7 | The app notifies security researchers about responsible disclosure policy within security.txt or similar mechanism. | L2 |

## User Privacy

| # | REQUIREMENT | LEVEL |
| - | - | - |
| 1.8	| The app receives user consent before sending user sensitive data to the remote endpoint or storing it locally. | L1 |
| 1.9	| No sensitive data, including PII, is shared with third-parties unless it is required for app's architecture. | L1 |
| 1.10 | The app doesn't allow account enumeration and prevents guessing of existing user accounts.	| L1 |
| 1.11 | Collected and shared PII is listed in data privacy section of app's store page. | L1 |
| 1.12 | Collected and shared PII documentation exists and explicitly specifies purposes of sharing with particular 3rd parties. | L2 |
| 1.13 | Screenshots published on App Store and Play Market don't contain any PII or sensitive data, e.g. names or user emails.	| L1 |
| 1.14 | The app collects PII only if it is required for app's functionality.	| L1 |
| 1.15 | The app complies with privacy laws and regulations. | L1 |
