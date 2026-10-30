**AWS Secure Account Foundation & IAM Security Architecture**

**Cloud Security Architecture Portfolio | Project 01**

**1. Project Overview**

This project demonstrates the design, implementation, and validation of a secure AWS multi-account environment, focusing on identity and access management (IAM), centralized authentication, least-privilege access, and security governance.

The architecture separates centralized administration from a dedicated security testing environment using AWS Organizations and IAM Identity Center.

Project Objective: Establish a secure AWS account foundation and implement identity and access controls aligned with AWS security best practices.

**2. Technologies & AWS Services**

* AWS Organizations
* AWS IAM Identity Center
* AWS Identity and Access Management (IAM)
* AWS Security Token Service (STS)
* AWS CloudTrail
* AWS IAM Access Analyzer
* Amazon GuardDuty
* AWS Config
* AWS Budgets
* AWS CloudShell
* Draw.io

**3. Architecture Design**

The architecture consists of two AWS accounts:

**Management Account — Edweena28**

Provides centralized organizational governance, consolidated billing, and IAM Identity Center administration.

**Member Account — IAM-Security-Lab**

Provides an isolated environment for implementing and testing IAM security configurations.

**Architecture Diagram**

For detailed architecture documentation, see the Architecture [https://github.com/edwinaukachukwu/aws-secure-account-foundations](http://architecture/README.md)

**4. Implementation**

**Phase 1: Secure AWS Account Foundation**

Configured the AWS management account with foundational security capabilities:

* Enabled MFA for the root user.
* Configured IAM Identity Center for centralized administrative access.
* Created an administrative workforce identity.
* Assigned the AdministratorAccess permission set.
* Configured AWS budget alerts.
* Reviewed CloudTrail event history.
* Created an IAM Access Analyzer external access analyzer.
* Enabled Amazon GuardDuty protection.
* Configured AWS Config recording.

**Phase 2: Multi-Account Architecture**

* Established an AWS Organization.
* Created the IAM-Security-Lab member account.
* Assigned centralized administrative access to the lab through IAM Identity Center.
* Separated security testing activities from management account operations.

**Phase 3: Least-Privilege IAM Configuration**

Created the following IAM resources in the security lab:

**IAM User:** SecurityAnalyst-Test

Created a dedicated IAM user without a console password or long-term access keys.

**IAM Group:** SecurityAnalysts

Created a group to organize analyst permissions.

Customer-Managed IAM Policy: SecurityAnalystReadOnlyPolicy

Configured a restricted policy allowing selected IAM read-only operations while excluding administrative actions.

I**AM Role:** SecurityAnalystRole

Created an IAM role with the same restricted read-only policy and configured a trust relationship for the designated IAM user.

**Phase 4: Security Testing & Validation**

Validated least-privilege permissions through the IAM Policy Simulator and live AWS STS testing

| Security Test | Result |
|---|---|
| IAM user: `iam:ListUsers` | Allowed in IAM Policy Simulator |
| IAM user: `iam:CreateUser` | Implicitly denied in IAM Policy Simulator |
| Live STS role assumption using temporary administrator trust | Successful |
| Assumed role: `iam:ListUsers` | Allowed |
| Assumed role: `iam:ListAccessKeys` | Access denied |
| Temporary administrator trust removed after testing | Completed |

**Testing clarification:** Live STS role assumption was validated using a temporary administrator trust relationship. The final role trust policy identifies SecurityAnalyst-Test as the trusted principal. Direct assumption by this IAM user was not independently tested.

**5. Security Architecture Principles**

**This project demonstrates:**

*** Account Isolation:** Separating governance and testing environments.
*** Centralized Identity Management:** Managing workforce access through IAM Identity Center.
*** Least Privilege:** Restricting permissions to required IAM read-only operations.
*** Role-Based Access:** Using IAM roles and permission sets to control access.
*** Temporary Credentials:** Using AWS STS instead of long-term credentials for role sessions.
*** Security Validation:** Testing allowed and denied API actions.
*** Security Monitoring:** Establishing foundational logging and threat detection capabilities.

**6. Security Framework Alignment**

The project demonstrates technical controls relevant to the following frameworks:

| Framework | Relevant Security Areas |
|---|---|
| NIST Cybersecurity Framework 2.0 | Identity management, access control, governance, and monitoring |
| NIST SP 800-53 | Access Control (AC), Identification and Authentication (IA), and Audit and Accountability (AU) |
| ISO/IEC 27001:2022 | Access control, identity management, authentication, and logging |
| AWS Well-Architected Framework | Security Pillar - identity and access management, detection, and infrastructure protection |

The project demonstrates technical controls relevant to the following frameworks.

**Note:** Framework alignment describes relevant security concepts and does not represent formal compliance certification or a completed control assessment.

**7. Project Deliverables**

* Secure AWS management account foundation
* Isolated IAM security lab account
* Centralized administrative access configuration
* Custom IAM least-privilege policy
* IAM group and role configuration
* IAM Policy Simulator validation
* Live AWS STS security testing
* Architecture diagram and technical documentation


**8. Key Skills Demonstrated**

Cloud Security Architecture | AWS IAM | Multi-Account Governance | Least-Privilege Access | Identity Federation Concepts | IAM Role Trust Policies | AWS STS | Security Control Validation | Cloud Security Monitoring

**9. Project Status**
    
**Status: Completed — Initial Implementation and Documentation**

The initial architecture, IAM configurations, and documented security tests are complete.

Future improvements may include direct testing of role assumption by the designated IAM user, automated infrastructure provisioning, and expanded security monitoring.


