---
title: "@Week 2 of 12 weeks aws workshops challenge"
datePublished: Mon Feb 03 2025 20:52:26 GMT+0000 (Coordinated Universal Time)
cuid: cm6pj1m2u001d09js35xz1b5d
slug: week-2-of-12-weeks-aws-workshops-challenge
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cckf4TsHAuw/upload/8479e09895dbc1576a1ab0cdae305c9d.jpeg

---

## AWS Identity and Access Management (IAM)

IAM is a web service that helps you to securely control access to AWS resources.

You use IAM to control who is **authenticated** (signed in) and **authorized** (has permissions) to use resources.

Terms used in IAM

1.Root user-this is the owner of the AWS account who has all the administrative rights(single sign-in identity)

2.IAM user-this is a entity which is created by the root user and then given some permissions by the root user

2.IAM groups-this is a collection of multiple IAM users who have the same permissions

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1738574799226/57f651fc-cde5-42cf-bded-81700c15c945.png align="center")

3.IAM Role- this is an identity with permissions that can be assumed by users or services that tells what the identity can do and what they cannot in aws account

4.policies-this is a JSON document which contains of the permissions or what can be assumed by a user,service and groups

## Root User best practice

### *1.DO NOT use your root account for every day tasks.Instead create an IAM user.*

### *2.Enable MFA soo that it can be used during logging in to your root account*

### a.Click on the arrow which has your root or IAM user and account id

