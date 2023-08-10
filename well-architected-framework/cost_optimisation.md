# Cost Optimisation Pillar
## Overview
Cost Optimisation is the ability to achieve business outcomes at the **lowest price point**.

## Design Principles
The design principles for cost optimisation in the cloud include:
- **Implement cloud financial management**: our organisation must dedicate the necessary time and resources for building capability in this new domain of technology and user management.
- **Adopt a consumption model**: pay only for the compute resources we consume, and increase or decrease usage depending on business requirements.
- **Measure overall efficiency**: measure business output of the workoad and the costs associated with delivery. Use this data to understand the gains we make from increasing output, increasing functionality and reducing cost.
- **Stop spending money on undifferentiated heavy lifting**: focus on customers and business projects rather than on IT infrastructure.
- **Analyse and attribute expenditure**: cloud makes it easy to accurately identify the cost and usage of workloads, which then allows transparent attribution of IT costs to revenue streams and individual workload owners. This helps measure ROI and give workload owners an opportunity to optimise their resources and reduce costs.

## Practice Areas
### Cost-Effective Resources
Using the appropriate services, resources, and configuration for our workload is key to cost savings.

The best practices include:
- Select the correct **pricing model** that best fits our needs. For example, EC2 offers on-demand instances that have no long-term commitments and Savings Plans and Reserved Instances that offer a discount for certain commitments.
- Take advantage of **managed services** such as Amazon RDS which can lower per-item and management costs.
- Consider **CloudFront** to potentially reduce costs associated with network traffic.
- Use **automation** through template-based services such as CloudFormation to bring up test environments only when needed.

### Manage Supply and Demand
We should supply resources to **match our workload demand** at the time they're needed - eliminating the need for costly and wasteful over provisioning.

The best practices include:
- **Manage demand** with a queue or buffer.
- Supply the right amount of resources **dynamically** through auto scaling.

### Expenditure Awareness
Being able to transparently **attribute expenditure** allows us to understand the ROI of our system and products. 

The best practices include:
- Use **Cost Explorer** to categorise and track AWS costs. See patterns in how much we spend on AWS resoucres over time, identify areas that need further inquiry, and see trends that we can use to understand our costs.

### Optimising Over Time
As AWS releases new services and features, it is best practice to reassess our existing architectural decisions to ensure they continue to be the most effective.

The best practices include:
- Aggressively **decommission** resources and entire services or systems that we no longer need.
- Use the **AWS blog** to identify new services and features that can be implemented in our workload.
