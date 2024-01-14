### Task 1: Sign in to AWS Management Console

### Task 2: Launching an EC2 Instance
2.1 Use N.Virginia(us-east-1) region
2.2 Click on Services and EC2 under Compute Section
2.3 Click on Launch instances button.
* Give the name as **my linux vm**
![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/3e56b941-c6b2-4a68-9fe1-dbb18cb2d2b8)


* Select Amazon Linux 2023 AMI image
    
![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/150f1db0-0fc3-4331-9c0c-4bb85a0009dc)


* Select Instance Type as t2.micro
  ![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/5be64b5d-8da0-40e9-be7d-2d3dbd061e62)

* Create a new Key Pair and give any name of your choice    
    
![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/61e11e3f-b335-4066-9287-8584baf7c9ab)


* Click Edit on Network Settings
* Select Create new Security group
* Security group name My VM SG
* Description : Security Group to allow traffic to EC2
    
![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/5234ea1a-1bcc-4f11-ae5f-bf9656f1d7a5)


* To add SSH: Choose Type: SSH
* Source: Anywhere
* For HTTP: Click on Add security group rule
* Choose Type: HTTP 
* Source: Anywhere
    
![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/be06884d-6e00-4922-aaec-b8f6ab4a5a4b)


2.4 Click on Advanced Details Under the User data section, enter the following script (which creates an HTML page served by an Apache httpd web server).

`    #!/bin/bash       
sudo su
yum update -y
yum install httpd -y                
echo "<html><h1> Welcome to Our Virtual Server </h1><html>" >> /var/www/html/index.html       
systemctl start httpd               
systemctl enable httpd		`

![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/1cd2251e-d31d-48e8-b079-5ca513f44f7e)


2.5 Keep remaining things default and click on Launch Instance
![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/b61deaf1-2b73-4060-872c-ea5c7ff6ac62)


Note down the sample IPv4 Public IP Address of the EC2 instance. 
Enter http://your IP address

![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/ce7ad363-7e88-4d76-8ae8-b8546944e9ce)


### Task 3. Creating an AMI from the EC2 Instance
3.1 In this step, our objective is to generate an Amazon Machine Image (AMI) from the currently active EC2 instance that was established in the preceding task. This procedure showcases the method of encapsulating both the setup and data of an ongoing instance into a replicable image, facilitating the swift creation of identical instances in the future.
3.2 Select the my linux vm. Click on Actions.
3.3 Under Image and templates, click on Create Image.

![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/3743ae7b-ef16-4682-b628-3cfab9b123fc)


3.4 In the pop-up window, enter the following details:

* Image Name : Enter MyEC2Image
* Image Description : Enter My EC2 Image
* Leave other details as default.
* Click on Create image button.
  
![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/9700ac75-3c60-44ee-9e49-a358629f9003)

![image](https://github.com/Asma09Akram/AWS-AMI-Creation/assets/124654068/83fe79e1-d851-441c-8e40-cd748e227714)

### Task 4: Check the newly created AMI

![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/4221dd88-9938-4995-9f4d-a0bccf0199ab)


![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/d6f9f811-3f9a-450d-8413-fdd41d20c9fa)


![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/a6135d73-8341-4351-aa84-bca11e0ad6a2)


### Task 5: Launching the EC2 Instance with the Created AMI and Testing the AMI
* Select the AMI and click on Launch instance from AMI
  
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/adc233fc-2c04-4076-905d-c10c3cfa7be6)

* Name : Enter MyEC2AMIServer
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/e48e1e5a-8ac3-4549-b2f8-6049476a01ca)

* For Instance Type: select t2.micro
* For Key pair: Select the key you created previously.
* In Network Settings :
* Auto-assign public IP: Enable
* Select Select existing security group and Select the group created earlier
* Keep rest thing Default and Click on Launch Instance Button.
* Select View all Instances to View the Instance you Created
* Launch Status: Your instances are now launching, Navigate to Instances page from left menu and wait the status of the EC2 Instance changes to running


![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/261604bc-f122-40df-8cfa-05c5b303d1be)



![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/3d58d572-7c7e-4014-85c4-15f0017dc4cb)



![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/7d053e98-a586-4864-a089-87c4fcc495b4)


![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/9f0c826f-5268-4c3b-9592-d2ccb548cfea)


![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/e81b703a-076c-45d4-80e8-d848e5b0c8fe)

* Navigate to the instances menu and copy the IPv4 Public IP address of the created EC2 instance.
* Enter the IP Address in the Browser.
* You will be able to see the HTML page displaying the message Welcome to Our Virtual Server
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/f89b9347-f13e-4f43-895f-5208607219bc)

