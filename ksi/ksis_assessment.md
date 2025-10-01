# Human-Readable KSI Assessment

This document lists KSIs in scope with status and brief rationale. See unified_ksi_validations-public.json for machine-readable details.

| KSI | Category | Status | Rationale (public) |
| --- | --- | --- | --- |
| KSI-CED-01 | Cybersecurity Education | Pass | Ensure all employees receive security and privacy awareness training, incident response training, and are familiar with all relevant policies and procedures. |
| KSI-CED-02 | Cybersecurity Education | Pass | Require role-specific training for high risk roles, including at least roles with privileged access. |
| KSI-CED-03 | Cybersecurity Education | Pass | Require role-specific training for development and engineering staff covering best practices for delivering secure software. |
| KSI-CMT-01 | Commitment | Pass | Log and monitor service modifications. |
| KSI-CMT-02 | Commitment | Pass | Execute changes though redeployment of version controlled immutable resources rather than direct modification wherever possible. |
| KSI-CMT-03 | Commitment | Pass | Implement persistent automated testing and validation of changes. |
| KSI-CMT-04 | Commitment | Pass | Consistently follow a documented change management procedure. |
| KSI-CMT-05 | Commitment | Pass | Evaluate the risk and potential impact of any change. |
| KSI-CNA-01 | Cloud Native Architecture | Pass | Configure ALL machine-based information resources to limit inbound and outbound traffic. |
| KSI-CNA-02 | Cloud Native Architecture | Partial | Design systems to minimize the attack surface and minimize lateral movement if compromised. |
| KSI-CNA-03 | Cloud Native Architecture | Pass | Use logical networking and related capabilities to enforce traffic flow controls. |
| KSI-CNA-04 | Cloud Native Architecture | Pass | Use immutable infrastructure with strictly defined functionality and privileges by default. |
| KSI-CNA-05 | Cloud Native Architecture | Pass | Protect against denial of service attacks and unwanted spam. |
| KSI-CNA-06 | Cloud Native Architecture | Pass | Design systems for high availability and rapid recovery. |
| KSI-CNA-07 | Cloud Native Architecture | Pass | Ensure cloud-native information resources are implemented based on host provider"s best practices and documented guidance. |
| KSI-CNA-08 | Cloud Native Architecture | Pass | Use automated services to persistently assess the security posture of all services and automatically enforce secure operations. |
| KSI-IAM-01 | Identity and Access Management | Pass | Enforce multi-factor authentication (MFA) using methods that are difficult to intercept or impersonate (phishing-resistant MFA) for all user authentication. |
| KSI-IAM-02 | Identity and Access Management | Pass | Use secure passwordless methods for user authentication and authorization when feasible, otherwise enforce strong passwords with MFA. |
| KSI-IAM-03 | Identity and Access Management | Pass | Enforce appropriately secure authentication methods for non-user accounts and services. |
| KSI-IAM-04 | Identity and Access Management | Partial | Use a least-privileged, role and attribute-based, and just-in-time security authorization model for all user and non-user accounts and services. |
| KSI-IAM-05 | Identity and Access Management | Pass | Design identity and access management systems that assume resources will be compromised. |
| KSI-IAM-06 | Identity and Access Management | Pass | Automatically disable or otherwise secure accounts with privileged access in response to suspicious activity. |
| KSI-IAM-07 | Identity and Access Management | Pass | Securely manage the lifecycle and privileges of all accounts, roles, and groups. |
| KSI-INR-01 | Incident Response | Pass | Respond to incidents according to FedRAMP requirements and cloud service provider policies. |
| KSI-INR-02 | Incident Response | Pass | Maintain a log of incidents and periodically review past incidents for patterns or vulnerabilities. |
| KSI-INR-03 | Incident Response | Pass | Generate after action reports and regularly incorporate lessons learned into operations. |
| KSI-MLA-01 | Monitoring, Logging, and Analysis | Pass | Operate a Security Information and Event Management (SIEM) or similar system(s) for centralized, tamper-resistent logging of events, activities, and changes. |
| KSI-MLA-02 | Monitoring, Logging, and Analysis | Pass | Regularly review and audit logs. |
| KSI-MLA-03 | Monitoring, Logging, and Analysis | Pass | Rapidly detect and respond to vulnerabilities following requirements and recommendations in the FedRAMP Vulnerability Response and Detection standard. |
| KSI-MLA-05 | Monitoring, Logging, and Analysis | Pass | Perform Infrastructure as Code and configuration evaluation and testing. |
| KSI-MLA-07 | Monitoring, Logging, and Analysis | Pass | Maintain a list of information resources and event types that will be monitored, logged, and audited. |
| KSI-MLA-08 | Monitoring, Logging, and Analysis | Partial | Use a least-privileged, role and attribute-based, and just-in-time access authorization model for access to log data. |
| KSI-PIY-01 | Policy and Implementation | Pass | Generate inventories of information resources from authoritative sources. |
| KSI-PIY-02 | Policy and Implementation | Pass | Document the security objectives and requirements for each information resource. |
| KSI-PIY-03 | Policy and Implementation | Pass | Maintain a vulnerability disclosure program. |
| KSI-PIY-04 | Policy and Implementation | Pass | Build security and privacy considerations into the Software Development Lifecycle and align with CISA Secure By Design principles. |
| KSI-PIY-05 | Policy and Implementation | Partial | Document methods used to evaluate information resource implementations. |
| KSI-PIY-06 | Policy and Implementation | Pass | Have staff and budget for security commensurate with the size, complexity, scope, executive priorities, and risk of the service offering that demonstrates commitment to delivering a secure service. |
| KSI-PIY-07 | Policy and Implementation | Pass | Document risk management decisions for software supply chain security. |
| KSI-RPL-01 | Recovery Planning | Partial | Define Recovery Time Objectives (RTO) and Recovery Point Objectives (RPO). |
| KSI-RPL-02 | Recovery Planning | Pass | Develop and maintain a recovery plan that aligns with the defined recovery objectives. |
| KSI-RPL-03 | Recovery Planning | Pass | Perform system backups aligned with recovery objectives. |
| KSI-RPL-04 | Recovery Planning | Pass | Regularly test the capability to recover from incidents and contingencies. |
| KSI-SVC-01 | Service Configuration | Pass | Continuously evaluate machine-based information resources for opportunities to improve security. |
| KSI-SVC-02 | Service Configuration | Partial | Encrypt or otherwise secure network traffic. |
| KSI-SVC-03 | Service Configuration | Pass | Encrypt information at rest by default. |
| KSI-SVC-04 | Service Configuration | Pass | Manage configuration of machine-based information resources using automation. |
| KSI-SVC-05 | Service Configuration | Pass | Use cryptographic methods to validate the integrity of machine-based information resources. |
| KSI-SVC-06 | Service Configuration | Pass | Use automated key management systems to manage, protect, and regularly rotate digital keys and certificates. |
| KSI-SVC-07 | Service Configuration | Pass | Use a consistent, risk-informed approach for applying security patches. |
| KSI-SVC-08 | Service Configuration | Pass | Ensure that changes do not introduce or leave behind residual elements that could negatively affect confidentiality, integrity, or availability of information resources. |
| KSI-SVC-09 | Service Configuration | Partial | Use mechanisms that continuously validate the authenticity and integrity of communications between information resources. |
| KSI-SVC-10 | Service Configuration | Partial | Remove unwanted information promptly, including from backups if appropriate. |
| KSI-TPR-01 | Third Party Risk | Pass | Follow the requirements and recommendations in the FedRAMP Minimum Assessment Standard regarding third-party information resources. |
| KSI-TPR-03 | Third Party Risk | Pass | Identify and prioritize mitigation of potential supply chain risks. |
| KSI-TPR-04 | Third Party Risk | Partial | Monitor third party software information resources for upstream vulnerabilities, with contractual notification requirements or active monitoring services. |
