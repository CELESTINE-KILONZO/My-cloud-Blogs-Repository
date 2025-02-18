---
title: "@Week 3 of 12 weeks aws workshops challenge"
datePublished: Wed Feb 05 2025 19:43:14 GMT+0000 (Coordinated Universal Time)
cuid: cm6sbgbku000109jpgn1nbcea
slug: week-3-of-12-weeks-aws-workshops-challenge
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cckf4TsHAuw/upload/5d6fc6b9b5e0d2e54c561cc2ed4c72cb.jpeg

---

# AWS Networking

## WEEK 3 DAY 1

Being the third week we are going to check on aws networking.Networking in cloud enables one to create a secure architecture.

Importance of aws networking

* **Scalability:**
    
    Easily scale your network infrastructure up or down based on application demands without the need for manual hardware management.
    
* **High Availability:**
    
    Leverage multiple Availability Zones to ensure continuous network access even in case of regional outages.
    
* **Security:**
    
    Control access to your resources in the vpc through network security groups .A security group defines the necessary inbound and outbound rules to ensure that the right traffic is directed in and out of your instance .
    
* **Flexibility:**
    
    Choose from a wide range of networking services like Elastic Load Balancing, Amazon Route 53, and Transit Gateways to tailor your network architecture to specific needs. One can only use what they want at a given time
    
* **Cost Efficiency:**
    
    Pay only for the network resources you use, eliminating the need for upfront hardware investment.
    
    You only deploy resources once you need them and when done with them you destroy them
    

**Amazon VPC (Virtual Private Cloud):**

A logically isolated virtual network within AWS where you can launch your resources with customized IP address ranges and security settings.

## components of vpc

1.Subnet-This is a subdivison of a large network.imagine of a large organisation which has several departments.For this case we have organisation network then each department is allocated their own subnet.

2.Route table-this is a table that directs data packets to their correct destination.

3.Network Access control list-this is a firewall which monitors traffic at the subnet level.NACL uses both inbound and outbound rule(stateless).it does not **remember past interactions** and keeps track of session information..Any traffic which comes in has to allowed out.

4.security group-this is a firewall which monitors traffic at the instance level.it makes use of inbound rule(stateful).**it remembers past interactions** and keeps track of session information.Any traffic which comes in is automatically allowed out

5.Nat gateway-it enables services deployed at the private subnet to be accessed over the internet

6.internet gateway-A component which enable your vpc to communicate to the internet

7.elastic ip-Elastic IP address is a public **static IPv4 address** which is reachable from the Internet. Basically Elastic IP addresses are used by AWS to manage its dynamic cloud computing services. Within the AWS infrastructure, customers have virtual private clouds (VPC), within the VPCs, users have instances. So when you launch an EC2 instance, you receive a Public IP address by which that instance is reachable from internet. Once you stop that instance and restart the instance you get a new Public IP for the same instance. So it's basically a problem to connect your instance from internet for not having a static IP. To overcome this problem, *we attach an Elastic IP to an Instance which doesn't change after you stop / start the instance*.

8.VPC peering-this is a network connection between two vpc which enables one to direct traffic to another vpc and share resources using a private ip address

9.VPC endpoints-A VPC Endpoint allows you to privately connect your Virtual Private Cloud (VPC) to AWS services without using the internet, NAT gateways, VPNs, or even Direct Connect. There are two types of vpc endpoints.Interface and gateway vpc endpoints.interface Endpoin**t** uses AWS Private Link to create a private IP in your VPC.Interface Endpoin**t** Requires an Elastic Network Interface (ENI) in a subnet for instance,Connecting to AWS Secrets Manager from a private subnet .Gateway Endpoint uses a gateway to route traffic from the VPC to AWS services.for instance,Allowing EC2 instances to access S3 without internet.

10. aws transit gateway-improves network performance in the cloud by acting as a unified center point for associating various virtual private clouds (VPCs) and on-premises networks. It permits associations to unite their organizational architecture and streamline routing.
    

lets get started with hands on🚀🚀🚀

## 1.VPC CREATION

### 1.Navigate to the console

