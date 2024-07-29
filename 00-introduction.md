# CL MSS (Cossack Labs Mobile Security Score)
CL MSS (Cossack Labs Mobile Security Score) is an actionable mobile security verification framework for product security, security assessments, SSDLC, and measuring security posture.

CL MSS is an extension of an industry standard [OWASP MASVS](https://mas.owasp.org/MASVS/).

We developed CL MSS to address specific risks and threats for mobile apps with increased security risk exposure. The framework covers typical security challenges of mobile applications, with focus on secure mobile app architecture, practical cryptography implementation, and data privacy.

## CL MSS goals are:

- to provide guidance for security engineers, quality assurance engineers, software developers, and architects on how to improve the security of mobile applications;
- to enumerate the most commonly used security controls and scenarios where they are applicable;
- to make the security posture of the mobile app measurable and its progress trackable over time.

## Contents of CL MSS

The CL MSS has eight core sections, aligning with MASVS. The additional customisable section #9 is designed for project-specific needs. 

CL MSS requirements can be tailored to project or assessment needs. Not all requirements are relevant to every mobile application. Some requirements may be marked as "not applicable", based on the specific internal logic and business goals. If the app has unique security requirements not listed in CL MSS, they can be added to the #9 section and counted toward the mobile security score of the app.

This guide breaks down security requirements into several levels based on how sensitive the app's data is and its threat model. Similar to OWASP MASVS, the multi-layered approach is represented by the following levels of requirements: 

- L1 — Basic Security Level
- L2 — Advanced Security Level or Defence-in-Depth
- R1 — Basic Resilience Level
- R2 — Advanced Resilience Level

L1 requirements describe the basics of mobile application security that are typically relevant to all mobile applications, even if they do not handle sensitive data. We recommend fulfilling at least 80% of L1 requirements (the more - the better) before proceeding to L2 and R1. It's a Pareto principle approach: Focusing on the efforts that deliver the most security benefit. The remaining 20% can be worked on in parallel to L2 and R1. Even if some L1 requirements are challenging to cover, L2 security control can address the same security risk.

Advanced or defense-in-depth security controls are listed in the L2 requirements. They are relevant for applications handling highly sensitive data, for example, private messaging, e-commerce or social media apps. Implementing these security controls might be challenging. They require complex architectural decisions from software developers. Implementing these security controls may involve several teams: mobile, backend and DevOps engineers.

The R1 level describes basic requirements for resilience against reverse engineering and tampering. The core goal is to detect compromised, rooted, or jailbroken devices and make reverse engineering and tampering more difficult.

R2 represents advanced security controls for resilience. These controls are typically sophisticated and challenging to implement, bringing their own reliability risks. Therefore, R2 requirements are usually implemented only when risk assessment and threat modeling explicitly call for that level of protection.

Resilience requirements can be implemented on top of either L1 or L1+L2. For example, gaming mobile applications typically do not process highly sensitive data, but code modification for cheating is a significant threat. A combination of L1 and R-level requirements can be a good fit for a mobile game. Mobile apps with highly sensitive data, like those in finance, banking, or healthcare, require stricter security measures. This means implementing a defence-in-depth protection: L1, L2 and R-level requirements.

## How to use CL MSS

**Pre-security assessment phase**

1. Download CL MSS sheet. 
2. Conduct risk assessment and threat modelling. 
    * If necessary, perform the pre-assessment tailoring in Chapter 9, based on identified risks and threats: add security requirements relevant for a particular product, its domain, local regulations, etc, that are not listed in 8 core sections of CL MSS.       

**Assessment phase**

For each chapter: 

3. Identify the application components; 
4. Determine if the requirement is met; 
5. Based on the existing application components and identified risks and threats, mark each item as:
    * Yes (the requirement is met) 
    * No (the requirement is not met) 
    * N/A (not applicable or risk acceptable based on the specific internal logic and business goals)

**Post-assessment phase**

6. Record the status: save values showing the percentage of satisfied requirements by levels and by sections. 
7. Address identified issues 
8. Update the status accordingly: if the identified issue is fixed, update the requirement status from “No” to “Yes”.
9. Compare updated status with the previous one, monitor changes over time to identify areas that need more attention.


Note: When calculating the security score for the advanced level, be sure to account for the basic level. This means you should add the number of satisfied L1 and L2 requirements and divide it by the total number of L1 and L2 requirements.