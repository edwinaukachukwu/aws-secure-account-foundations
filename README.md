**AWS Secure Account Foundation**

**Project Overview**

This project demonstrates the implementation of foundational security controls within an Amazon Web Services (AWS) environment.

The objective is to establish a secure, monitored, and governed AWS account using industry-relevant cloud security practices.

The project focuses on Identity and Access Management (IAM), security monitoring, threat detection, configuration management, and cost governance.

**Project Objectives**
* Establish secure administrative access using AWS IAM Identity Center.
* Implement multi-factor authentication (MFA) to strengthen account security.
* Enable AWS CloudTrail Event History for auditing AWS API activity.
* Configure Amazon GuardDuty for threat detection.
* Implement AWS Config for resource configuration monitoring.
* Configure IAM Access Analyzer to identify potential external access.
* Establish AWS Budgets for cost monitoring.

## AWS Services Used

| AWS Service | Security Function |
|---|---|
| AWS IAM Identity Center | Centralized workforce access management |
| AWS Organizations | AWS account organization and governance |
| AWS CloudTrail | API activity auditing |
| Amazon GuardDuty | Threat detection |
| AWS Config | Resource configuration monitoring |
| IAM Access Analyzer | External access analysis |
| AWS Budgets | Cost monitoring |

## Security Controls Implemented

**Security Controls Implemented**

**1. Identity and Access Management**
* Enabled MFA for the AWS root user.
* Configured AWS IAM Identity Center.
* Created an administrative identity.
* Assigned the AdministratorAccess permission set.
* Enabled MFA for administrative access.

**2. Security Monitoring and Threat Detection**
* Verified AWS CloudTrail Event History.
* Enabled Amazon GuardDuty.
* Reviewed optional GuardDuty protection plans.
* Disabled unnecessary protection plans to reduce potential costs.

**3. Configuration Management**
* Enabled AWS Config in the US East (N. Virginia) Region.
* Configured recording for Amazon S3 bucket resources.
* Selected daily configuration recording.
* Configured Amazon S3 delivery for configuration history.

**4. Security Governance**
* Created an IAM Access Analyzer external access analyzer.
* Reviewed findings associated with AWS IAM Identity Center.
* Examined IAM role trust relationships and SAML federation.

**5. Cost Governance**
* Configured a $10 monthly AWS Budget.
* Verified email notifications.
* Enabled administrative access to AWS billing information.



**Security Architecture**

An AWS security architecture diagram will be added to illustrate the relationships between identity management, monitoring, governance, and AWS resources.

**Security Framework Alignment**
The implemented controls support concepts found in the following frameworks:
* NIST Cybersecurity Framework (CSF)
* NIST SP 800-53
* CIS AWS Foundations Benchmark
* AWS Well-Architected Framework — Security Pillar

This project demonstrates selected security practices rather than full compliance with these frameworks.

**Key Learning Outcomes**
Through this project, I gained practical experience in:
* AWS account security configuration.
* IAM Identity Center and federated administrative access.
* Security monitoring and threat detection.
* AWS configuration recording.
* External access analysis.
* Cloud security governance and cost management.

**Future Enhancements**
* Create an AWS security architecture diagram.
* Add sanitized configuration screenshots.
* Implement automated compliance checks using AWS Config rules.
* Explore least-privilege access policies.
* Implement additional security controls in a dedicated test environment.

**Project Status**

Phase 1: Initial AWS Security Foundation — Completed

Phase 2: Architecture Documentation — In Progress

Author

Edweena28

Cloud Security Architecture Portfolio
