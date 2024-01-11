### Task 1: Sign in to AWS Management Console

### Task 2: Launching an EC2 Instance
2.1 Use N.Virginia(us-east-1) region
2.2 Click on Services and EC2 under Compute Section
2.3 Click on Launch instances button.
* Give the name as **my linux vm**
    
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/fa14b901-4109-4e54-87bd-9c8166d81e4b)

* Select Amazon Linux 2023 AMI image
    
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/a20d911b-5b2d-45c6-b841-e5665fa89cf1)

* Select Instance Type as t2.micro
    
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/c0487dca-5223-49b1-a14a-bf09f2b4f283)

* Create a new Key Pair and give any name of your choice    
    
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/69c7c5c6-253a-45dc-91a7-c11272220d48)

* Click Edit on Network Settings
* Select Create new Security group
* Security group name My VM SG
* Description : Security Group to allow traffic to EC2
    
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/ff436bde-fe8c-41e7-83dc-08e85ee806fe)

* To add SSH: Choose Type: SSH
* Source: Anywhere
* For HTTP: Click on Add security group rule
* Choose Type: HTTP 
* Source: Anywhere
    
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/a2bd00cd-3ba5-45b0-aea4-88b5bbcd77fe)

2.4 Click on Advanced Details Under the User data section, enter the following script (which creates an HTML page served by an Apache httpd web server).

`    #!/bin/bash       
sudo su
yum update -y
yum install httpd -y                
echo "<html><h1> Welcome to Our Virtual Server </h1><html>" >> /var/www/html/index.html       
systemctl start httpd               
systemctl enable httpd		`

2.5 Keep remaining things default and click on Launch Instance
![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/105c05f0-f98b-4295-8282-03bcbcf4965f)


Note down the sample IPv4 Public IP Address of the EC2 instance. 
Enter http://your IP address

![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/2c5f607b-dc6b-42b7-afd4-8b7582c61e6f)

### Task 3. Creating an AMI from the EC2 Instance
3.1 In this step, our objective is to generate an Amazon Machine Image (AMI) from the currently active EC2 instance that was established in the preceding task. This procedure showcases the method of encapsulating both the setup and data of an ongoing instance into a replicable image, facilitating the swift creation of identical instances in the future.
3.2 Select the my linux vm. Click on Actions.
3.3 Under Image and templates, click on Create Image.

![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/a4f8004c-1e5a-448c-b677-e29ababb7eed)

3.4 In the pop-up window, enter the following details:

* Image Name : Enter MyEC2Image
* Image Description : Enter My EC2 Image
* Leave other details as default.
* Click on Create image button.


![image](https://github.com/Asma09Akram/Asma09Akram/assets/124654068/62b19ed7-cf46-4261-be86-d76dc975a0ab)

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

