# Performance Efficiency Pillar
## Overview
Performance Efficiency revolves around the ability to **use IT resources efficiently**. 

## Design Principles
Design principles for performance efficiency in the cloud include:
**Democratise advanced technologies**: consume technologies as a service to allow teams to focus on product development rather than resource provisioning and management.
- **Go global in minutes**: deploying around the world providers lower latency and a better experience for customers at minimal cost.
- **Use serverless architectures**: removes the operational burden of managing physical servers, and can lower transactional costs because managed services operate at cloud scale.
- **Experiment more often**: quickly carry out comparative testing using different types of instances, storage, or configurations.
- **Consider mechanical sympathy**: use the technology approach that aligns best with our goals.

## Practice Areas
### Selection
The optimal solution for a particular workload **varies**, and solutions often **combine multiple approaches**. Well-architected workloads use multiple solutions and allow different features to improve performance.

One key best practice is to **appropriately size** computer, storage, database, and networking resources. **Benchmarking** and **load testing** allow us to experiment with different sizes of resources and features. This gives us the data to select the combination of size and features with the best return on investment.

### Review
Over time, **new technologies and approaches** become available that could improve the performance of our workload. In the cloud, is it easy to **experiment** with new features and services because infrastructure is code.

One key best practice is **load testing**. We can use CloudFormation to define architecture as code allowing us to version control and modify over time. This allows us to provision different environments in a controlled way and allow us to bring up production-scale test environments. When we want to try out a new resoucre type or feature, we can:
1. Fork the template.
2. Change it to use the new settings.
3. Bring up a short-lived test environment.
4. Carry out load testing at production scale.
5. Terminate the environment to stop costs.

This allows us to experiment with features in a low-risk and affordable way.

### Monitoring
We must **monitor** the performance of our workload and **remediate issues** before they impact customers. 

One key best practice is **performance alarms**. Monitoring metrics should be used to raise alarms when thresholds are brached, and initate an automated action to work around any badly performing components.

### Trade-off
In some situations, we can **trade** consistency, durability, and space for time or latency, to deliver higher performance. As we make changes to our workload, we should **collect and evaluate metrics** to determine the impact of those changes to the system and end users.

One key best practice is **proximity and caching**. For example:
- **Web layer**: CloudFront can be used to cache content closer to end users.
- **Database layer**: ElastiCache and read replicas can be used to speed up reads.

