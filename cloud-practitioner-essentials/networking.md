# Networking
## Connectivity to AWS
### Virtual Private Cloud
**Virtual Private Cloud** (VPC) enables us to provision a **logically isolated section** of the AWS cloud. In this isolated section, we can launch resources in a **virtual network** we define.

#### Internet Gateway
We use an **internet gateway** to allow **public traffic** from the internet to access our VPC.

#### Virtual Private Gateway
We use a **virtual private gateway** to establish a VPN connection between our VPC and a **private network**, such as an internal corporate network.

#### Direct Connect
**Direct Connect** is a service that enables us to establish a **dedicated private connection** between our data center and a VPC.

## Subnets and Network Acess Control Lists
### Subnets
A **subnet** is a **section of a VPC** in which we can **group resources** based on security or operation needs. Subnets can be public or private:
- **Public subnet**: contains resources that need be accessible by the public, such as an online store's website.
- **Private subnet**: contains resources that should be accessible only through our private network such as a database that contains customer's personal information and order histories.

In a VPC, subnets can **communicate with each other**.

### Network Traffic in a VPC
#### Network Access Control List (ACLs)
A **network access control list** (ACL) is a **virtual firewall** that controls inbound and outbound traffic at the **subnet level**.
    - Analogy: ACL is like a passport control officer between countries.

Network ACLs perform **stateless** packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound.

#### Security Groups
A **security group** is a **virtual firewall** that controls inbound and outbound traffic for an **EC2 instance**.
    - Analogy: a security group is like the lobby attendant in an apartment building.

Security groups perform **stateful** packet filtering. They remember previous decisions made for incoming packets. When a packet is sent from an EC2 instance to the internet, the security group remembers the request and allows the response packet to proceed, regardless of inbound security group rules.

## Global Networking
### Domain Name Service
**Domain Name System** (DNS) resolution is the process of translating a **domain name** to an **IP address**. Suppose we want to visit AnyCompany's website:
- When we enter the domain name into the browser, this request is sent to a customer (ISP) DNS resolver.
- The customer DNS resolver asks the company DNS server for the IP address that corresponds to AnyCompany's website.
- The company DNS server responds by providing the IP address for AnyCompany's website.

#### Route 53
**Route 53** is Amazon's DNS web service. It gives developers and businesses a reliable way to route end users to internet applications hosted in AWS.

### Flow of User Request
Suppose that AnyCompny's application is running on serveral EC2 instances in an Auto Scaling group that attaches to an Application Load Balancer. The flow of a customer request is:
- A customer requests data from the application by going to AnyCompany's website.
- Route 53 uses DNS resolution to identify AnyCompany's corresponding IP address. This is sent back to the customer.
- The customer's request is sent to the nearest edge location through Amazon CloudFront.
- Amazon CloudFront connects to the Application Load Balancer, which sends the incoming packet to an EC2 instance.
