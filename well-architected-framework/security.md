# Security Pillar
## Overview
**Security** is the ability to **protect information, systems and assets** while delivering business value through **risk assessments** and **mitigation strategies**.

## Design Principles
Design principles for security in the cloud include:
- **Strong identity foundation**: follow principle of least privilege and enforce separation of duties.
- **Traceability**: monitor, alert, and audit any changes to our environment in real time. 
- **Security at all layers**: apply defense in depth to all layers such as edge, VPC, application, code, etc.
- **Automation**: automate to securely scale more rapidly and cost-efectively. 
- **Protect data**: classify data into sensitivity levels and use mechanisms, such as encryption, tokenization, and access control where appropriate.
- **Keep people away**: use mechanisms and tools to reduce or eliminate the need for direct access or manual processing data.
- **Preparation**: prepare for incidents by having incident management and investigation policy and processes that align to organisational requirements.

## Practice Areas
### Identity and Access Management
#### Identity Management
When operating secure AWS workloads, we need to manage **human identities** and **machine identities**. 

The best practices include:
- **AWS IAM**: ensure only authorised and authenticated users and services are able to access resources, and only in the manner that is intended.
- **Strong sign-in mechanism**: require MFA and strong password policies.
- **Centralised identity provider**: manage access by creating, managing and revoking access from a single location.
- **Secure secrets**: automatically rotate secrets using AWS Secrets Manager.

#### Permissions Management
Permissions control who can access what, and under what conditions.

The best practices include:
- **Access requirements**: have clear definitions of who or what should have access to a resource
- **Least privilege**: grant only the access that identities require to perform specific actions on specific resources under specific conditions.
- **Limit public and cross-account access**: reduce cross-account access to only the resources that require it.
- **Permission reduction**: continuously remove permissions no longer needed to achieve least-privilege permissions.

### Detection
Detection is the ability to **detect** and **identify** a **security event**.

AWS provides detective mechanisms that **runs a playbook** when certain events happen. For example, we can launch code when users perform an action on AWS resources. This allows playbooks to now be in code, which can be versioned, tested and run whenever a certain event happens.

### Infrastructure Protection
Infrastructure protection ensures systems and services in our workload are protected against **unintended and unauthorised access**, and **potential vulnerabilities**.

#### Control Traffic at All Levels
Layers in our architecture allow us to apply a **defense in-depth** approach to securing networks:
- Use edges services (e.g. CloudFront).
- Divide VPC into layers using subnets.
- Use all controls available.

#### Managed Services
Managed services **reduce maintenance tasks** by taking care of the underlying instances or compute and therrefore patching and hardening.

### Data Protection
Data protection involves identifying and classifying the data we have, and then using **controls** and **patterns** to keep the data **confidential** while preserving its **integrity** and **availability** at rest and in transit.

#### Encrypting Data
Data should be encrypted both in **transit** and at **rest**. Most AWS services can be easily configured for encryption.

#### Keeping People Away From Data
All users (including administrators) should be kept away from directly accessing sensitive data and systems under normal operational circumstances.

For example:
- Dashboards should be provided instead of direct access to a data store to run queries.
- CI/CD pipelines should be used to automate creation and updates using CloudFormation when managing infrastructure.

### Incident Response
Incident response defines how the processes in place **respond** to and **mitigate** potential impact of **security incidents**.

The best practices include:
- **Pre-deployed tools**: CloudFormation enables us to template and provision a **clean room** for conducting investigations and forensics.
- **Game Days**: conduct regular Game Days to simulate security events to test and improve processes.
