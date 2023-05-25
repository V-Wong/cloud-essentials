# Monitoring and Analytics
## Monitoring
**Monitoring** involves observing systems, **collecting metrics** over time, and then using them to **make decisions** or **take actions**. With the elastic nature of AWS services, we want to keep a close pulse of AWS resources to ensure that systems are running as expected.

## Amazon CloudWatch
**CloudWatch** enables us to monitor and manage various **metrics** and configure **alarm actions** based on data from those metrics.

AWS services send metrics to CloudWatch, CloudWatch then uses these metrics to create graphs automatically that show how performance has changed over time.

### CloudWatch Alarms
With CloudWatch, we can create **alarms** that **automatically perform actions** if the value of a metric has gone above or below a **predefined threshold**.

For example, we can create an alarm that automatically stops an EC2 instance when the CPU utilisation percentage has remained below a certain threshold for a certain period.

### CloudWatch Dashboard
The CloudWatch **dashboard** enables us to access **all the metrics** for our resources from a single location.

## AWS CloudTrail
**CloudTrail** records **API calls** for our account. This includes information such as:
- Identity of API caller.
- Time of API call.
- Source IP address of API caller.
- Etc.

This gives us a complete history of user activity and API calls for applications and resources.

### CloudTrail Insights
**CloudTrail Insights** is an optional feature that allows CloudTrail to automatically **detect unusual API activities** in our AWS account.

## AWS Trusted Advisor
**Trusted Advisor** inspects our AWS environment and provides real-time recommendations in accordance with AWS **best practices**. These best practices are split into 5 categories:
- Cost optimisation.
- Performance.
- Security.
- Fault tolerance.
- Service limits.

For each of these categories, Trued Advisor offers a list of **recommended actions** and resources to learn more about AWs best practices.

### Trusted Advisor Dashboard
From the Trusted Advisor dashboard, we can review completed checks for the 5 categories. For each category:
- Green check indicates the number of items for which it detected **no problems**.
- Orange triangle represents the number of recommended **investigations**.
- Red circle reprsents the number of recommended **actions**.
