# Security
## Shared Responsibility Model
The **shared responsibility model** divides responsibility for **security** into:
- **Customer responsibility**: security **in** the cloud.
    - Securing applications and data.
    - Managing access controls and user identities.
    - Configuring network security groups, firewalls and other security measures within the cloud.
    - Encrypting data in transit and at rest.
    - Implementing backup and diaster recovery strategies.
    - Regularly updating and patching applications and operation systems.
    - Monitoring and logging activities within the cloud environment.
    - Compliance with applicable regulations and industry standards.
- **AWS responsibility**: security **of** the cloud.
    - Infrastructure security, including physical security measures.
    - Network security, such as firewall configuration, intrusion detector systems, and DDoS protection.
    - Hypervisor security, ensuring the isolation and security of virtual machines.
    - Patch management and system updates for the underlying infrastructure.
    - Data center operations and maintenance.
    - Availability of the cloud services as specified in the service-level agreements (SLAs).

## User Permissions and Access
### AWS Identity and Access Management (IAM)
**IAM** enables us to manage access to AWS services and resources securely.

#### AWS Account Root User
All new AWS accounts begin with a **root user** identity. It is accessed by signing in with the email address and password used to create the AWS account. It has **complete access** to all AWS services and resources in the account.

Best practice: the root user should NOT be used for everyday tasks. Instead, we use the root user to create the first IAM user and assign it permissions to create other users. We then create other IAM users, and access those identities for performing regular tasks in AWS.

#### IAM Users
An **IAM user** is an identity that we create in AWS. It represents a person or application that interacts with AWS services and resources. It consists of a name and credentials.

To allow an IAM user to perform specific actions, we must grant the IAM user the necessary **permissions**.

Best practice: an IAM user should be created for each person who needs to access AWS.

#### IAM Policies
An **IAM policy** is a document that allows or denies permissions to AWS services and resoucres.

IAM policies enable us to customise users' level of access to resources. Each IAM policy can be attached to an **IAM user** or an **IAM group**.

Best practice: follow the principle of **least privilege**.

#### IAM Groups
An **IAM group** is a collection of IAM users. When we assign an IAM policy to a group, all users in the group inherit the permissions.

#### IAM Roles
An **IAM role** is an identity that we can assume to gain **temporary access** to permissions. 

Before an IAM user, application, or service can assume an IAM role, they must be granted permissions to switch to the role. When someone assumes a new IAM role, they abandon all previous permissions they had from a previous role.

Best practice: roles are ideal for temporary access, instead of long-term.

## AWS Organisations
**AWS Organisations** consolidates and manages multiple AWS accounts within a central location. 

When we create an organisation, Organisations automatically creates a **root**, which is the parent container for all accounts in the organisation.

In Organisations, we can centrally control permissions for the accounts in our organisation by using **service control policies** (SCPs). SCPs enable us to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.

### Organisational Units
In Organisations, we group accounts into **organisational units** (OUs) to ease managing accounts with similar business or security requirements. When we apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy.

## Compliance
### AWS Artifact
**AWS Artifact** provides on-demand access to AWS security and compliance reports and select online agreements. It consists of 2 main sections:
- **Artifact Agreements**: review, accept and manage agreements with AWS regarding our use of certain types of information throughout AWS services.
- **Artifact Reports**: provide compliance reports from third-party auditors.

### Customer Compliance Center
The **Customer Compliance Center** contains resources to help us learn more about AWS compliance.

## Denial of Service Attacks
A **denial-of-service (DoS) attack** is a deliberate attempt to make a website or application unavailable to users.

Typically, this is achieved by attackers flooding a website or application with excessive network traffic until the targeted website or application becomes overloaded and is no longer able to respond.

### Distributed Denial of Service Attacks
In a **distributed** DoS attack, multiple sources are used to start an attack that aims to make a website or application unavailable.

### AWS Shield
**AWS Shield** protects applications against DDoS attacks. It provides two levels of protection:
- **Standard**: automatically protects all customers at 0 cost. Protects AWS resources from the most common, frequently occurring types of DDoS attacks.
- **Advanced**: paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks.

## Additional Security Services
### AWS Key Management Service (AWS KMS)
**AWS KMS** enables us to perform encryption operations through **cryptographic keys**.

### AWS Web Application Firewall (AWS WAF)
**AWS WAF** lets us monitor network requests that come into our web applications. WAF works together with CloudFront and an Application Load Balancer. It allows blocking of traffic via a **web access control list (ACL)** to protect our AWS resources.

### Amazon Inspector
**Amazon Inspector** helps improve the security and compliance of applications be running **automated security assessments**. It checks applications for security vulnerabilities and deviations from security best practices. After an assessment has been performed, Inspector provides a list of security findings. The list prioritises by security level and includes a description of each security issue and a recommended fix.

### Amazon GuardDuty
**Amazon GuardDuty** provides intelligent threat detection for AWS infrastructure and resources. It identifies threats by continuously monitoring the network acctivity and account behaviour within our AWS environment.
