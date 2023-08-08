# Reliability Pillar
## Overview
Reliability is the ability of a workload to **perform its intended function correctly and consistently** when it is expected to. This includes the ability to operate and test the workload through its total lifecycle.

**Resiliency** is the ability of a workload to:
- **Recover** from infrastructure or service disruptions.
- **Meet demand** by dynamically acquiring computing resources.
- **Mitigate disruptions** such as misconfigurations or transient network issues.

## Design Principles
Design principles for reliability in the cloud include:
- **Automatically recover from failure**: monitor the workload and run automations when a threshold is breached.
- **Test recovery procedures**: reduce risk by simulating failure scenarios to improve recovery procedures.
- **Scale horizontally**: replace one large resource with multiple small resources to reduce impact of a single failure.
- **Stop guessing capacity**: automate addition or removal of resources in response to demand and workload utilisation.
- **Manage change through automation**: infrastructure changes should be made using automation.

## Practice Areas
### Foundations
Foundational requirements are those whoe scope **extends beyond a single workload or project**. For example:
- The data center must have sufficient network bandwidth to accomodate the workload.
- The service limits are sufficient for the workload.

### Workload Architecture
#### Service-Oriented Architecture (SOA)
SOA is the practice of making software components **reusable via service interfaces**. **Microservices archictecture** goes further to make components **smaller** and **simpler**.

#### Distributed Systems
Distributed systems rely on **communications networks** to interconnect networks such as servers or services. Our workload must operate reliably despite data loss or latency in these networks. Components must operate in a way that does not negatively impact other components or the workload. These best practices prevent failrues and improve mean time between failrues (MTBF).

Architectural choices to **prevent** failures include:
- Implementing **loosely coupled** dependencies.
- Making all responses **idempotent**.

Architectural choices to **mitigate** failure include:
- Implementing **graceful degredation**.
- **Throttling requests**.
- **Failing fast**.
- **Limiting queues**.

### Change Management
#### Monitoring Workloads
**Monitoring** allows us to quickly **identify trends** that could lead to capacity issues or SLA breaches. We can then run automations in response to these trends. For example, we can setup an automation to add more servers as a system gains users.

#### Automatic Scaling
With AWS, the best practice is to use **automatic scaling** to add new instances only when necessary, and terminate them when no longer needed.

#### Deployment