![Step 1 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/34711039-63b5-4f48-8c1b-7d11364f6424/a19989ef-e034-43ef-a165-1f87a14e691a.png?crop=focalpoint&fit=crop&fp-x=0.2794&fp-y=0.4261&fp-z=1.4634&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=160&mark-y=146&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz02NjImaD0zNzMmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 2\. Click on VPC

![Step 2 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/3c4d2e5b-48f4-4c99-95c9-9a3d803d1e4f/ae96862b-3550-4b02-8194-4fcc2d3c8be4.png?crop=focalpoint&fit=crop&fp-x=0.1252&fp-y=0.4449&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=416&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz04MCZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 3\. Click on Create VPC

![Step 3 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/80f1aa10-4a5d-440c-bde1-5fd0df09ef18/6c943080-2a13-4144-bd8a-2af055917594.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=238&mark-y=78&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05MiZoPTI4JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 4\. Click on Resources to create…

![Step 4 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/f0d3b1ab-40ed-421a-b684-a898cc28e9af/bb9b5ecf-6dde-4285-abde-7746165c4cbb.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=63&mark-y=190&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0zNTcmaD00NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Select VPC only

![Step 5 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/c1c499a4-eeea-4420-9243-e8368589deed/5025f161-23e6-4b04-818d-a2f427e39394.png?crop=focalpoint&fit=crop&fp-x=0.0798&fp-y=0.3283&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=263&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 6\. Type your vpc name

![Step 6 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/9359da16-0e6a-4c39-be1b-7a4e7eeb9c6b/9df6171b-a433-4f35-9744-1b80eaa16a0b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=76&mark-y=275&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02MDMmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 7\. Click on Create VPC

![Step 7 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/599cdda2-2ae1-4460-bd29-54c16fedc450/b751a602-f75d-4de4-acfd-6f2cdbc02100.png?crop=focalpoint&fit=crop&fp-x=0.7949&fp-y=0.9050&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=416&mark-y=356&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zNjgmaD0xMTImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 8\. vpc availability

![Step 8 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/8fd9f0b1-b987-453f-abb4-27114d0de0b1/8bf0c454-b3e1-4407-92c8-6f2568075d2a.png?crop=focalpoint&fit=crop&fp-x=0.4932&fp-y=0.3400&fp-z=1.8076&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=403&mark-y=180&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zOTQmaD0zMDQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 9\. vpc details

![Step 9 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/925c2b39-5069-469d-80ae-7134c8ecdc41/788cbead-ab0d-4737-b221-5240c2e74000.png?crop=focalpoint&fit=crop&fp-x=0.4134&fp-y=0.4637&fp-z=1.0125&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=15&mark-y=35&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz05NzUmaD01NTQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 10\. Click on Actions

![Step 10 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/1300be65-1fc9-4e71-9359-238402eec9e0/b7254560-572b-491e-8a50-2ecf3d05932a.png?crop=focalpoint&fit=crop&fp-x=0.9562&fp-y=0.1254&fp-z=2.9222&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=918&mark-y=203&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTcmaD04MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 11\. Click on Edit VPC settings

![Step 11 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/60291c27-f121-48eb-8e99-dd79fed28c30/9e9023cd-9e91-4353-a0dc-c0d40c1a1f86.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1012&mark-y=119&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNzgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 12\. Click on DNS settings

![Step 12 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/2bc2bc61-f633-438c-a418-b0605407b8b4/52dd4bef-d53d-4692-8ae2-ecd36a87e3c5.png?crop=focalpoint&fit=crop&fp-x=0.0620&fp-y=0.5293&fp-z=2.6239&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=67&mark-y=300&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTUmaD02MyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 13\. Enable DNS host names…

![Step 13 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/9f9f8b09-b052-4f7d-8a9e-2a1f899d41e1/09c25721-5a78-40d8-afe9-631f5bbccd0f.png?crop=focalpoint&fit=crop&fp-x=0.0292&fp-y=0.6073&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=78&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 14\. Click on Save

![Step 14 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/8ffc3b8f-ba21-44ac-a12e-800605f18fd0/953abdd7-c9e1-45de-b29d-07fc9da1c5fb.png?crop=focalpoint&fit=crop&fp-x=0.9679&fp-y=0.7913&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=929&mark-y=276&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yMzQmaD0xMTImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 15\. here is our vpc

![Step 15 screenshot](https://images.tango.us/workflows/edad9624-0755-4d95-b519-c2987c0d7d0a/steps/4a54312b-f84a-4c55-b8bc-27f036c02e60/38c1ba84-65b9-49b7-a77f-b767e2532bd1.png?crop=focalpoint&fit=crop&fp-x=0.5782&fp-y=0.1237&fp-z=1.1964&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=6&mark-y=77&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTg5Jmg9NDImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

## 2.SUBNET CREATION

### 1\. Navigate to the vpc dashboard

![Step 1 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/f31e756b-e92d-41eb-8f80-e1f21f355137/bb4f64ca-902e-474f-82de-e9f5b5a6bef2.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=3&mark-y=62&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOTMmaD01ODImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 2\. Click on Subnets(our first subnet)

![Step 2 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/4c027665-8139-459d-887d-0403897f14f5/38ed6987-007d-4b82-9800-7ca584e58fe9.png?crop=focalpoint&fit=crop&fp-x=0.0347&fp-y=0.3382&fp-z=2.9561&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=55&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMzYmaD01OCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 3\. Click on Create subnet

![Step 3 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/e416fcaf-320c-46bf-a077-09754bde3a1e/7b5b62a1-60fb-46e5-8e48-ba943c6df7c3.png?crop=focalpoint&fit=crop&fp-x=0.9455&fp-y=0.1231&fp-z=2.9222&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=854&mark-y=198&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zMDkmaD04MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 4\. Click on the vpc you want to create the subnet in

![Step 4 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/feb922ae-b593-4b38-a6cb-bd163f99c738/01e4358e-1279-4dd4-8a64-f3fed2f72c86.png?crop=focalpoint&fit=crop&fp-x=0.3537&fp-y=0.2743&fp-z=1.0958&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=62&mark-y=184&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz04MDYmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Type subnet name

![Step 5 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/99020b86-d21d-49df-babb-c5595e8cde4e/f1e81d45-925b-41bb-af48-488318e4bafb.png?crop=focalpoint&fit=crop&fp-x=0.3605&fp-y=0.4232&fp-z=1.1044&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=77&mark-y=295&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz04MDImaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6.input the IPV4 subnet CIDR block

![Step 6 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/d29b825a-943d-40e1-b6f0-9dd9f9f7d548/fc3ea20b-481d-46cc-a966-5c464b1b0663.png?crop=focalpoint&fit=crop&fp-x=0.3342&fp-y=0.6905&fp-z=1.1148&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=48&mark-y=421&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OTkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 7\. Click on Create subnet

![Step 7 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/7663d56b-31c4-4738-8c2f-61c0d73505a3/6610c146-f789-4255-9758-d5669dc03c39.png?crop=focalpoint&fit=crop&fp-x=0.9384&fp-y=0.9191&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=692&mark-y=393&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MjQmaD0xMTImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 8\. here is our subnet

![Step 8 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/ca31ee75-5768-48f3-9425-977e8a420f45/f2722d12-0934-493c-9642-9d094d5c252c.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=191&mark-y=33&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMDAxJmg9MzUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 9\. Click on Create subnet(second subnet)

![Step 9 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/a28c9598-0877-4c87-bba5-b5dec7f097ff/0a4b3db4-67d3-437a-a82a-9f6d9acd35b8.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1082&mark-y=9&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMDYmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 10\. Click on Select a VPC

![Step 10 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/103edc07-5de8-42f2-93fd-b0efc496cba9/591910d5-a279-41ef-b1a3-3252b2bec846.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=13&mark-y=138&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NzImaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 11\. Click on the vpc you want to create the subnet in

![Step 11 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/e090adac-ff89-4dfb-b1c4-97e66583239a/a3095fa2-e334-40ab-8c1b-149394d68624.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=16&mark-y=186&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NzAmaD00NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 12\. input the IPV4 subnet CIDR block

![Step 12 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/e1e7bce4-1c90-4bad-9fa7-570b8e1079c9/e4b1bb95-76af-4210-a3e9-f6570fc207a5.png?crop=focalpoint&fit=crop&fp-x=0.3342&fp-y=0.6624&fp-z=1.1148&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=48&mark-y=400&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OTkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 13\. Click on Create subnet

![Step 13 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/4baaf91d-419d-41f0-bf2e-811a10cdd4a8/ed39867c-a2b2-4157-8198-f9f1d7183549.png?crop=focalpoint&fit=crop&fp-x=0.9384&fp-y=0.9191&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=692&mark-y=393&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MjQmaD0xMTImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 14\. Click on Create subnet(third subnet)

![Step 14 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/cc72b203-f57a-4558-9e72-c425fdffd2e8/caabb080-8c1d-4e9a-8191-05eece8c0077.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1082&mark-y=35&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMDcmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 15\. Click on Select a VPC

![Step 15 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/2d095f9c-49dd-43a4-9c9d-fc17e885de1d/13e1b883-1b93-4d6f-94f1-a8a048638161.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=46&mark-y=135&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NTEmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 16\. Click on the vpc you want yo create the subnet in

![Step 16 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/31224960-f518-4a5e-97da-d3ac61ef121d/e386c71a-fb79-4fdd-8105-efef0dd6a93d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=45&mark-y=183&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NTEmaD00NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 17\. input the IPV4 subnet CIDR block

![Step 17 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/5bc07992-f368-40b2-923f-5befeca87bcf/062f17b3-2e88-484b-aebb-8580713c70bd.png?crop=focalpoint&fit=crop&fp-x=0.3342&fp-y=0.6729&fp-z=1.1148&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=48&mark-y=408&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OTkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 18\. Click on Create subnet

![Step 18 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/827c7dd6-3537-4f30-8df7-25906fcdd60a/bfbf604c-5359-4d66-be9f-af8ad6cc83a1.png?crop=focalpoint&fit=crop&fp-x=0.9384&fp-y=0.9191&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=692&mark-y=393&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MjQmaD0xMTImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 19\. Click on Create subnet(forth subnet)

![Step 19 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/703d2196-368b-4092-97d3-71c6b3a86c39/679e68cf-bfea-479a-a07b-ecc476d47728.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1082&mark-y=35&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMDYmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 20\. Click on Select a VPC

![Step 20 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/d65c30c7-cdac-409b-b13a-15af05431009/a30a1f9b-9553-4148-932c-bc32e9c0e29b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=56&mark-y=140&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDQmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 21\. Click on the vpc you want to create the subnet in

![Step 21 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/592ccb21-582e-49c3-b389-f5a6d331563e/1602d5c0-6575-4583-a5cd-f30670809065.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=51&mark-y=186&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDcmaD00NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 22\. input the IPV4 subnet CIDR block

![Step 22 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/c07405f1-24a9-4f30-8075-9761d7850102/7939d13d-7ddc-403a-9aae-7e64cf0ceaa2.png?crop=focalpoint&fit=crop&fp-x=0.3342&fp-y=0.5170&fp-z=1.1148&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=48&mark-y=318&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OTkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 23\. Click on Create subnet

![Step 23 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/a804230e-c704-4588-90cb-43d637ad1bf3/02ec4095-ef23-4996-b21b-88248ff290c1.png?crop=focalpoint&fit=crop&fp-x=0.9384&fp-y=0.9191&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=692&mark-y=393&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MjQmaD0xMTImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 24\. Here are our 4 Subnets

![Step 24 screenshot](https://images.tango.us/workflows/2dc2f4bd-bf37-49ee-b7f5-6a01e15b0577/steps/c1951525-20da-469b-b732-7fa251128ce0/62f01b77-ca72-4a5b-ae03-120acf98ba59.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

## 3.NETWORK ACCESS CONTROL LIST(NACL) CREATION

### 1\. For the subnets created,check LAB3 PUBLIC SUBNET1

### 2\. Click on Network ACL

![Step 2 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/2441ea3f-7050-47fe-8301-5f5038f86303/507743cb-d6a1-491b-a78e-75549dfb9681.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=468&mark-y=239&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMDImaD0zNCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 3\. Click on Inbound rules

![Step 3 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/d99edad9-d4f9-4d6c-a354-318cbb933a4d/de025e26-bc58-4652-bf21-e86e0bae32f8.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=193&mark-y=370&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05ODYmaD03OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 4\. Click on Outbound rules

![Step 4 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/9f03806b-dae3-4dfd-8fb2-e3078fbed16c/73f97ae2-a553-4cc2-abbe-3a8353e2453b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=198&mark-y=520&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05ODAmaD03OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6\. At the dashboard Click on Network ACLs

![Step 6 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/38bbeee0-87ef-40de-bcb6-dac9941c616f/c7cb436f-42cb-457d-b8a9-2abe1c73b7e0.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=19&mark-y=449&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NSZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 7\. Click on Create network ACL

![Step 7 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/9fea7d6d-c0e2-4ec1-a0df-b8632622f7ff/a52e6adf-e82b-448f-b822-587b9f28f88e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1050&mark-y=35&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMzgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 8\. enter the name you wish to give to your NACL

![Step 8 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/8b283c74-5689-4f55-90dc-c3262fc194ac/c5036f23-5266-4a19-84f2-057a5d7a8d9e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=47&mark-y=158&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NTAmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 9\. Click on Create network ACL

![Step 9 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/ca696327-5961-4e31-b7ad-469d8958b8c6/184e26c7-eed8-4ec0-9fed-bded771fb9a5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1054&mark-y=424&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMzcmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 10\. Click on Details…

![Step 10 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/35304071-d00c-4cd6-96b3-dd248e7a61b3/4f02dcb6-581b-469f-bb07-ceddcb3d4f30.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=186&mark-y=448&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05OTQmaD0zNiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 11\. Click on Subnet associations

![Step 11 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/a8d6d578-691d-41ee-92d3-88caca50c3d6/aa9bacf0-a9b6-4029-9417-742c1bafe97e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=515&mark-y=436&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNDImaD0zNCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 12\. Click on Edit subnet associations

![Step 12 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/1f8247e2-390b-4efe-8a0b-260bcf9e497e/dd3a587a-ad4a-4b6a-86c0-b77381614d3d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1015&mark-y=343&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNjAmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 13.Check the 4 subnets you want to associate to the NACL

![Step 13 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/23fb90d9-6ed6-4c88-befc-5f0413e74c1e/7d2d126b-2c35-4d3e-909a-5bb54a600f59.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=46&mark-y=117&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

14. ### Here is the output.Our subnets have been allocated to the NACL
    

![Step 14 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/6964cfff-485e-45ab-9bea-b8abce191d49/9565e5b2-be1a-47e8-b7e5-f6f3d63b5047.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 15.Check the NACL we created

![Step 15 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/fd5eb226-e23e-4750-9245-eadc7eee9486/db6ab49b-c0c8-4ee9-9674-96efd72a39d9.png?crop=focalpoint&fit=crop&fp-x=0.1830&fp-y=0.2392&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 16\. Click on Inbound rules

![Step 16 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/77e709dd-24b9-4066-9ebd-c36729a68e48/72dadd6c-0aa5-43f2-9047-6883358731e0.png?crop=focalpoint&fit=crop&fp-x=0.2758&fp-y=0.4848&fp-z=2.5670&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=462&mark-y=287&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNzYmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 17\. All inbound rules are denied by default

![Step 17 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/ac65372c-6246-4493-80cc-f29f8c526b78/111990ba-b802-4996-824d-e53ca011d9bc.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=196&mark-y=395&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05OTUmaD01NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 18\. Click on Edit inbound rules

![Step 18 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/595a09de-708f-4edc-85da-7332eb2deefb/5057c6d3-dfb8-4dd3-8eec-f8713ef0fe4e.png?crop=focalpoint&fit=crop&fp-x=0.9247&fp-y=0.5862&fp-z=2.9222&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=747&mark-y=291&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zNzgmaD04MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 19 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/8356c00f-9203-4180-8a68-ec9e54a8ae0a/44eb0a5e-9d68-4ceb-bb68-29cd96637f79.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=29&mark-y=38&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMzgmaD0yNSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 20\. Click on Add new rule

![Step 20 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/b48b576a-b122-48a9-aa27-91f29fc152e8/b01ae363-ff30-4e1e-be4d-161442ca5e2c.png?crop=focalpoint&fit=crop&fp-x=0.0902&fp-y=0.3294&fp-z=2.5930&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=147&mark-y=296&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNjcmaD03MyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 21\. Type the rule number

![Step 21 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/38c46366-03ee-450f-b421-bd3aa6e196b1/9f4fac87-5609-4f6f-81c3-6491fd6ef58b.png?crop=focalpoint&fit=crop&fp-x=0.0837&fp-y=0.2673&fp-z=2.6833&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=153&mark-y=295&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yMzQmaD03NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 23\. Click on Allow

![Step 23 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/d4fb54ec-0c52-4ad8-8afe-12f592c43479/a74101c9-f88c-4f88-8894-658ed3721378.png?crop=focalpoint&fit=crop&fp-x=0.8251&fp-y=0.3072&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=338&mark-y=287&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01MjMmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 24\. Click on Save changes

![Step 24 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/3f356a63-ecfe-4182-84ca-781fa4dc97f6/f3c152df-4006-4262-822d-91c0565bb941.png?crop=focalpoint&fit=crop&fp-x=0.9491&fp-y=0.4338&fp-z=2.9222&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=870&mark-y=291&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zMDMmaD04MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 25\. check the NACL

![Step 25 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/80af3287-e2f4-40bf-9f9a-34ad40d45059/a65b7b3c-dd9d-4186-b49e-402163c13eb9.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=210&mark-y=146&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 26\. Click on Inbound rules

![Step 26 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/54984514-1cdb-4805-b40f-15e4d3bd4c7e/ebdab5eb-a9df-4395-aa9e-db3f701401e3.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=193&mark-y=432&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05OTgmaD03OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 27\. Click on Outbound rules

![Step 27 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/bce64c75-c763-4bb3-8d0c-138a2ef748bc/247cd704-11b7-4f2d-bd29-e073b93da28f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=388&mark-y=314&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTgmaD0zNCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 28 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/a3a9b9f8-e9af-489c-8388-0d9eb84b3dfe/10fc0319-2431-4dac-a48a-06650670640f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=191&mark-y=436&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05OTkmaD01NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 29\. Click on Edit outbound rules

![Step 29 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/13c9d74c-845a-47c6-bf3e-5d5578f22e63/dec1ec37-1105-4e53-a890-d119ed4a8eb9.png?crop=focalpoint&fit=crop&fp-x=0.9215&fp-y=0.6436&fp-z=2.9222&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=724&mark-y=291&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MDEmaD04MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 30 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/bc76bfe5-53b5-4d0a-9284-04b09e43a520/3f2a1370-48f6-46b8-a9b0-0f01c38533b3.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=31&mark-y=39&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNDkmaD0yNSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 31\. Click on Add new rule

![Step 31 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/a59a5119-946e-4627-81a9-02c65c1c8dd7/e5a576d8-c42f-4459-9062-3e7d2c3ee408.png?crop=focalpoint&fit=crop&fp-x=0.0902&fp-y=0.3294&fp-z=2.5930&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=147&mark-y=296&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNjcmaD03MyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 32\. Type rule number

![Step 32 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/40897dee-2455-433f-ad11-74732888fedf/0c119dca-c24b-43a4-9762-36958c9ecff6.png?crop=focalpoint&fit=crop&fp-x=0.0837&fp-y=0.2673&fp-z=2.6833&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=153&mark-y=295&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yMzQmaD03NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 34\. Click on Allow

![Step 34 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/4ea259df-8b4e-4b5f-81cb-1ecd9914cba9/c6fbd8b7-643b-474f-b72a-7bea0313c46f.png?crop=focalpoint&fit=crop&fp-x=0.8251&fp-y=0.3072&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=338&mark-y=287&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01MjMmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 35\. Click on Save changes

![Step 35 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/190da3be-dee0-4d04-8280-01155d927cee/ccd29228-10ac-4ae8-8dc1-bbf621b01f0d.png?crop=focalpoint&fit=crop&fp-x=0.9491&fp-y=0.4338&fp-z=2.9222&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=870&mark-y=291&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zMDMmaD04MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 36\. check nacl

![Step 36 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/8225c29f-4a87-4e7c-9363-bff602fc4460/e7ec4fb8-1288-4fb7-8e01-b095989759f3.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=200&mark-y=150&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 37\. Click on Outbound rules

![Step 37 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/64e61241-9e38-4bd7-a4f4-87b1217c527c/9129eb5d-2107-4755-875b-7f27ddb14ce8.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=383&mark-y=312&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTkmaD0zNSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 38\. our outbound rule has been successfuly created

![Step 38 screenshot](https://images.tango.us/workflows/54d7bac2-0523-430d-9755-0625d7e9abd1/steps/d64a3d16-ecd1-485b-a088-cd92b1a01aab/48390a34-811c-414c-9a50-16c7335bf95f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=198&mark-y=433&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05OTImaD03OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

## WEEK 3 DAY 2

## 4.CREATING ROUTE TABLES

### 1\. Navigate to the VPC dashboard

### 2\. Click on Route tables

![Step 2 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/f2ab211a-7f51-443b-9e34-0560d358f3dd/853850cd-9f65-4923-9ff9-3d15c9a47509.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=13&mark-y=205&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02OSZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 3\. Click on Create route table

![Step 3 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/f46327c8-90c8-4ee8-9e7e-633dee3c1b58/c59e675a-2c18-4b8a-a15e-2c90abfe94cb.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1060&mark-y=32&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 4\. Type the name of the route table

![Step 4 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/9af536c7-da00-49aa-b6ea-0ff9702c5dca/3fee02c3-8023-4c4d-af85-f59cd87db612.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=40&mark-y=157&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NTUmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Select LAB3 VPC

![Step 5 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/fc735015-56b6-4a6d-8779-4f4c052f677d/ca5ae530-8905-40df-b2d6-261bfde42fc6.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=40&mark-y=261&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NTUmaD0zMiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6\. Click on Create route table

![Step 6 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/da725062-d7b0-4765-9f68-ad5a1597d447/548600e0-c4b4-46aa-b517-f06fa0d55b72.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1062&mark-y=434&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 7\. Click on Routes

![Step 7 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/91cfc8a0-fbd9-4e2d-be03-80a5b1482a1c/cab334e3-7105-444d-b3db-97a5b07c0597.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=231&mark-y=220&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02NiZoPTM0JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 8\. Click on Subnet associations

![Step 8 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/b1770d9c-ebdc-4f3d-b9f7-1f9f2f6702df/2566e9f9-9fee-42b6-9add-e54d5929beb8.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=301&mark-y=225&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNDMmaD0zNSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 9\. Click on Edit subnet associations

![Step 9 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/4103f209-4aca-456e-b067-7d2e0c56e072/7c645280-9179-4e99-a1af-1019340be69f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1004&mark-y=354&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNjAmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 10\. Check the public subnets

![Step 10 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/03f46c8d-1406-4154-b14c-a449b46da222/267dcdf5-0aa0-4ccc-86ac-5c55002e3b4d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=58&mark-y=214&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 11\. Click on Save associations

![Step 11 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/c790c0e7-3fc1-4d80-8c52-5a18b2c209ef/b3e9e744-d08e-48b0-8c58-a3956ba756c7.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1067&mark-y=352&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjQmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 12\. Click on Explicit subnet associations

![Step 12 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/2c0bf44e-dfbb-4c98-a263-3941ab86046b/0b24e577-5dfb-45a3-a736-4858b15b863a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=225&mark-y=317&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NTQmaD03OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 13\. Click on Create route table

![Step 13 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/74c83fd5-de21-40da-9321-9c2eba472a9b/bf982d61-17c3-4e5e-8b90-dd69a773aacf.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1060&mark-y=26&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 14\. Type the name of the route table

![Step 14 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/316fa5f2-eca3-41af-a46a-5a596db83f30/b4b4b3ca-df6c-475c-b4e6-df9f9a2fd86a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=40&mark-y=121&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NTUmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 15\. Select LAB3 VPC

![Step 15 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/a27835a9-7b9a-45a0-a17d-ae5e8169454f/f12acdbb-e783-460e-be6c-850a8790c253.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=57&mark-y=178&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDMmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 16\. Click on Create route table

![Step 16 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/1834232b-c809-4340-b947-f0cb2e0185f1/e87c75b3-7301-4de4-854c-aecd58ca1b33.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1063&mark-y=424&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 17\. Click on Subnet associations

![Step 17 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/6741a1f5-a032-4870-94b6-188f47212dba/42106b4f-bad6-49bb-a9cb-24d9cf2d6ea7.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=307&mark-y=225&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNDImaD0zNCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 18\. Click on Edit subnet associations

![Step 18 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/32348a00-4f1d-4254-8033-faa0f12624cf/9760b335-d66e-423a-b329-d7484dd0899b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1004&mark-y=193&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNTkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 19.Check the private subnets

![Step 19 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/9e786ff0-b6ef-4dfc-81e9-60d044205b9c/5d330bb1-5e1d-493a-8a45-679ccc6bf3fd.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=52&mark-y=196&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 20\. Click on Save associations

![Step 20 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/cfde290c-7f94-41ab-9860-dd839bf63ec7/1ef46f56-f4e2-4f21-bc80-9e9a53c9b941.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1066&mark-y=349&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjUmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 21\. Click on Route tables

![Step 21 screenshot](https://images.tango.us/workflows/43d5b8e9-f532-42e6-b8b8-3e785d76952c/steps/704b5ed3-1228-4a16-8c53-45997736ce42/534e21b1-0a35-4522-a61e-beb5a35ea547.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

# Internet Connectivity

### 1\. Navigate to the VPC dashboard

![Step 1 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/b9d0895b-0cbe-43bc-add5-efff25a10cb4/78035e4f-ba02-4ded-80f4-c3a691dbf3cd.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2\. Click on Internet gateways

![Step 2 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/b349eba2-56f5-44cd-a53f-0d53e9bcadfe/11e23de5-f892-4659-aa45-996d0a02c442.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=16&mark-y=223&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NSZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 3\. Click on Create internet gateway

![Step 3 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/b329d87b-8bcc-42d8-962b-2f6024a9b65c/20c65452-eb2c-451f-8acc-db99bd451247.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1029&mark-y=34&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNTkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 4\. Enter the name for the internet gateway

![Step 4 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/4d69f335-f353-4d63-9b0d-857e49bb14a6/2f5c5586-048b-4afc-9ee6-57c63daeaf1d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=13&mark-y=161&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzUmaD0yOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Click on Create internet gateway

![Step 5 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/3f134d52-6072-465c-b500-5a084f21ca86/7ceb25ba-5649-46b9-aed2-a9a713e66ff8.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=978&mark-y=371&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNTkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6.Our igw is finally ready

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738822750775/80ee0f8b-deb6-4fa0-ba94-a91f208887e3.png align="center")

### 7\. Click on Attach to a VPC

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738822807730/eaaa89e5-b65f-49d7-8392-a27fc181adf5.png align="center")

### 8\. Click on Available VPCs

![Step 8 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/b129cf5d-b54c-491a-b7e9-cb42bc3dde57/81428904-2432-4533-b6c9-01f524adc869.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=49&mark-y=157&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MTImaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 9\. Select LAB3 VPC

![Step 9 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/c9665164-4ddf-49b7-8d80-cf0974533c6e/cd94dc65-34b7-474e-b9b0-ec916a82b2ad.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=55&mark-y=179&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MDkmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 10 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/a1fc69b3-6fbb-40c9-9d7b-be969507f837/aa281776-7255-4b6c-a825-ae11ac91527e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=46&mark-y=153&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MTQmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 11\. Click on Attach internet gateway

![Step 11 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/9600510f-07bf-4bb0-81c7-e6d319654fad/7bf9f99a-95b4-4bb2-ad6d-b554763db183.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=975&mark-y=243&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xNjImaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 12\. igw was successfully attatched to VPC

![Step 12 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/436d5ec8-f899-4306-a429-15dcc1eb63fd/c82005d4-39a3-47bc-93ee-5cc8a587a98a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=218&mark-y=4&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NzYmaD0zNSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 13\. Click on Route tables

![Step 13 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/4bc93c4a-233e-4def-9863-90b9fcef250b/cd171963-3fdf-4fd4-b32f-71ca117b8a66.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=19&mark-y=201&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02OSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 14.Check LAB3 public Route table

![Step 14 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/5e9432cd-2971-446e-8572-811c5eb5c36e/fa2fceb4-078d-46b2-9133-be01f024ed7c.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=206&mark-y=194&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 15\. Click on Routes

![Step 15 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/0bf14448-b682-4364-927e-2603a082e767/9c136731-287c-4b8c-abf9-42f887174199.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=271&mark-y=393&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02NiZoPTM1JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 16\. Click on Edit routes

![Step 16 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/f7601524-ebf7-4094-af14-c9e9831d79d7/10d677ae-c6c0-44e1-9f9a-1563b3c7b48a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1084&mark-y=441&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05MCZoPTI4JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 17\. Click on Add route

![Step 17 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/15443e13-b9bc-4e80-87b1-d29eff80342f/e555ff6c-bf92-44fc-9c4f-5a3a5e60a2e2.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=55&mark-y=146&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04NiZoPTI4JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 18\. Enter 0.0.0.0/0 as the destination

![Step 18 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/f0192578-1418-4302-a338-8060b81c2a56/64137720-e9fd-4c3f-9575-c58f17466d5a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=52&mark-y=160&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0zNTkmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 19.Search for internet gateway in the drop down

![Step 19 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/2a1c59d4-1118-4405-861f-56522a8dd646/516edbe3-716a-4eee-885c-8a5cff6bb7c0.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=333&mark-y=134&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yNzcmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 20\. Click on Internet Gateway

![Step 20 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/1cf4e2d8-b48f-48cc-a38f-d5256ef028fc/88037e00-a5ae-40a1-97a9-a35ff150511a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=338&mark-y=273&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yNzUmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 21\. Select LAB3 IGW

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738823543643/281f8ce6-8339-4747-83a4-94353a1c9564.png align="center")

### 22\. Click on Save changes

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738823592620/2b3ad7a4-dd81-44a6-9ba6-edb5825c866e.png align="center")

![Step 23 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/a5c38b75-c819-46b4-a4f0-539fd325115e/60514fa0-a464-450a-91cf-2a947476946b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 24\. Click on NAT gateways

![Step 24 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/03a57071-6848-45fe-8408-823ef180701d/e2481385-5ab1-4298-a255-a98043a1d11a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=13&mark-y=342&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NiZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 25\. Click on Create NAT gateway

![Step 25 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/fa9f36a2-b652-402a-9e94-178243331ddc/19bcfb15-6dad-43e5-8282-3eb33073254d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1050&mark-y=36&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMzkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 26.Enter the name for the NAT gateway

![Step 26 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/3d86075e-1658-447b-a133-356e8f907c1c/09aa00bd-0ac1-46a7-b29f-d963c5347f93.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=57&mark-y=118&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzUmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 27\. click on subnets

![Step 27 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/464d0f7b-078a-4430-8a9c-bffeaeec3ef6/415bfedb-f40d-4952-814c-520d75180c04.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=49&mark-y=240&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDAmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 28\. Select LAB3 PRIVATE SUBNET1

![Step 28 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/7d3eaf2a-330e-462b-bdf4-1b75c605dc06/1968640e-5261-4961-8c1c-9673e883fa6f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=36&mark-y=340&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDkmaD00NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 29\. Click on Allocate Elastic IP

![Step 29 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/f820505e-665f-4020-a9af-b678d7806bb9/dbb750ea-3483-42eb-aeb0-fb41a294c7c0.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=796&mark-y=410&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 30\. Click on Create NAT gateway

![Step 30 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/9c1bb8d4-6c98-40b8-b493-eb2569443297/37da66f0-a4ea-4cb7-87c6-f4dfd6287bf5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1041&mark-y=565&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMzkmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 31.NAT gateway successfully created

![Step 31 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/60fb41ec-edd6-4e42-bf2c-cbe1d44b6678/a2190a5b-5a46-4eb7-ab64-452696a5be0e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 32\. Click on Route tables

![Step 32 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/dc195b2c-9aeb-4485-8b15-59897bc308a3/57989295-43c3-4170-bfc2-8019c288571c.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=16&mark-y=102&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02OSZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 33.check LAB3 PRIVATE ROUTE TABLE

![Step 33 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/c96fcba8-19d3-40c5-bd83-9a92c13b758d/8bb7feb1-f47f-407f-8135-cc59a2b04049.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=207&mark-y=214&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 34\. Click on Routes

![Step 34 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/4ad967d0-1fe3-4bdd-b883-19b3eb36d7d0/f04b45b6-770d-4649-9d2c-4a5fa920f675.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=277&mark-y=371&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02NyZoPTM0JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 35\. Click on Edit routes

![Step 35 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/7864626c-fcc9-4f78-bd67-b918bcb7b0f8/6d249889-db3e-47af-ac2d-f53ef2de1441.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1084&mark-y=418&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05MSZoPTI4JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 36\. Click on Add route

![Step 36 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/b2cc5af3-90cb-4ae0-ba36-85b448c2785c/620213ca-651e-42be-8d2c-293102361af7.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=57&mark-y=143&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04NiZoPTI4JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 37\. Enter 0.0.0.0/0 as the destination

![Step 37 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/3b2ad131-24f4-43ed-8887-34c1d64e2e3f/f9ab4305-c86c-488d-976e-e500f12e00c4.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=52&mark-y=153&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0zNTkmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 38\. Search for NAT gateway in the drop down

![Step 38 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/be595fcb-8a67-41dd-842f-856ee87e3c77/16a1b199-5a40-460d-971d-538362eed99f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=320&mark-y=131&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yODEmaD0yOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 39\. Click on NAT Gateway

![Step 39 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/c9ab3e85-634f-4b13-8de0-002dc7409f42/b3256bf3-bccb-4b2d-a0c8-040a21a8b450.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=327&mark-y=323&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yNzkmaD0zMiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 40\. Click on LAB3 NAT GATEWAY

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738824322080/2d07851b-6bb8-4cee-83d5-990e2476fd14.png align="center")

### 41\. Click on Save changes

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738824356974/0784ed4d-5602-408a-8279-5949cadc3979.png align="center")

### 42.Route updated

![Step 42 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/da0bbdf3-b9c4-4a2a-b840-b0887da3f7c4/fd52f02a-82e4-4261-ad64-85851ae44abf.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=225&mark-y=5&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NjYmaD01NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 43\. Click on Routes

![Step 43 screenshot](https://images.tango.us/workflows/4d87e0ef-813e-4a82-84ca-282e16328d03/steps/1be53b46-d1dc-474b-b3bf-a73baeb5e3cb/988f620d-30aa-4155-a551-1737e86a0be4.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=228&mark-y=239&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NjEmaD03OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

## VPC ENDPOINTS

### 1\. navigate to the dashboard

![Step 1 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/cb380b16-9bdb-4745-bd5e-30c1f08c2f04/0cee6b51-e728-4e26-804b-c7cf95f1f4ad.png?crop=focalpoint&fit=crop&fp-x=0.0831&fp-y=0.5305&fp-z=1.1021&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=3&mark-y=12&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yMTMmaD02NDEmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 2\. Click on Endpoints

![Step 2 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/52fd5dde-3521-4df1-a606-e7e28950e0b0/29cb9e27-65c2-45ee-ad10-90d29209cdc4.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=14&mark-y=538&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01NiZoPTIwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 3\. Click on Create endpoint

![Step 3 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/b1da1f29-7589-4311-b31f-c56444f0df04/70c05c3a-e369-4e9a-b30a-d522d9fdac16.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1070&mark-y=65&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 4\. enter endpoint name

![Step 4 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/64eae84d-616a-464c-98dc-b5c29b04b8b6/eff7eefb-d683-483f-a624-18318432dfa7.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=57&mark-y=172&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzUmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Click on AWS services

![Step 5 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/9182e31c-def0-4be7-94c9-c944a59d90d3/3c4a7149-be08-475c-b10f-6dfaf7f96009.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=68&mark-y=248&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0zNDcmaD00NyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6\. search on KMS

![Step 6 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/f1551ee1-aa78-484b-800a-3dd8aa75c869/1dd05891-bb17-451e-88ed-44546970735e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=46&mark-y=164&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01MTYmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 7\. Click on Select a VPC

![Step 7 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/62cf544f-826d-4ae1-a74c-27ef531ee5ed/6302c1f2-339f-489a-9140-af925a0293ac.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=55&mark-y=301&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzcmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 8\. Click LAB3 VPC

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738824930078/3423ff96-845d-4422-aca0-a5f9de2d700a.png align="center")

### 9\. Click on DNS record IP type

![Step 9 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/30e27691-c6ec-4bfc-81d9-d319832df782/73e0f5e3-7219-4645-a724-91ca1e6e76e3.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=53&mark-y=350&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzgmaD03MyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 10\. Click on Select a subnet

![Step 10 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/e12f57c8-6011-4518-8254-404bdbf2318b/b5e4f805-5fd9-417b-843c-140e49e05949.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=253&mark-y=251&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yMTYmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 11\. Click on LAB3 PRIVATE SUBNET1

![Step 11 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/d04c5cba-e158-4173-b5f4-fabfbd773cd1/6417b31f-6c5e-4bfa-a874-769293e967a5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

![Step 12 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/435a1da2-120f-4698-86b5-5969c44a5971/79bc0ea8-caae-42a4-96d4-cc217f4db625.png?crop=focalpoint&fit=crop&fp-x=0.0642&fp-y=0.4959&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=206&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 13\. Click on Select a subnet

![Step 13 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/9ff2de7f-8f27-4f7e-886c-e55cdd23af2b/5bb329d4-e26b-4902-812f-d099f325225f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=250&mark-y=288&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yMTcmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 14\. Click on LAB3 PRIVATE SUBNET2

![Step 14 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/bfc0e27d-0180-4a0e-ad6d-a5b52366324f/2734ab72-e46e-4775-bbc8-41edced440dd.png?crop=focalpoint&fit=crop&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 15\. Click on IP address type

![Step 15 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/4ff42b00-3f13-45ba-8963-b6dbccfa271c/f3e2314c-2bd8-4bdd-b13c-973ddef33236.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=52&mark-y=278&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzgmaD01NiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 16\. Check on security group and select default SG

![Step 16 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/72252872-54e1-4a44-b846-687a44d122d4/fc4574dc-4747-4500-b2aa-59f4f1d21e25.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=67&mark-y=484&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 17\. Click on Full access

![Step 17 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/96589a83-9058-4f7e-8895-958e459665db/f30c1a18-e9b0-4cb8-b5fb-b776093366ad.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=69&mark-y=364&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMDk0Jmg9MjImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 18\. KMS endpoint

![Step 19 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/a71eaed1-8d78-4f43-9b64-043b0b36ccef/62e19d51-ccc2-43b7-9539-65364d1e649d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1070&mark-y=95&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 20\. Click on endpoints and then name it S3 ENDPOINT

![Step 20 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/2b904c13-e057-4be7-bf34-f272ed51a0c8/e7584770-f5c8-4f79-a3ae-c327975d4df8.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=45&mark-y=171&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDMmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 21.Search for s3

![Step 21 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/1e6dcbd8-9f71-4b3d-8686-3ff499aa972e/0bacd81c-a573-4d01-82a0-4bd75492f0e1.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=51&mark-y=307&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01MTQmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 22\. Select S3 with interface endpoint

![Step 22 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/efd890c5-e5ad-49f3-a243-04733f13ac77/cf7d0f82-f04f-4593-b40e-9d152c33b59e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=59&mark-y=394&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 23\. Click on Select a VPC

![Step 23 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/74429e7d-38f8-487c-94bf-2c51624fd02f/e386758f-c43b-4f9a-8035-78e918d9fb94.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=47&mark-y=515&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDImaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 24\. Click on LAB3 VPC

![Step 24 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/83fef0bb-4d97-4205-9849-a3886c92494a/df69c302-8016-403c-8aa1-516607cc1b30.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 25\. Click on Route tables

![Step 25 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/6d2f5a49-988f-4277-8233-6c9eef781034/6d7341c0-446f-4c4a-bb7a-9155deb1597d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=33&mark-y=352&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTQ2Jmg9MTA0JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 26\. Select the two subnets available in the vpc

![Step 26 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/41550c07-ea03-4fb1-b664-b65839dcc4f0/645178f5-5d2f-49de-b436-4c967989ffdb.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=61&mark-y=373&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xOSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 27\. Click on Full access

![Step 27 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/2d4762da-a873-4fdb-b20e-cf83275a932a/f674af46-cfe8-4664-87db-85bdecba6b45.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=62&mark-y=247&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTAxJmg9MjImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 28\. Click on Create endpoint

![Step 28 screenshot](https://images.tango.us/workflows/a13d05ae-d76f-420a-8ee7-c1759c439eda/steps/2d1184bf-bfe3-4936-abeb-c7b3b308188a/de37a35e-2a27-4e0b-92cb-ba57c927427f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1062&mark-y=568&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTgmaD0yOCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

## WEEK 3 DAY 3

# EC2

our first ec2 instance will be deployed at the public subnet while the second vpc will be deployed at the private subnet

### 1\. Navigate to the dashboard and search for ec2 instance

![Step 1 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/cf3f01b1-2c33-427d-ae16-c18fe5d59d52/805ffb47-49a4-454d-9f58-acd5aa7ba58d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2\. Click on EC2

![Step 2 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/bfbf771b-98ce-4794-a14a-792b7a6ec39e/5e5d90a7-0cce-449f-81e0-c946ed410d0b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=317&mark-y=53&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yOCZoPTIyJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 3\. Click on Launch instance

![Step 3 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/5d8a2b26-04de-45fe-b5da-76cb63fd357e/77ed9682-6f79-4382-a6c4-f41d022df231.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=208&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjImaD0zMiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 4\. ec2 instance name

![Step 4 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/13767857-75e3-415c-95a1-7830976f642e/c18cc116-50ae-4a17-b848-607dbc5a079a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=30&mark-y=155&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00ODkmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Click on Amazon Linux

![Step 5 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/80da1f18-9368-4607-9ed7-3477dfc1286d/0e66e9cc-d8a5-4bad-8c16-6e0336e4850e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=37&mark-y=309&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03OCZoPTEwNCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6\. Click on Amazon Linux 2023 AMI

![Step 6 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/caaeea47-2338-4da4-8436-5dd6419498cb/128fd5b5-3730-483b-b910-7fc52a377c1b.png?crop=focalpoint&fit=crop&fp-x=0.3332&fp-y=0.5780&fp-z=1.0950&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=35&mark-y=327&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz04MDYmaD02MSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 7\. Click on t2.micro …

![Step 7 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/7e0b66de-a0c3-458e-9c5b-d05b7b30c17d/e3cb3168-55f1-44e5-8946-a0d213190f25.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=16&mark-y=380&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01NTAmaD05NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 8\. Create new keypair

![Step 8 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/f394fb1a-f11d-4229-beaf-b0cd2d8982ba/b419f584-9801-4769-8255-a7d79ad7d98b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=26&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00ODUmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 9\. select LAB3 VPC,LAB3 SUBNET2 and then enable Auto Assign public ip

![Step 9 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/f183d815-da29-4763-a943-d44420bf79ce/a5508054-083c-4a64-9ca2-a07bae97b7d9.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=24&mark-y=276&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00OTEmaD00NyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 10\. Click on create security group

![Step 10 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/25917b92-9fc8-45b9-b5be-c7041cbe8f60/7bcd98f2-14ce-4a38-9b2d-d243bd481177.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=20&mark-y=196&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00OTMmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 12 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/8e579eb6-0a3e-4174-8cb1-530ff21909ca/e6103024-e717-46dc-952f-d40cfec72728.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=30&mark-y=366&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzgmaD0xNTQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 13\. Click on advanced network configuration

![Step 13 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/89d01cf0-d0f7-4c89-a2e4-f95a674c9e8b/065ef87c-7d30-49fb-b48e-2892770e7456.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=27&mark-y=288&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03MzkmaD0zMCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 14\. input the primary ip as 10.0.2.100.Launch the instance

![Step 14 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/a64bb534-aa42-4295-bd14-3a71e47a2aa5/cf6e61fb-5a11-4524-8f9d-7124a5d0c0b6.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=528&mark-y=289&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yNDAmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 15 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/1c8a56a1-45d7-4b4d-a609-76a08beb7da8/da280bae-15df-4884-a50a-e00c330a54b6.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=9&mark-y=60&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTY1Jmg9NjAmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 16\. Click on Launch instances

![Step 16 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/d7dc5cc4-64b0-4a1a-bf8a-daef81f9bb71/22ff23ed-1d1d-4879-a6bb-5354410c85a0.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=1018&mark-y=42&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMjYmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 17\. Type LAB3 PRIVATE INSTANCE as the instance name

![Step 17 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/72fdb1c5-1d5d-41b7-8bff-7f63554baea7/89eb031b-3ddb-4b08-b316-fddf96a03f7a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=32&mark-y=85&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz00ODgmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 18\. Click on Amazon Linux

![Step 18 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/4294c79d-ebb5-441b-ab7c-85aa5af29f38/c41d9777-9093-4fe9-b22d-b85b7b305119.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=28&mark-y=385&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03OCZoPTEwNSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 19\. Click on t2.micro

![Step 19 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/137ffbe9-4dff-440d-940c-cb039c9ec8af/685640e1-6efa-4207-aaf1-0dc07925d3b1.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=17&mark-y=373&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01NDkmaD05NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 20\. Create new keypair

![Step 20 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/b209ef09-7ac7-482d-87d3-724f3c135508/1e8a5386-5bbd-4318-8540-92a713941b95.png?crop=focalpoint&fit=crop&fp-x=0.2274&fp-y=0.5885&fp-z=1.4251&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=46&mark-y=310&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz02ODcmaD00NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 20\. Select LAB3 VPC,LAB3 PRIVATE SUBNET1

### 21\. Click on LAB3 SECURITY GROUP

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738828664839/881e7a74-78e1-412a-932f-5904ec78719b.png align="center")

### 22\. Click on advanced network configuration

![Step 22 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/ca83204b-5872-45e2-87cf-07b2d1dfcf18/742bb312-9f92-400b-938d-d1efecef5854.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=27&mark-y=168&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDAmaD0zMCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 23\. Navigate to primary ip

![Step 23 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/5c8174a9-94d1-443e-9bfd-68df0ce8851a/410d3ecc-d98f-48f9-b0bc-fdf6ef24e1b0.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=13&mark-y=24&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz03NDkmaD0zMCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 24\. input the primary ip as 10.0.1.100.Launch the instance

![Step 24 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/ca339b18-fbd3-4fa4-aa97-3a95916951de/ebb29ff4-de2a-4e3d-ac00-75768095942b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=523&mark-y=129&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yNDEmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 25 screenshot](https://images.tango.us/workflows/3e350626-6fe7-466f-bad9-9a43294eab45/steps/f5359413-e745-4fe3-a9b5-b102aba70f0b/47d2a9cc-93ce-45e9-91a4-b1fac7f032ea.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=10&mark-y=55&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTYzJmg9NTkmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

# Test Connectivity

in this session,we shall use the EC2 instances in the public and private subnets of our VPC to test the connectivity for the network foundations we created in the previous section.

Here are our two EC2 instances which we created

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738899906778/3914d146-4458-44a2-94fa-0eb643cc8113.png align="center")

Select the instance at the public subnet and and then copy its public ipv4 address

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738899941082/34f22c42-5dd0-4216-897c-12fc75b97dc2.png align="center")

Open your terminal at your computer and then try to ping the instance.

ping 44.222.145.205 -c 5 then click enter.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738899976743/b520f371-5db9-404c-84ec-f3917e86844f.png align="center")

For our second instance which is at the private subnet,we are going to first ssh to our instance which is at the public subnet then we shall then ssh to the instance at the private subnet as shown below:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738899999423/14ec7806-fc24-45e7-96c4-ee69eefb09d6.png align="center")

Having manged to ssh to our instance at the private subnet,we are going to test connectivity to both the public instance at `10.0.2.100` and external connectivity to [`example.com`](http://example.com) via the NAT Gateway.

Input these two command and click enter:

ping 10.0.2.100 -c 5

ping example.com -c 5

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738900018376/b19ce532-94ba-400a-b339-06c6d31aaccf.png align="center")

Type the following to check the DNS for the KMS service from the VPC A instance:

digkms.us-east-1.amazonaws.com

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738900049854/b14759df-1d84-4ee4-b7f6-63d4f53ad069.png align="center")

# VPC PEERING