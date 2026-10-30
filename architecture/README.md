**AWS Identity and Access Management (IAM) Security Architecture**

**1. Project Overview**

This project demonstrates the design and implementation of a secure, multi-account AWS identity and access management architecture.

The architecture incorporates AWS Organizations, IAM Identity Center, IAM users, groups, customer-managed policies, IAM roles, and AWS Security Token Service (STS).

The objective is to demonstrate centralized identity management, least-privilege access control, account isolation, and temporary credential management.

**2. Architecture Diagram**

The diagram illustrates how centralized administrative access and restricted IAM permissions are implemented across two AWS accounts.


**3. Architecture Components**

| AWS Component | Purpose |
|---|---|
| AWS Organizations | Provides centralized management of multiple AWS accounts. |
| Management Account | Hosts organization-level governance and centralized identity administration. |
| IAM-Security-Lab | Provides an isolated environment for IAM security testing. |
| IAM Identity Center | Centralizes workforce authentication and AWS account access. |
| AdministratorAccess Permission Set | Grants administrative permissions to the assigned administrator. |
| IAM User | Represents the SecurityAnalyst-Test identity. |
| IAM Group | Organizes security analyst permissions. |
| Customer-Managed IAM Policy | Defines restricted IAM read-only permissions. |
| IAM Role | Provides an assumable identity with defined permissions. |
| AWS STS | Issues temporary security credentials for authorized role sessions. |



**4. Security Controls Implemented**

**Account Isolation**

Created a dedicated AWS member account to separate security experiments from the management account.

**Centralized Identity Management**

Configured AWS IAM Identity Center with MFA-enabled administrative access.

**Least-Privilege Access**

Created a custom IAM policy granting selected IAM read-only permissions while excluding administrative actions.

**Role-Based Access Control**

Configured a dedicated IAM role with a restricted permissions policy and a trust relationship for the designated IAM user.

**Temporary Credentials**

Successfully tested AWS STS role assumption using a temporary administrator trust configuration, which was removed after testing.

****5. Security Validation**

| Security Test | Result |
|---|---|
| IAM user: `iam:ListUsers` | Allowed in IAM Policy Simulator |
| IAM user: `iam:CreateUser` | Implicitly denied in IAM Policy Simulator |
| Live STS role assumption using temporary administrator trust | Successful |
| Assumed role: `iam:ListUsers` | Allowed |
| Assumed role: `iam:ListAccessKeys` | Access denied |
| Temporary administrator trust removed after testing | Completed |

**Testing clarification:** The live STS test used a temporary administrator trust relationship. The final role trust configuration identifies SecurityAnalyst-Test as the trusted principal. Direct role assumption by that IAM user was not independently validated.

**6. Security Architecture Principles Demonstrated****

* Centralized identity and access management
* Multi-account security architecture
* Least-privilege access
* Separation of administrative and analyst permissions
* Role trust and permissions management
* Temporary credential usage
* Security control validation

**7. Project Deliverables**

* AWS IAM security architecture diagram (PNG)
* Editable architecture diagram (Draw.io)
* AWS IAM security configuration
* IAM permissions and STS testing results
* Technical architecture documentation

**8. Key Takeaways**

This project demonstrates practical experience designing and validating identity and access controls within a multi-account AWS environment.

It highlights the importance of separating privileged administration from restricted operational access, applying least-privilege policies, and using temporary credentials for authorized AWS role sessions.

