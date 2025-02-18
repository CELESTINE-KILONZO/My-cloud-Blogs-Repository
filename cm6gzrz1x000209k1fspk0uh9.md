---
title: "12 Weeks Workshop Challenge"
datePublished: Tue Jan 28 2025 21:30:54 GMT+0000 (Coordinated Universal Time)
cuid: cm6gzrz1x000209k1fspk0uh9
slug: 12-weeks-w0rkshop-challenge
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cckf4TsHAuw/upload/3e2213156b33a2048319e034ea4584db.jpeg

---

**Inspired by Prasad Rao ( LinkedIn Link -** [**https://www.linkedin.com/feed/update/urn:li:activity:7044291636020834304/**](https://www.linkedin.com/feed/update/urn:li:activity:7044291636020834304/)**)**

## **aws core overview services**

in the First week,i am going to do aws core overview services. i will divide week 1 tasks into multiple days.

Lets get started💥🚀

Below is what i am going to be cover 👇

1.introduction to cloud computing

2.Aws core services part1

3.Aws core services part2

**WEEK 1 - DAY 1**

**Introduction to cloud computing**

what is cloud computing?

Cloud computing is on demand delivery of computing services such as compute servers, storage, databases, networking, software, analytics and intelligence over the Internet so called cloud.This has helped enterprises provision infrastructure in quick time compare to traditional approach where it took months to build and provision an infrastructure in a data center. It eliminates the need for enterprises to procure, configure or manage resources themselves. They only pay for what they use with zero or less administration on the infrastructure.

Types of cloud computing

`Public Cloud:` Public clouds are run by third-party cloud service providers. They offer compute, storage, and network resources over the internet, enabling companies to access shared on-demand resources based on their unique requirements and business goals. The main 3 public cloud providers are AWS, GCP and Microsoft Azure

`Private Cloud:` Private clouds are built, managed, and owned by a single organization and privately hosted in their own data centers, commonly known as on-premises.They provide greater control, security, and management of data while still enabling internal users to benefit from a shared pool of compute, storage, and network resources.

`Hybrid Cloud:` Hybrid clouds combine public and private cloud models, allowing companies to leverage public cloud services and maintain the security and compliance capabilities commonly found in private cloud architectures.

cloud computing service Models

***Infrastructure as a Service (IaaS)***: model that provides virtualized computing resources such as servers ,storage and networking over the internet .i can relate it to buying raw materials to build your own house.Here one is in control of the infrastructure and everything.

***Platform as a Service* (PaaS)**: A model that provides a virtualized application development platform.

i can relate it to renting a house for you to sleep.You focus on what to cover yourself with while sleeping while the owner of the house focuses on the well being/condition of the house.

**Software as a Service (SaaS)**: A model that provides access to software applications over the internet.

Benefits of cloud computing

1.Flexible and easy to use. User can access the environment any where from the world as long as one has access to the internet

2.Pay as you go model. Pay what you have used.This makes cloud very cost effective.

3.Cloud offers high level of security whereby security in the cloud is the responsibility of the customer and security of the cloud is the reponsibility of the cloud service provider

4.provides high level of scalability and scaling.One can always increase or reduce the number and size of resources they need.

cloud being soo much advantageous,its benefits cannot be exhausted .i just listed a few if them.

***What is AWS cloud and fundamental services of AWS***

AWS stands for Amazon Web Service. it is the top most public cloud service provider.AWS is the world’s most comprehensive and broadly adopted cloud.it offers over 200 fully featured services . Millions of customers, startups, largest enterprises and leading government agencies are using AWS to lower costs, become more agile, and scale faster.

Having discussed the cloud basics, i will get started with the Week 1 workshop lab.

Here is the link for the workshop [click me](https://catalog.workshops.aws/general-immersionday/en-US)

Relevant environments to use in the 12 weeks aws workshop challenge:

1.aws account- in case you do not have one use this link to create one:[https://www.youtube.com/watch?v=3sqAzIb3rRw](https://www.youtube.com/watch?v=3sqAzIb3rRw)

***Note:***

a) Please **DO NOT** forget to set up billing alarm to avoid any surprise bills.

b) Set up MFA set up for your root user and create another admin user for the same. you can use this video - [https://www.youtube.com/watch?v=OVaYHdYfaH4](https://www.youtube.com/watch?v=OVaYHdYfaH4).

c) Create an IAM User to for this workshop. Create an IAM user and set up the MFA by following the above youtube video.

2.aws workshop studio-here is the links to use for sign in:[https://catalog.us-east-1.prod.workshops.aws/sign-in?redirect=%2Fjoin](https://catalog.us-east-1.prod.workshops.aws/sign-in?redirect=%2Fjoin)

you can use any relevant link to create a working environment.

Having managed to create the required environment,that is a great achievement🎖.

This completes the Week 1 -Day 1 💯✅

**WEEK 1 - DAY 2**

For Day -2, i will discuss the basic modules and foundational services of AWS.

Basic modules consist of the following agenda:

1. Compute - Amazon EC2
    
2. Network - Amazon VPC
    
3. Security - AWS IAM
    
4. Monitoring - Amazon CloudWatch
    
5. Database - Amazon RDS
    
6. Storage - Amazon S3, Amazon Elastic File System
    

i will go through each module steps by step in the labs.

1. ***Compute - Amazon EC2***
    

what is ec2 🤔?

EC2 stands for elastic compute cloud.It is a web service that allows users to run virtual servers in the cloud.For any application to be built,ec2 is highly required to deploy and run the application.

ec2 features

1.Instances

Virtual servers which one accesses in order to build and run applications in cloud.

2.Amazon Machine Images (AMIs)

Preconfigured templates for your instances that package the components you need for your server (including the operating system and additional software).

3.Instance types

Various configurations of CPU, memory, storage, networking capacity, and graphics hardware for your instances.There are different Instance families like general-purpose, storage optimized, Compute-optimized.

4.Amazon EBS volumes

This is a virtual disk which is attached to the ec2 instance and it enables data to persist even if an instance is terminated.EBS snapshots are used for backup.

5.Instance store volumes

Instance store volumes offers temporary storage of data that is deleted when you stop, hibernate, or terminate your instance.

6.Key pairs

Secure login information for your instances through ssh. AWS stores the public key and the customer store the private key in a secure place.

7.virtual private cloud(vpc)

security group which is a vpc component is very important when creating an ec2 instance in cloud.security group is a virtual firewall that allows you to specify the protocols, ports, and source IP ranges that can reach your instances and the destination IP ranges to which your instances can connect.

Having discussed what an ec2 is,lets proceed to the hands on lab👌:

### **step 1: Select EC2 from the console**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738078016568/5f03b6f2-522e-4569-b9dd-79995db9f65d.png align="center")

### **step 2: select key pairs**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738081737296/c65a0ce2-993c-4388-8b0f-763a0d66ef82.png align="center")

### **step 3: Click on create key pair**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738082363001/196e48cd-00e5-478d-800c-814b9da9c8e8.png align="center")

### **step 4: A dialog box as shown below will be opened**

Provide the name of your key pair as you wish.

for the key pair type select RSA.Incase you need a more robust,more performance and more secure keypair type kindly go for ED25519.

when you create a key pair,the private key is stored in your local work station while the public key is stored at aws default location i.e ~/.ssh/authorized\_keys .

for the Private key file format, .pem format is used in Linux or mac distributions while .ppk is used in windows.

for my case i will use .pem Private key file format and then finally proceed to create my key pair

finally click on create key pair

Tags are important when creating key pair because they allow you to add descriptive metadata to the key, making it easier to identify, categorize, and manage within your system especially when dealing with a large number of key pairs, by attaching key-value pairs that indicate the purpose, environment, owner, or other relevant information about the key pair.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738085491436/c4f24fb8-4989-46c5-bb93-8af6180b40d9.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738086408556/25750dde-7eb3-4c1b-886c-0510f7d7f55e.png align="center")

### **step 5:Navigate to the search bar and search for EC2**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738086942995/7b4ba0b4-ac02-431f-8927-5b6b61d074e5.png align="center")

### **step 5: It’s now time to create our Ec2 instance.choose launch instance.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738087361933/8d853a9a-5abc-43f1-a07a-cc1d55965b9e.png align="center")

### **step 6: Filling in the instance credentials**

Provide the name for the instance.For the AMI any but wanna use Amazon linux.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738088403137/3c82ccb3-f86a-408d-a33f-6ef04e59c54b.png align="center")

upon selecting the AMI,a drop down for the categories of selected AMI is displayed.You choose any based on your use case.For the architecture,Choose **x86\_64** for compatibility and high-performance needs and **ARM (64-bit)** for cost efficiency, energy savings, and workloads optimized for ARM architecture (e.g., Gravitation instances).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738089803829/1b8ef237-7659-47de-8610-bcf823aca5d1.png align="center")

