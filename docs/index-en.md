# ZooKeeper Community Edition Service Instance Deployment Document
## Overview
A ZooKeeper is a centralized service that maintains configuration information, names services, and provides distributed synchronization and clustering services. ZooKeeper provides the community version service on the computing nest, you can quickly deploy the ZooKeeper service and implement O & M monitoring on the computing nest without configuring the cloud host, so you can easily build your own applications based on the ZooKeeper. This topic describes how to activate the ZooKeeper Community Edition service on the computing nest, as well as the deployment process and usage instructions.
## Billing Description
The cost of the ZooKeeper Community Edition on the calculation nest mainly involves:

-Selected vCPU and memory specifications
-Disk capacity
-Public network bandwidth

Billing methods include:

-Pay-as-you-go (hourly)
-Annual and monthly packages

The estimated cost is displayed in real time when you create an instance.

## Deployment Architecture
ZooKeeper Community Edition has two architectures: stand-alone deployment and three-node deployment.

## Required Permissions for RAM Users
ZooKeeper services need to access and create resources such as ECS and VPC. If you use a RAM user to create a service instance, you need to add the corresponding resource permissions to the account of the RAM user before creating the service instance. For detailed instructions on adding RAM permissions, see [Grant Permissions to RAM Users](https://help.aliyun.com/document_detail/121945.html). The required permissions are shown in the table below.

| Permission policy name | Comment |
| --- | --- |
| AliyunECSFullAccess | Permissions to manage ECS instances |
| AliyunVPCFullAccess | Permissions to manage a VPC |
| AliyunROSFullAccess | Manage permissions for Resource Orchestration Service (ROS) |
| AliyunComputeNestUserFullAccess | Manage user-side permissions for the compute nest service (ComputeNest) |
| AliyunCloudMonitorFullAccess | Permissions to manage CloudMonitor |


## Deployment process
### Deployment Steps
Click [Deployment Link](https://computenest.console.aliyun.com/user/cn-hangzhou/serviceInstanceCreate?ServiceId=service-c679a8e504824810830e) to enter the service instance deployment page, and fill in the parameters according to the interface prompts to complete the deployment.

### Deployment Parameter Description
During the process of creating a service instance, you need to configure the service instance information. The details of the input parameters ZooKeeper the Community Edition service instance are described below.

| Parameter Group | Parameter Item | Example | Description |
| ------------ | -------- | -------------- | --- |
| Select a template | | Three-node version | Template schema type |
| Service Instance Name | | test | The name of the instance |
| Region | | China East 1 (Hangzhou) | The region of the selected service instance. We recommend choosing the region closest to you for lower network latency. |
| Availability Zone Configuration | Deployment Region | Availability Zone I | Different availability zones within a region |
| Payment Type Configuration | Payment Type | Pay-As-You-Go or Subscription |
| Select Existing Infrastructure Configuration | VPC ID | vpc-xxx | Select the ID of the VPC. |
| Select Existing Infrastructure Resources | VSwitch ID | vsw-xxx | Select a VSwitch ID. If the switch cannot be found, try switching the region and availability zone.
| ECS Instance Configuration | Instance Type | ecs.g7.large | Instance specifications can be selected based on actual needs |
| ECS Instance Configuration | System Disk Space | 40 | System disk space can be selected based on actual requirements |
| ECS Instance Configuration | Data Disk Space | 40 | Data disk space; can be selected based on actual needs |
| ECS Instance Configuration | Instance Password | ******** | Set the instance password. The password must be 8 to 30 characters long and include at least three of the following: uppercase letters, lowercase letters, numbers, and special characters from the set: ()'~!@#$%^&*-+={}[]:;'<>,.?/. |
| ECS Instance Configuration | Enable Public IP | true | Whether to enable a public IP address |

![1.jpg](images-en/1.jpg)

### Verification Results

1. View the service instance.
After the service instance is created, the deployment will take approximately 2 minutes. After deployment is complete, you can see the corresponding service instances on the page.

![2.jpg](images-en/2.jpg)

2. Access the ZooKeeper through the service instance.

![3.jpg](images-en/3.jpg)
After navigating to the corresponding service instance, you can obtain the PublicEndpoint, PrivateEndpoint, and InstallPath on the page.


### Use ZooKeeper
Please visit the ZooKeeper website to learn how to use the ZooKeeper:[ZooKeeper Usage Documentation](https://zookeeper.readthedocs.io/zh/latest/usage.html)
