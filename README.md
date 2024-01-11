# AWS-AMI-Creation

### In this Repo we will learn how can we create AMI from EC2 Instance
## Lets Understand what is AMI
An Amazon Machine Image (AMI) is a pre-configured virtual machine image, which includes the operating system, application server, and applications that have been set up on an Amazon Elastic Compute Cloud (EC2) instance. AMIs are used for creating and launching EC2 instances, providing a quick and efficient way to replicate and deploy a consistent computing environment. AMIs can also include data and configurations, allowing users to save time by starting new instances with predefined setups.

![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/ccb54a49-83d0-48a8-ba87-c51afe604adc)


An Amazon Machine Image (AMI) is a foundational concept in AWS, serving as a blueprint for the creation of virtual servers known as EC2 instances. Essentially, AMIs act like customizable templates preloaded with an operating system and specific software configurations, defining the environment in which users operate.

AMIs are meticulously categorized based on region, operating system, system architecture (32 or 64 bit), launch permissions, and whether they are backed by Amazon Elastic Block Store (EBS) or the Instance Store.

Comprising a template for the root volume necessary for an instance, an AMI typically includes components such as the operating system, an application server, and various applications. When launching an instance, the root device volume contains the image required to boot the instance.


Access to AMIs is controlled by permissions, ensuring that only the appropriate AWS accounts can launch instances from specific AMIs. 

Users have the flexibility to choose AMIs provided by AWS, the user community, or the AWS Marketplace. Additionally, users can create their own AMIs and share them within the same region or across regions, offering a high degree of customization and collaboration.




## Steps we will follow in order to create AMI from EC2 Instance

### 1. First we will create an EC2 instance 
### 2. Create an AMI using the instance which created
### 3. Launching the EC2 instance created with the created AMI and testing the AMI.