select the instance type from the drop down and the select the keypair we created from the drop down i.e lab1\_keypair.One can still decide to create a new key pair

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738090732900/7013ccce-1f60-4ab5-b331-062cb99e8cb0.png align="center")

### **step 6: Configure the Network Settings**

For the vpc,subnet and security group you can choose from the one which is already created or use a default one from the drop down.Name the security group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738091239620/fe813168-1d3b-4e0b-9a5d-e9939db87285.png align="center")

for the security group add inbound security group rules since security group is stateful.

stateful means that if a traffic gets in,it can still get out automatically

stateless means that whatever traffic which gets in must be allowed get out

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738091736856/39268c12-603a-40e9-adcc-9a82c654547e.png align="center")

### **step 6: configure the EBS storage**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738094074284/2088d0ad-d8db-406a-88c0-186021205d55.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738095331013/4ec8c708-e9f0-4bfb-9170-caf4a651e432.png align="center")

Click the **Meta Data** version dropdown and select \*\*V2 only (token required)\*\*Enter the following values in the User data field

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738096052818/9100cf68-669c-4d25-86be-9f5050045273.png align="center")

### **step 7: Launching an EC2 instance**

select Launch instance on the bottom right

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738096578481/42f5d2bf-1398-414b-b74b-d84f407d870c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738096871723/d8c43bb6-24f8-49ca-9374-4ca4e24d1417.png align="center")

