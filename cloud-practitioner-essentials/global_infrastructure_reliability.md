# Global Infrastructure and Reliability
## Overview
AWS operates data centers all **around the world**. Applications can use services in multiple data centers, so that traffic can be **diverted** if one data center fails. This ensures applications can be **highly available**.

## Availability Zones
An **Availability Zone** (AZ) is a **single data center** or a **group of data centers**. AZs are located **tens of miles apart from each other**. This is close enough to have low latency, but distant enough to reduce collateral disasters.

## Regions
A **Region** is a **geographical area** that contains AWS resources. Each Region consists of multiple Availability Zones.

There are four **business factors** when determining the right Region:
- **Compliance**: certain companies and locations have **regulations** that require data reside in a specific area.
- **Proximity**: picking a Region that is **close to the customer** will help them get the content **faster**.
- **Available services**: not all AWS services are available on all Regions.
- **Pricing**: different Regions may have **different costs** due to the taxation structure in the country or otherwise.

## Edge Locations
An **edge location** is a site that Amazon CloudFront (CDN service) uses to store **cached copies** of content **closer to the customers** for **fast delivery**.

## Provisioning AWS Resources
In AWS, everything is an **API call**. These APIs can be invoked to provision, configure and manage AWS resources.

There are various wrappers to help interact with the AWS API:
- **Management console**: web-based interface.
- **Command Line Interface**: allows for automation using scripts.
- **Software Development Kits**: APIs designed for specific programming languages.

### Elastic Beanstalk
**Elastic Beanstalk** (EBN) is a service that helps provision **EC2-based environments**. We provide the code and configuration settings, and EBN deploys the resources necessary for the following tasks:
- Adjust capacity.
- Load balancing.
- Automatic scaling.
- Application health monitoring.

### CloudFormation
**CloudFormation** is an **infrastructure-as-code** (IaC) service that allows us to build environments by writing **lines of code**. CloudFormation provides us resources in a safe, repeatable manner. This enables us to frequently build our infrasturcture and applications without manual actions.
