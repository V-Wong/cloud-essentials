# Compute in the Cloud
## Amazon EC2
### Overview
**Elastic Compute Cloud** (EC2) provides secure, resizable compute capacity in the cloud as EC2 instances. With EC2 instances:
- You can provision and launch an instance **within minutes**.
- You can **stop using it** when you have finished running a workload.
- You **pay only** for the compute time **you use** when an instance is running.
- You can **save costs** by paying only for server capacity that you need or want.

### How Amazon EC2 Works
There are three steps to running an application on EC2:
- **Launch**: select a template with basic configuration for the instance. 
    - This includes the OS, application server, or applications.
    - We specify the instance type; specific hardware configuration. 
    - We specify security settings to control the network traffic that can flow into/out of the instance.
- **Connect**: applications have different methods to connect directly to the instance and exchange data. Users can also connect to the instance by logging in and accessing the computer desktop.
- **Use**: commands can be run to install software, add storage, copy and organise files, and more.

### EC2 Instance Types
EC2 instances are optimised for **different tasks**. The main instance types are:
- **General purpose**: **balances** compute, memory and networking resources. These can be used for:
    - Application servers.
    - Gaming servers.
    - Backend servers for enterprise applications.
    - Small and medium databases.
- **Compute optimised**: ideal for **compute-bound applications** that benefit from high-performance processes. This includes:
    - High performance web servers.
    - Compute-intensive application servers.
    - Dedicated gaming servers.
    - Batch processing workloads.
- **Memory optimised**: designed for workloads that process **large datasets in memory**. This includes:
    - High-performance databases
    - Real-time processing of a large amount of unstructured data.
- **Accelerated computing**: uses **hardware accelerators**, or coprocessors, to perform some functions (e.g. floating point operations) more efficiently. These are ideal for:
    - Graphics applications.
    - Game streaming.
    - Application streaming.
- **Storage optimised**: designed for workloads that require high, **sequential** read and write access to large datasets on local storage. These are ideal for:
    - Distributed file systems.
    - Data warehousing applications.
    - High-frequency OLTP systems.

### Amazon EC2 Pricing
EC2 offers **pricing options** for different use cases. These options are:
- **On-demand**: ideal for **short-term, irregular, and uninterrupted workloads**. No upfront costs or minimum contracts. Instances run continuously until stopped, and you only pay the compute time you use. The main use cases include:
    - Developing and testing applications with **unpredictable usage patterns**.
    - Not recommended for extended workloads because other cost options can be cheaper.
- **Savings plans**: costs are reduced by committing to **spend a specific dollar amount** per hour over a defined period.
- **Reserved instance**: costs are reduced by committing to **utilize an instance** at a specific price over a defined period.
- **Spot instance**: ideal for workloads with **flexible start and end times**, or can withstand **interruptions**. Offers significant savings but instances may not always be available, and AWS may take back the instance.
- **Dedicated hosts**: physical servers with Amazon EC2 instance capacity that is fully **dedicated to your use**.

### Scaling Amazon EC2
**Scalability** involves automatically responding to **changing demand** by scaling in/out. AWS provides automatic scaling for EC2 instances via **Auto Scaling**. Auto Scaling enables us to automatically add/remove EC2 instances in response to **changing application demand**. There are two scaling approaches:
- **Dynamic scaling**: scaling responds to changing demand.
- **Predictive scaling**: automatically schedules the right number of EC2 instances based on predicted demand.

### Directing Traffic with Elastic Load Balancing
**Elastic Load Balancing** (ELB) is an AWS service that **automatically distributes incoming application traffic** across multiple resources, such as EC2 instances.

A **load balancer** acts as a **single point of contact** for all incoming web traffic to an Auto Scaling group. Requests are first routed to the load balancer, which then **spreads the request** across multiple resources that will handle them.

## Messaging and Queueing
### Monolithic Applications vs Microservices
Applications are made of **multiple components** that communicate with each other to transmit data, fulfil requests, and keep the application running.

In a **monolithic** application:
- Components are **tightly coupled** and heavily rely on each other.
- If a single component fails, **other components fail**, and possibly the entire application fails.

In a **microservices** application:
- Components are **loosely coupled** and can work independently of each other.
- If a single component fails, the other components can keep running, preventing the entire application from failing.

### Amazon Simple Notification Service (SNS)
**Simple Notification Service** (SNS) is a **publish/subscribe** service. In this service, software components can send a message and **notify subscribed software components**. A component sends a message to the service, then all subscribed components are notified and can process the receieved message.

### Amazon Simple Queue Service (SQS)
**Simple Queue Service** (SQS) is a **message queueing** service. In this service, software components can send and receive **messages to other software components**. A component places a message into the queue, then another component retrieves the message from the queue, processes it, and then deletes it from the queue.

## Other Compute Services
### Serverless Computing
#### Overview
With EC2, we must:
- Provision instances.
- Upload our code.
- Manage the instance while the application is running.

In contrast, **serverless** means that code still runs on servers, but:
- We do not need to provision or manage these servers.
    - The service is for responsible managing these servers for us.
    - The service can automatically scale to meet our application demands.
- We can focus on innovating new products and features.

#### AWS Lambda
**Lambda** is a service that lets us run code **without needing to provision or manage servers**. The typical Lambda workflow is:
- **Upload our code** to Lambda.
- Set the code to **trigger from an event source**, such as AWS services, mobile applications, or HTTP endpoints.
- Lambda only runs the code when triggered.
    - We only pay for the compute time used.
    - Charges are **only incurred** when the code is **running**.

### Containerisation
#### Overview
**Containers** are a standard way to **package application code and dependencies into a single object**. These are useful for processes and workflows where there are essential requirements for **security**, **reliability** and **scalability**.

#### Amazon Elastic Container Service (Amazon ECS)
**Elastic Container Service** (ECS) is a highly scalable and performant **container management system** that enables running and scaling containerised applications on AWS.

#### Amazon Elastic Kubernetes Service (EKS)
**Elastic Kubernetes Service** (EKS) is a fully managed service to run Kubernetes on AWS. **Kubernetes** is an OSS to deploy and manage containerised applications at scale.

#### AWS Fargate
**Fargate** is a **serverless compute engine** for containers. It works with both ECS and EKS. With Fargate, we do not need to provision or manage servers. Fargate manages the server infrastructure for us.