### **step 8:Navigate to the dashboard and select ec2 and finally select running instance**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738097678061/f7035f0b-e2ba-4d3e-9a31-a02a824a3b76.png align="center")

### **step 9: select the running ec2 instance yo created then paste the public dns in the browser**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738098300961/4c3f3690-5ced-4b8b-979f-86cf89b705ba.png align="center")

Boom💥💥.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738098564300/d0d4591b-d9d4-4556-b7fe-50509336bdd2.png align="center")

Congratulations👏👏.This is how one deploys a server and launches a website in it within minutes.

If you are stuck somewhere, please check your configurations and validate it.Clean up all resources to avoid surprise charges.

**WEEK 1 - DAY 3**

Today i am going to discuss on how to connect to an EC2 instance.

1.SSH using SSH client

2.connect using EC2 instance connect

3.connect using session manager

4.Connect to your instance for windows OS using putty

## a) SSH using SSH client

### step 1: select the running instance you would like o connect to and then click connect

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738170313832/cb70b3d6-9ed6-4de7-ac9e-c9531904598e.png align="center")

### step 2:Select ssh client.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738170542213/08d0bad8-9ae5-4d87-9c14-fb658710c71a.png align="center")

### step 3:navigate to your terminal and move to the directory to where your .pem file was saved in your local computer.copy chmod 400 “mine.pem”and click enter to **set the file permissions** for `LAST.pem`.Copy ssh -i "LAST.pem" [ec2-user@ec2-3-239-86-196.compute-1.amazonaws.com](mailto:ec2-user@ec2-3-239-86-196.compute-1.amazonaws.com) and paste to the terminal then click enter to **connect to an AWS EC2 instance via SSH** using a private key (`LAST.pem`).

### Here comes the output

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738171913917/0bc9655c-0584-4685-abe4-fa55e716c8ff.png align="center")

## b).SSH using EC2 instance connect

### step 1: select the running instance you would like o connect to and then click connect

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738170313832/cb70b3d6-9ed6-4de7-ac9e-c9531904598e.png align="left")

### step 2:Select EC2 instance connect.Click connect using EC2 instance connect and finally click connect button at the lower right.If your vpc is t the private subnet,use connect using EC2 instance connect endpoint.Ensure you create a endpoint t the vpc.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738310272689/5b0740c9-68fb-4db7-9977-7f79661cd401.png align="center")

### i have finally connected to my instance

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738227952775/545e7c39-2d62-4e09-b306-2f331835399a.png align="center")

## c)SSH using session manager

### step 1:navigate to the console and the choose IAM

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738228510543/45a08e5b-2c82-471e-b4d4-1726f381e605.png align="center")

### step 2:under IAM select roles and then click create role

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738229405658/4f9c0e1b-b3cc-4e53-9c29-620ddd30bf86.png align="center")

### step 3:select aws service

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738229641859/abb44090-3fcf-4cdb-bc8c-e487ea58340b.png align="center")

### step 4:chose the service to which your role shall be attached to and for this case we choose ec2 then click next

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738229741904/f899aafc-657b-46f1-8d34-7d6a56eb2a2e.png align="center")

### step 5:under permissions search for AmazonSSMInstanceCore then elect it.At the lower right select next

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738229924306/4506b239-3de8-48bc-8ad6-e5b7b108b113.png align="center")

### step 6:Name the role

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738230070634/7dd61f93-6fdb-4124-9983-964352ddadea.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738230330418/29b65c30-964b-4821-bf40-ce8e40916648.png align="center")

### step 7:At the lower right click create role

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738230362512/d929699f-5c63-462c-a48f-19bf174f16ca.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738230446233/eb14e194-ea0e-420b-b86f-b6ed49064ab6.png align="center")

