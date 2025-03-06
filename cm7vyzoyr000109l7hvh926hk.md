---
title: "@Week 4  of 12 weeks aws workshops challenge"
datePublished: Wed Mar 05 2025 13:45:10 GMT+0000 (Coordinated Universal Time)
cuid: cm7vyzoyr000109l7hvh926hk
slug: week-4-of-12-weeks-aws-workshops-challenge
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cckf4TsHAuw/upload/b4a1523bf05eb5cdadfecfd9d93e7dc7.jpeg

---

# Aws Storage

## DAY 1 OF WEEK 4

imagine that you have a company that produce a large amount of data which cannot fit in an hard disk.One can always be afraid of having the data on hard disk since the hard disk can crash anytime.For such a situation,Cloud gets us sorted by providing a virtual storage called simple storage service simply called S3.

S3 comes with other advantages such as scalability,availability and durability,security among many other unstated advantages of S3

## S3 Security Best Practices

We are going to learn on how to use bucket policies, encryption, and VPC endpoints to secure your S3 buckets. We will also explore using AWS Config and IAM Access Analyzer to review your S3 security posture.

## a.Bucket Policies

Bucket policies and user policies are the access policy options available for granting permission to your Amazon S3 resources.

For our case we will create a S3 Bucket Policy that requires connections to use HTTPS so that permission to access the S3 bucket can be granted.

### 1\. SSH to the SID security instance

![Step 1 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/4fbb158e-c65c-42f1-a3b4-0c372046ed80/49e8e6b1-b897-4bcf-9342-4eff5b68dcd2.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=194&mark-y=33&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05ODAmaD00NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

![Step 2 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/6fa23fd1-5307-443b-850c-ef6b75078ab7/130ad172-5287-4460-a3e9-290149e5b956.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2.use this policy which only allows https request to access the instance only

![Step 3 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/7874aa2a-6c5e-4eb2-9ae5-831238265d26/7e64e266-6705-4069-9dff-5bfcc6e2eda5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=247&mark-y=277&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04MjUmaD0zMjkmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

![Step 5 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/1a6c4290-309b-49dc-88a4-54e5d4cba3fb/e950ef7f-d858-451f-96fd-8d1e196e875d.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

## b.Encryption

### 1\. Create a SSE KMS key

![Step 4 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/f49386a2-ed22-4b0c-87a1-3ab6f2b7ee6d/00682c79-74fb-415b-bff3-433572eecd9b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=234&mark-y=167&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NTEmaD02OSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 2.Create a text file and the server side encryption shall be AES256

![Step 7 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/bfbdf755-20b0-43aa-a2e8-dd882a26debe/334de4bd-027d-4ecb-94ed-5b0b6f3f42a5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 3\. Edit the default encryption from SSE-S3 to SSE-KMS

![Step 6 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/d01ef9f8-dbbe-4a93-92f3-4e15b4a48f15/6858621b-d868-4f20-872a-3b6aeb709553.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=16&mark-y=5&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTU3Jmg9NDQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 4.server side encryption is `aws:kms` instead of AES256

![Step 7 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/bfbdf755-20b0-43aa-a2e8-dd882a26debe/334de4bd-027d-4ecb-94ed-5b0b6f3f42a5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 5.How to ensure we enforce SSE-KMS but still allow any encryption for other prefixes.for in this case a policy which ensures that any file put in the SSE-KMS only prefix must have SSE-KMS encryption.

![Step 12 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/bf0b1069-739d-4a63-9e29-7b18b65462b9/be273bfc-869b-43b1-b193-b46b1152f4c0.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

## c) S3 VPC Endpoint

### 1\. Create a vpc endpoint

![Step 9 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/0d8836c7-0db2-4090-b879-912e99add502/fdf0c77f-5a11-4f8d-bea5-938848179258.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2\. Upon trying to access the the S3 even after updating a bucket policy,this does not work.Permission is forbidden.The reason for this is because our EC2 instance is accessing S3 via the internet gateway. This is because the VPC endpoint does not yet have a route table association.

![Step 10 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/aa5ea829-978e-4b10-bdb9-4e10d7a01f2a/f93ce458-5101-4067-a9e1-1f10a4bee3f4.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=10&mark-y=5&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTYzJmg9NDQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 3\. At this point we associated our SID route table to our newly created VPC endpoint so our EC2 instance can access S3 via the VPC endpoint instead of the internet gateway.

![Step 11 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/3bd22f9c-a693-4581-b5e3-acc3a47d8eb3/bc1d4104-aae6-4ddd-8790-7fb4c49541d5.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=42&mark-y=111&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTQ5Jmg9NzkmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 4\. This finally worked

![Step 12 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/bf0b1069-739d-4a63-9e29-7b18b65462b9/be273bfc-869b-43b1-b193-b46b1152f4c0.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

## d)AWS Config

This is a service which enables one to co

### 1\. At this moment,no bucket was public and therefore my S3 was compliant

![Step 13 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/33201182-5e7c-47f1-a70c-d9a174fd5e58/0e94b114-fdd8-44fe-84a1-fbd08e10bec3.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=238&mark-y=261&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yOTEmaD0xODImZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 2.At this point i used a policy which made my bucket publicly accessible

![Step 15 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/e4f5d05a-96ea-42fd-97df-ce6d28f4a3f9/5843353a-398c-495e-91b1-04539ae06057.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=16&mark-y=1&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTU3Jmg9NDQmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 3.Upon making my bucket public a notification pops up in config which tells me one of my bucket is public

![Step 14 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/0a0fd8f5-64d4-4ce3-b42c-20586e57de6d/8aa29d00-e791-4edf-9aa9-8bcbc2f1a9ad.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=9&mark-y=386&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTY0Jmg9MTMwJmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 16.Upon checking on the dashboard,one of my resource is non compliant

![Step 16 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/bc4c8005-c513-4f6d-83f4-24bbc005ccf5/f32771cc-47c4-41b4-b59d-b133a8ce2075.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=245&mark-y=225&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0yODkmaD0xODAmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 17\. Here is the rule which makes my bucket non compliant

![Step 17 screenshot](https://images.tango.us/workflows/e8825567-fb89-43ca-a433-f60bd6444c71/steps/679c8e49-af36-413f-b7cc-dea94f2999bd/e8850b35-3501-4721-a805-2a35cab80e67.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=246&mark-y=237&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz04OTUmaD03NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

## e).Access Analyzer

### 1.Input the name of resources you want to analyze

![Step 1 screenshot](https://images.tango.us/workflows/bfa37502-44e6-4c8a-ad62-667f02140e1d/steps/448c7ae4-0358-4061-b723-971a6f708c9b/8a5866f2-8ee6-4f33-97dd-840d19d2f087.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=235&mark-y=340&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05NjImaD04NCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 2.if the bucket is public,then the notification below will pop up

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1741182034600/0daf9372-432b-4bf4-accd-1f11f7ee8f74.png align="center")

## DAY 2 OF WEEK 4

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1741235813802/5aa861f6-2562-45d6-8156-4f09f5b4a78c.png align="center")