![Step 1 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/61690ea8-6941-4928-b44e-73c8ab3d38c7/9aae12ab-67aa-466b-9e23-0c96587bb8d3.png?crop=focalpoint&fit=crop&fp-x=0.9153&fp-y=0.0352&fp-z=2.8068&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=682&mark-y=13&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00NjYmaD0xMDUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### b. Click on Security credentials

![Step 2 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/83e7359b-a4d3-44ed-96b1-af26b6e50270/614cd46e-4f1c-45cc-8fa6-d5f0c3a0217b.png?crop=focalpoint&fit=crop&fp-x=0.8488&fp-y=0.3552&fp-z=3.0046&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=500&mark-y=299&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zMDkmaD02NiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### c. Click on Assign MFA device

![Step 3 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/e493d8bc-b164-4457-831b-911e1284f95b/87794c39-103d-4a7e-9068-065e1936bdfa.png?crop=focalpoint&fit=crop&fp-x=0.9075&fp-y=0.6975&fp-z=3.0683&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=653&mark-y=284&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MTMmaD05NiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### d. Type MFA device name

![Step 4 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/39aeb0af-488e-4c5b-a34c-61663d1d3183/a69ad3a9-53ba-4fa1-ab09-b1d9b30a59c8.png?crop=focalpoint&fit=crop&fp-x=0.4254&fp-y=0.3247&fp-z=1.3719&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=247&mark-y=275&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03MDYmaD00MyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### e. Select the method to use for authentication

![Step 5 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/c764d3fb-1f90-4c54-8e43-1ae6865a61b3/34067953-7015-401e-acb7-7368645e16ee.png?crop=focalpoint&fit=crop&fp-x=0.4306&fp-y=0.7479&fp-z=1.3917&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=251&mark-y=226&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz02OTkmaD00MTAmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### f. in case you choose aunthenticator app install it to your mobile phone

![Step 6 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/a594322e-3b40-46d1-90b9-8260bace6487/8dea4172-fa97-4b4c-9216-7fd90209ab14.png?crop=focalpoint&fit=crop&fp-x=0.2382&fp-y=0.7046&fp-z=3.1688&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=570&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01OSZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### g. Click on Next

![Step 7 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/43a4cea7-538e-4790-85fb-0a062045454a/ccf6bc5b-81e3-47ed-b55d-3db65ae4da4a.png?crop=focalpoint&fit=crop&fp-x=0.6265&fp-y=0.8980&fp-z=2.8260&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=509&mark-y=429&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xODMmaD04OCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### h. Click on Install a compatible application such as Google Authenticator, Duo Mobile, or Authy app on your mobile device or computer.

![Step 8 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/4dc45182-8daa-4f73-8dd5-c65c8d00d577/5f76da55-d782-424f-bdbb-5352db70b681.png?crop=focalpoint&fit=crop&fp-x=0.4513&fp-y=0.3482&fp-z=1.4770&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=266&mark-y=305&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz02NjgmaD01NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### i. Click on Show QR code…

![Step 9 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/7a138752-aa7e-4735-bffe-86f01df8743c/3fd4f393-c79e-418b-a43c-55ca9ce720da.png?crop=focalpoint&fit=crop&fp-x=0.4513&fp-y=0.5592&fp-z=1.4770&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=266&mark-y=201&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz02NjgmaD0yNjImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### j. Click on Type two consecutive MFA codes below…

![Step 10 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/31fe48e2-ab11-4aa4-a953-f02091ba6d28/9325e253-7b2d-40c5-b371-972a8d074545.png?crop=focalpoint&fit=crop&fp-x=0.3676&fp-y=0.8101&fp-z=1.9623&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=353&mark-y=276&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00OTQmaD0yODEmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### k. Click on Add MFA

![Step 11 screenshot](https://images.tango.us/workflows/79ec8cc3-c220-431a-a450-4d2f0529ddbf/steps/d23f902e-7295-41e0-89ef-2ca7681ad4df/c4f2b4e5-1865-4a27-9c8b-9c9c4c2eb16e.png?crop=focalpoint&fit=crop&fp-x=0.6175&fp-y=0.8980&fp-z=2.6879&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=484&mark-y=440&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yMzImaD04NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

## ***3.Avoid using aws account root user access keys***

These keys should actually be frequently rotated

## *4.keep on changing aws root user password*

## *5.Configure strong password policy*

### 1\. Click on IAM

![Step 1 screenshot](https://images.tango.us/workflows/440b319c-6109-4006-babf-50a7fd194720/steps/4fe2fd22-4174-4036-8c96-76e4b41175ac/731343b6-93f6-46fc-bdf8-7c657c1b1ccc.png?crop=focalpoint&fit=crop&fp-x=0.1249&fp-y=0.2526&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=416&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OCZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 2\. Click on Account settings

![Step 2 screenshot](https://images.tango.us/workflows/440b319c-6109-4006-babf-50a7fd194720/steps/de2cd553-dde9-4e38-a8a6-6824c4481dcb/7f014d5b-c929-4d78-8dbf-750a4a73910a.png?crop=focalpoint&fit=crop&fp-x=0.0535&fp-y=0.5434&fp-z=2.6601&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=50&mark-y=306&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNDImaD01MiZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 3\. Click on Edit

![Step 3 screenshot](https://images.tango.us/workflows/440b319c-6109-4006-babf-50a7fd194720/steps/5b9ccee2-c08d-402e-b6a0-cac4a8b22a31/4ecfb949-34f5-4274-8c69-9380393065b8.png?crop=focalpoint&fit=crop&fp-x=0.9384&fp-y=0.2005&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=899&mark-y=287&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xNzUmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Select Custom

![Step 5 screenshot](https://images.tango.us/workflows/440b319c-6109-4006-babf-50a7fd194720/steps/5642b648-75ab-448f-812c-072742e74342/1d221446-f9a8-4099-bde4-601bd2c4c102.png?crop=focalpoint&fit=crop&fp-x=0.5185&fp-y=0.2521&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 6\. Click on Save changes

![Step 6 screenshot](https://images.tango.us/workflows/440b319c-6109-4006-babf-50a7fd194720/steps/f1fba835-c006-437b-9706-148c7dbb928f/49b5c312-2576-4116-afa2-3a76991b0cc2.png?crop=focalpoint&fit=crop&fp-x=0.9413&fp-y=0.7878&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=699&mark-y=270&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MzkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

## Tasks that require root user credentials.

a.changing of account settings

b.Restore IAM user permission

c.closing of aws account

d.register as a seller in the Reserved Instance Marketplace.

e.activate IAM access to the billing and cost management

f.Sign up for Govcloud

g.configuration of amazon S3 bucket to enable MFA

## Creating an IAM user

### 1\. Click on IAM

![Step 1 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/6cf4a739-b2a9-4e38-a863-e5af22f225d7/b2c5216e-8b1d-4bd9-a7d4-0559758aa224.png?crop=focalpoint&fit=crop&fp-x=0.1249&fp-y=0.2526&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=416&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OCZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 2\. Click on Identity and Access Management (IAM Console)

![Step 2 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/79f71cff-9857-4241-ad49-20114aacafa4/184d9cd1-4e14-4f2a-8413-5b569ff3464a.png?crop=focalpoint&fit=crop&fp-x=0.0960&fp-y=0.5305&fp-z=1.1021&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=3&mark-y=12&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNDcmaD02NDEmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 3\. Click on Users

![Step 3 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/5171a718-7686-4fb4-8f56-de1e77a9678a/c6b9c36f-d18a-4aa5-a39f-f914c8d26b3f.png?crop=focalpoint&fit=crop&fp-x=0.0295&fp-y=0.4121&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=57&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMDImaD01OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 4\. Click on Create user

![Step 4 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/2990a346-abc2-40a9-9b6c-c68d07f7a6bf/85452b3b-4bee-408e-93ac-36c005acd592.png?crop=focalpoint&fit=crop&fp-x=0.9458&fp-y=0.1547&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=870&mark-y=251&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yODUmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5.Enter the user name

![Step 5 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/3800860d-e195-44ae-b6aa-d08fb598e5c1/0061d070-fb2b-4396-b100-7d51292a2a8f.png?crop=focalpoint&fit=crop&fp-x=0.4637&fp-y=0.3200&fp-z=1.2673&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=216&mark-y=250&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03NjkmaD0zOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6\. Check Provide user access to the AWS Management Console - optional

![Step 6 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/1b932f30-1b91-4ddb-9ddb-1a32dbb8b04b/c7193880-09b3-46d0-8a62-39aa0d745d0b.png?crop=focalpoint&fit=crop&fp-x=0.2187&fp-y=0.3880&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 7\. Click on Next

![Step 7 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/54101582-8130-4d4e-a853-18ded3eb39b5/e7d6536c-927b-49d9-bde5-ce80727fb0fb.png?crop=focalpoint&fit=crop&fp-x=0.9601&fp-y=0.8417&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=879&mark-y=270&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 8\. Click on User name

![Step 8 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/28f29f89-d3cd-44ee-b31f-b89e0ccc9b7c/857c7711-1946-4eb1-b6e9-3f01d2b5342c.png?crop=focalpoint&fit=crop&fp-x=0.4637&fp-y=0.3200&fp-z=1.2673&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=216&mark-y=250&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03NjkmaD0zOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 9\. Select I want to create an IAM user

![Step 9 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/5454c55b-7247-4f94-a944-333fac883bea/5fba7ccf-8b57-4cd1-b9fa-1b15dad67902.png?crop=focalpoint&fit=crop&fp-x=0.2459&fp-y=0.5991&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 10\. Select Custom password

![Step 10 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/3f7ded0c-ee53-4dbb-9fec-ee4256df4a06/19a4979f-b309-4b0f-9849-4127680e9f73.png?crop=focalpoint&fit=crop&fp-x=0.2187&fp-y=0.7819&fp-z=3.1688&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=570&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01OSZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 11\. Type password

![Step 11 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/dc1c0ede-8e4a-489e-9c5c-73f0a49d7093/5df06e2e-1c9a-4f18-aa58-14e5bf9e7fe0.png?crop=focalpoint&fit=crop&fp-x=0.4650&fp-y=0.8312&fp-z=1.2885&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=227&mark-y=500&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03NDUmaD00MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 12\. Click on Next

![Step 12 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/bc751bb2-8364-40db-9643-d6f165555522/01169a34-ca89-43aa-b31c-a65a53373d46.png?crop=focalpoint&fit=crop&fp-x=0.9504&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=832&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 13\. Click on Permissions options

![Step 13 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/c57a8075-c484-4f39-a486-bbaa4133615d/95f8f253-77f1-4844-8f8b-3e8dfbb33a6b.png?crop=focalpoint&fit=crop&fp-x=0.5921&fp-y=0.3417&fp-z=1.2673&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=20&mark-y=232&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTYwJmg9MTEyJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 14\. Select Attach policies directly

![Step 14 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/ab18ce21-89f5-424d-90d3-e82d0ffd9477/046824f7-3dbe-46f4-b70f-7189c6cd1b96.png?crop=focalpoint&fit=crop&fp-x=0.7313&fp-y=0.3107&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 15\. Click on Policies table

![Step 15 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/2e8f2033-6cfd-43fc-a192-d249ef130014/52c7ffad-ed2a-4a9e-a88f-300c5dca1130.png?crop=focalpoint&fit=crop&fp-x=0.5873&fp-y=0.6249&fp-z=1.2468&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=17&mark-y=47&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTY1Jmg9NjE0JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 16\. Check on

![Step 16 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/27734f63-8a32-4849-a77e-995fdca0770a/cc3220dd-599b-4f07-8e28-da5437478b74.png?crop=focalpoint&fit=crop&fp-x=0.2271&fp-y=0.3728&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 17\. Click on Next

![Step 17 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/e197a739-e2e3-48a5-9cbd-6438a5ed494f/322f3a8f-6b54-4472-beec-535a554c0e08.png?crop=focalpoint&fit=crop&fp-x=0.9504&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=832&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 18\. Click on Create user

![Step 18 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/e0825051-507e-463b-b2e4-c676915f1e42/5da58652-3256-45d9-910c-e55a8514a13b.png?crop=focalpoint&fit=crop&fp-x=0.9458&fp-y=0.8757&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=742&mark-y=272&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zOTYmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 19\. Click on Steps

![Step 19 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/3482fd09-2101-4530-b9f8-7220773c56eb/dbb58130-5286-4b8f-b794-849d9a2b7591.png?crop=focalpoint&fit=crop&fp-x=0.0999&fp-y=0.3640&fp-z=1.2714&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=20&mark-y=102&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNjUmaD00MTEmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 20\. Click on Return to users list

![Step 20 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/b299f463-da43-4983-86db-28b3799230c2/975b6d11-7fc3-48c8-ba60-83015095d657.png?crop=focalpoint&fit=crop&fp-x=0.9296&fp-y=0.5838&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=758&mark-y=287&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zOTcmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 21\. Click on Users

![Step 21 screenshot](https://images.tango.us/workflows/6413115d-051c-4331-8754-0cef7a9c485b/steps/5ac77f87-8f57-44da-b0dd-e7b6d30be699/aace6d46-11b3-451a-a30a-199c27d6ef82.png?crop=focalpoint&fit=crop&fp-x=0.5964&fp-y=0.3329&fp-z=1.2427&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=2&mark-y=213&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTk2Jmg9MTI0JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

Creating an IAM User group

### 1\. Click on IAM

![Step 1 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/f5fb8192-dec9-4635-9c80-44a5c4e8b815/86afe0fb-c96c-45bb-aabb-a3976e1e1e72.png?crop=focalpoint&fit=crop&fp-x=0.1249&fp-y=0.2526&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=416&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OCZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 2\. Click on Identity and Access Management (IAM Console)

![Step 2 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/88fb8850-387c-485f-bf97-7837026d0eed/4c250850-0d9f-41a9-b300-16de0b1646e1.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=3&mark-y=62&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yMjQmaD01ODImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 3\. Click on User groups

![Step 3 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/4bed7fc6-633f-4b19-b007-95ed6701150d/cb7972b1-3e66-46ae-a2b0-476a87a2d990.png?crop=focalpoint&fit=crop&fp-x=0.0428&fp-y=0.3792&fp-z=2.8208&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=53&mark-y=305&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xODUmaD01NSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 4 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/ee764eb8-80bc-415f-9b23-cb6117930563/5acb4032-a972-42e2-b839-85ba19c992e5.png?crop=focalpoint&fit=crop&fp-x=0.5912&fp-y=0.1301&fp-z=1.2427&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=10&mark-y=88&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTgxJmg9MzkmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 5\. Click on Create group

![Step 5 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/4dee0d82-896a-44a2-8c28-b3a1b1b782d9/87668d27-f280-422d-ad4b-937517e0703f.png?crop=focalpoint&fit=crop&fp-x=0.9422&fp-y=0.1301&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=845&mark-y=204&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zMTAmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6\. Type group name

![Step 6 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/1a506bce-4e2e-4032-8a83-211e15f948a5/94c90d05-eacd-4f7c-97cc-9fec0ba67cd5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=252&mark-y=180&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02MDAmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 7 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/5a58235e-f307-4065-8967-b130c5e85c6d/3cd43a7b-ada8-4e6c-98ad-353f3c5c7c80.png?crop=focalpoint&fit=crop&fp-x=0.2252&fp-y=0.6366&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

![Step 8 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/4ddd8108-5614-4463-9359-f2b872b0223e/cbbb364e-3e7f-452c-a9f9-baf2e4f09c70.png?crop=focalpoint&fit=crop&fp-x=0.5863&fp-y=0.5346&fp-z=1.2437&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=17&mark-y=260&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTY1Jmg9MTQzJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 9\. Check on

![Step 9 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/a5bcb928-5ba0-4f65-8b7a-fb1b447cf357/2b59b263-e3fc-44c3-88fd-f840e922ed60.png?crop=focalpoint&fit=crop&fp-x=0.2252&fp-y=0.4713&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 10\. Click on Create user group

![Step 10 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/c817e02b-2fb6-4213-a128-cd44f6426f24/65fc7269-4796-4b1e-8f28-fa6824b4ce6e.png?crop=focalpoint&fit=crop&fp-x=0.9221&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=561&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01MzAmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 11\. Click on User groups

![Step 11 screenshot](https://images.tango.us/workflows/29186269-f39c-43a3-a3fd-262c8c3e4aaf/steps/ddfbe40c-abb5-4f1b-a666-a7a78ffc094a/c370f2b0-baa3-4f1b-a63b-ee6dfa4c1636.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=234&mark-y=157&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NTAmaD05OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

## Creating an IAM Role

### 1\. Navigate to the Console

![Step 1 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/00edb242-4089-4f42-88a6-250ac58f20dc/d2cbc176-c181-45a7-8d37-7559a0d75e2f.png?crop=focalpoint&fit=crop&fp-x=0.2794&fp-y=0.4261&fp-z=1.4634&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=160&mark-y=146&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz02NjImaD0zNzMmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 2\. Click on IAM

![Step 2 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/c215fb60-e55a-4288-a361-f066ef3411a2/86cd4752-ff25-46b7-969a-831123cfec8c.png?crop=focalpoint&fit=crop&fp-x=0.1249&fp-y=0.2526&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=416&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OCZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 3\. Click on Identity and Access Management (IAM Console)

![Step 3 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/8e61fe44-e30c-4703-95d7-bf8a5fc3e3db/78873031-0c14-426a-9c0a-3c99406c8b8d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=3&mark-y=62&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yMjQmaD01ODImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 4\. Click on Access management

![Step 4 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/bc5d4401-c267-4874-9619-30131d075c86/a3ead62a-b602-4ad4-96ac-7e6501f515d1.png?crop=focalpoint&fit=crop&fp-x=0.0873&fp-y=0.4455&fp-z=2.2552&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=42&mark-y=308&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zODgmaD00OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. Click on Roles

![Step 5 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/bb5476fa-7576-4fb9-90bb-6312be728330/dcbc0222-4990-4016-9ec9-8251b1bee9f7.png?crop=focalpoint&fit=crop&fp-x=0.0292&fp-y=0.4449&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=57&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz05OSZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

![Step 6 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/bc781e34-55ce-4065-a78b-d52a67cfb0a7/5720c237-cdea-48a8-9161-25936396affd.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=234&mark-y=71&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NTAmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 7\. Click on Create role

![Step 7 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/d1ef61df-c4b0-419e-afb4-3434948361da/e8d41f94-fcbc-4711-851a-72f55e033900.png?crop=focalpoint&fit=crop&fp-x=0.9465&fp-y=0.1301&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=875&mark-y=204&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yODEmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 8\. Click on Entity options and click aws services

![Step 8 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/84e25631-0dd5-4212-a88a-5ab48c6eb72c/722ee05c-8ece-4d8c-b6fe-5b5f8a981d84.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=253&mark-y=164&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02MDcmaD0xODEmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 10\. Click on EC2

![Step 10 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/4b35f2a2-2a7b-4a9b-b5b0-3a43cf404c7b/9b4e849c-f828-402a-8025-e4b4b1870454.png?crop=focalpoint&fit=crop&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 11\. Click on Next

![Step 11 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/1b24277e-4c2c-428d-89d5-0bf13612d118/5d87238a-05a1-4339-90c9-fbd8842b661a.png?crop=focalpoint&fit=crop&fp-x=0.9504&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=832&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

![Step 12 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/9dc67ee9-c00e-48e6-8c44-166134c44547/12d33f27-0dd7-4a59-ad1b-c51b5e9f0425.png?crop=focalpoint&fit=crop&fp-x=0.5873&fp-y=0.1524&fp-z=1.2458&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=17&mark-y=88&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTY2Jmg9NzYmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 13\. Check on the policy to attach to role

![Step 13 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/97141c0b-f92d-44f7-9d76-51b7ed6b5003/2792b186-9c87-4203-b0c5-cea8072b3630.png?crop=focalpoint&fit=crop&fp-x=0.2271&fp-y=0.4302&fp-z=3.0475&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=572&mark-y=304&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz01NyZoPTU3JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 14\. Click on Next

![Step 14 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/1ff5dde3-00d5-4a1a-9a46-2309b2a08f58/42a82966-20b9-4a57-892e-193fc1bbb2ba.png?crop=focalpoint&fit=crop&fp-x=0.9504&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=832&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 15\. Type "first-role"

![Step 15 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/ff6f7ce3-816a-4fc7-be97-d72b7c4fff6d/a6a74008-1235-453c-bc98-0b7fe8c22b7a.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=253&mark-y=132&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01OTkmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 16 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/75fc890e-b7cb-43de-b2d9-f6428bc3405e/8e0235c8-5812-4044-bc35-5b16593de1ea.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=238&mark-y=97&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05MzQmaD0yMDkmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

![Step 17 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/ad63030d-53d0-41df-96f4-04e32ea4f959/e130858d-5298-4bbf-8725-528b69bd7747.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=237&mark-y=230&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05MzYmaD0xNDcmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 18\. Click on Create role

![Step 18 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/e1738340-6c64-4140-ae2a-46407ee78b78/d03cef32-1e71-4417-8497-665c00d54e00.png?crop=focalpoint&fit=crop&fp-x=0.9367&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=702&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zODkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 19\. Click on Roles

![Step 19 screenshot](https://images.tango.us/workflows/28a133ec-02b8-4085-9361-c5340da489b6/steps/392d60e3-b960-48f8-a51a-5fe709766793/98d159a1-cb66-4147-b6e0-6293387cb89e.png?crop=focalpoint&fit=crop&fp-x=0.5863&fp-y=0.4877&fp-z=1.2427&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=17&mark-y=177&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTY2Jmg9MzEwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

## Creating an IAM policy

### 1.Navigate to the console

![Step 1 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/c0422638-032c-4756-8194-6095f57d3a6d/1d8f45cd-31cd-4f35-8e89-7bfe882464b3.png?crop=focalpoint&fit=crop&fp-x=0.2794&fp-y=0.4261&fp-z=1.4634&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=160&mark-y=146&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz02NjImaD0zNzMmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 2\. Click on IAM

![Step 2 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/3fe529e2-3e72-4def-b440-ac9d6fd0bc1f/239473c3-8660-4696-82b9-0e63de2e0666.png?crop=focalpoint&fit=crop&fp-x=0.1249&fp-y=0.2526&fp-z=3.0367&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=416&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03OCZoPTU5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 3\. Click on Identity and Access Management (IAM Console)

![Step 3 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/2793eee3-124f-4c44-a93c-3dc86e4a7811/17f9efc8-2846-41e2-bc3b-033fb45b550f.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=3&mark-y=62&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yMjQmaD01ODImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 4\. Click on Policies

![Step 4 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/b92b593d-fd2a-46db-9e5d-22c055ff619d/803c781d-eb9e-4970-ad54-224e5800e2ec.png?crop=focalpoint&fit=crop&fp-x=0.0334&fp-y=0.4777&fp-z=2.9789&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=56&mark-y=303&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMjgmaD01OCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 5\. you can choose the once which are already created by aws. For this case i am going to create my own policy

![Step 5 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/67682967-3d47-40b6-9e4d-d5c41625030d/e87f3682-a518-4104-9e76-3668caa43da5.png?crop=focalpoint&fit=crop&fp-x=0.5912&fp-y=0.6290&fp-z=1.2427&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=10&mark-y=56&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTgxJmg9NjA1JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 6\. Click on Create policy

![Step 6 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/0b03e719-c10b-4966-b2ef-eca11e4bee47/7cccceb2-8767-4f8e-993e-b4cbc4e182dd.png?crop=focalpoint&fit=crop&fp-x=0.9322&fp-y=0.1301&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=809&mark-y=204&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zMTImaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 7\. Click on JSON

![Step 7 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/6a98c9f9-67ae-4c66-911e-0f250f3441a3/9db832f9-8f0c-42af-ab50-aa40bfa5a977.png?crop=focalpoint&fit=crop&fp-x=0.8157&fp-y=0.2591&fp-z=2.8827&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=497&mark-y=287&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yMDcmaD05MCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 8\. Click on Editor content, press Enter to start editing, press Escape to exit

![Step 8 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/ed65c707-f6b7-408e-87bb-a13fd25422e9/09d8ad36-6d25-4505-8ee0-0e31f127d154.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.6231&fp-z=1.3059&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=184&mark-y=44&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz04MzMmaD01ODcmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 9\. Click on Next

![Step 9 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/daa8e0c2-be8d-4875-89b8-75f50d0d8e08/f9def54e-88d4-476e-8f9b-e38d2d130c23.png?crop=focalpoint&fit=crop&fp-x=0.9504&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=832&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yNTkmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 10\. Type the policy name

![Step 10 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/acfb242a-2cc8-4ac4-a218-c11e745368ff/121f821c-cf2a-411b-8f91-4747c40ab7f3.png?crop=focalpoint&fit=crop&fp-x=0.4604&fp-y=0.3529&fp-z=1.2673&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=221&mark-y=277&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz03NTkmaD0zOSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 11\. Click on Create policy

![Step 11 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/b404cde9-a858-4cc6-a4ec-968d13327a3d/f0cd4d10-fe5d-40b3-8830-404adf05db62.png?crop=focalpoint&fit=crop&fp-x=0.9322&fp-y=0.9004&fp-z=4.0000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=658&mark-y=337&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz00MzMmaD0xMjUmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 12\. Click on Policies table

![Step 12 screenshot](https://images.tango.us/workflows/5c691ed8-62a1-4a16-828f-188ebe2fc118/steps/2b3ee924-ed4e-489b-8fef-ef239a86905b/a309fef6-d796-48f7-b292-ca403f45e214.png?crop=focalpoint&fit=crop&fp-x=0.5912&fp-y=0.3787&fp-z=1.2427&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=10&mark-y=271&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0xMTgxJmg9ODMmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

## this marks the end of week 2