### step 8:Check the box of the instance you would like to connect to and then click on actions.Under actions select security.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738230609355/0d2e7ca1-d540-40aa-b799-6c598f10ee88.png align="center")

### step 9: Select Modify IAM role

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738230673600/7255744f-59a7-4233-960f-48552967e0a8.png align="center")

### step 10: Select the role you just created

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738231723062/80095cc6-be4f-4d36-9c27-96c4f2e19b0e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738231812360/38556588-fe2d-4394-b36a-0bb118b8c4ce.png align="center")

### step 11:Check the box of the instance you would like to connect and then click connect.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738231886021/7fbebdf7-9f80-422f-9e8d-848b19449487.png align="center")

### step 11:navigate to session manager.Click connect at the bottom left

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738307732246/c91ab37e-8230-4166-a555-abb75a8bc187.png align="center")

### We have finally connected to the ec2 instance through session manager

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738308050679/86554014-73b3-48bb-8246-c6bfd99b45ba.png align="center")

**WEEK 1 - DAY 4 :AWS Auto scaling**

Today i am going to discuss about auto scaling and load balancing.

Auto scaling is very crucial in any busy organization or even a business.

it ensures that resources can automatically scale up when there is high traffic and scale down incase the traffics is low .

load balancing ensures that traffic is only sent to the healthy resources inorder to reduce delays.

for this we are going to host a web server which shall scale up to 3 more servers incase the cpu usage gets above 25%.

Below is the aws auto scaling lab architecture:

**NOTE:** - This diagram is from AWS page ( Link - [https://catalog.workshops.aws/general-immersionday/en-US/basic-modules/10-ec2/ec2-auto-scaling/ec2-auto-scaling/2-ec2-as](https://catalog.workshops.aws/general-immersionday/en-US/basic-modules/10-ec2/ec2-auto-scaling/ec2-auto-scaling/2-ec2-as)), but i created our resources in N.Virginia region and used 1 ec2 instances only.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738563090849/2cc8c9de-b45a-494f-a268-0341716fc52e.png align="center")

Before doing the lab, let us understand what is Elastic Load balancer.

***Elastic Load Balancer***

Elastic Load Balancing automatically distributes your incoming traffic across multiple targets, such as EC2 instances, containers, and IP addresses, in one or more Availability Zones. It monitors the health of its registered targets, and routes traffic only to the healthy targets. Elastic Load Balancing scales your load balancer as your incoming traffic changes over time. It can automatically scale to the vast majority of workloads.

Elastic Load Balancing supports the following load balancers:

1. Application Load Balancers
    
2. Network Load Balancers
    
3. Gateway Load Balancers
    
4. Classic Load Balancers
    

Details on each load balancer is available in AWS documentation - [https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)

Here we created a application load balancer. `Application Load Balancer (alb)` An Application Load Balancer functions at the application layer, the seventh layer of the Open Systems Interconnection (OSI) model. After the load balancer receives a request, it evaluates the listener rules in priority order to determine which rule to apply, and then selects a target from the target group for the rule action. You can configure listener rules to route requests to different target groups based on the content of the application traffic. Routing is performed independently for each target group, even when a target is registered with multiple target groups. You can configure the routing algorithm used at the target group level. The default routing algorithm is round robin; alternatively, you can specify the least outstanding requests routing algorithm.

lets get started;

### Create an Ec2 instance.For my case i used cloud formation to make it faster

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738563701903/c5eff2a6-5d4e-4cc6-ae72-aed083be3b2d.png align="center")

### copy the public iv4 dns to the browser

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738563871856/db2df694-c66a-48c7-9f0c-927d21f7c69f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738563914664/04bd4947-51ec-4f05-bdf3-6d7efee0d5bf.png align="center")

### Here is my target group

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738564309639/a042c083-3961-4017-8335-ecb353480d7b.png align="center")

### auto scaling group

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738564516183/c6195604-f830-431f-879b-3cf10e4fc0dc.png align="center")

### active load balance

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738564682311/e6478e2a-3100-4e41-8fe9-f0b2b71c3abd.png align="center")

### security group for the load balancer

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738564791731/990d687f-ba5e-481f-90da-827e22c4adf0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738564859482/526bd700-bfb5-4d57-9000-14499d915e3e.png align="center")

### To check your application is accessible from load balancer or not, take the load balancer URL and access it web browser.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738564951392/c88705a5-16a5-4b40-a007-09f16a770ce7.png align="center")

try increasing the cpu load to above 25% and keep n refreshing the tab for your browser

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738565648246/7dff5e98-daec-4cd2-8b9b-ba9cacaf014e.png align="center")

This marks the end of week 1 challenge

We will start the Week -2 challenge.