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

## S3 Storage Performance

### a.Optimize throughput

### 1\. SSH to your currently and then update it

![Step 1 screenshot](https://images.tango.us/workflows/152f59ce-baf2-4f99-a85f-65e04163b0f8/steps/ab1bd21e-ef62-47a1-aadd-f71bb670c1b1/8f1958f7-872a-44d0-9f29-70592e5a5698.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2\. Configure the AWS CLI S3 settings and after that confirm the CLI configuration.Finally create a create a 1GB file

![Step 2 screenshot](https://images.tango.us/workflows/152f59ce-baf2-4f99-a85f-65e04163b0f8/steps/2e2faa85-89b2-485c-ba49-eee6a86860dc/42354485-06c0-4d6c-baed-9ec966754703.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 3\. Upload a 1 GB file to the S3 bucket using 1 thread,2 thread,10 thread and 20 threads and note the time difference.

![Step 1 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/922f6f4b-b7ef-477f-a344-16bba9f426c2/f321d05b-2ec1-4c3f-982c-2d44c3495a82.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### b.Optimizatin using Sync Command

We gonna use sync command to synchronizes the contents of a bucket and a directory

1.we wanna perform sync using 1 thread and 10 threads.We notice that multiple threads decreased the time needed to move the files.

![Step 5 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/28d111a2-6a2a-4953-98c9-40cb32e5a1ed/cdaf684c-98cc-4aa1-b98e-4b38eee54dd6.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=319&mark-y=574&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMyZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### c. Small files Operations

Anyone gets bothered on the time to be taken for them to transfer data to S3.Transferring data in small files does it very fast.Lets demonstrate:

### 1.create a text file that represents a list of object ids.The created files are 500

![Step 6 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/e253c663-e43d-4d48-a4d1-1a60483ba08c/18c50d52-2b3d-443e-a3d7-25ea94a70df6.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2\. Lets proceed and create a one KB file and upload 500 1KB files to S3 using 5 threads. Record the time to complete.

![Step 7 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/0532ad73-54e1-4e60-8819-ff57c9a0cc93/605ca509-d336-4312-8e45-d8c6906267bb.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 3\. upload 500 1KB files to S3 using 15 threads,50 and 100 threads. Record the time to complete.

![Step 8 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/2dbf56e5-b57c-48ed-996f-8637b003422d/166a2cb8-10ef-4ea1-8604-99382edd8846.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=3&mark-y=476&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTc3Jmg9MTkmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

The higher the number of threads then the higher the performance

![Step 10 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/db946d9f-2797-4f3f-aa98-009eef8a035d/a831c8ef-4b48-4677-b4ab-88656fb1ebce.png?crop=focalpoint&fit=crop&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### d)Copy Operation

### 1.Download a file from S3 and then upload it back using a different prefix

![Step 11 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/457f5e1b-6183-4231-9c99-ccbea2d31ea0/75e5c4ef-7e2b-4fcc-8a33-8416059b5a90.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2\. Now run the command below to copy objects in the bucket

![Step 12 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/3222e635-2abb-4fc6-9b16-70b1cd684053/dc8ceb20-7907-4144-bbe2-198ddeb27fb2.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 3\. copy the file between S3 using a single command between locations

![Step 13 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/eb1422eb-bd1e-457c-9a0c-82b3a0287fc2/684f9b3d-abc9-4267-afb1-6f54c2cbed5b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### e. EFS - Optimize IOPS

1.Let us generate 1,024 zero byte files. Record time to complete,generate 1,024 zero byte files using multiple threads this time out and Record time to complete.lastly we are going to generate 1,024 zero byte files in multiple directories using multiple threads. Record time to complete.

![Step 14 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/a7b821f9-87b3-4753-93a0-d97b5ae8eb89/3c30123b-e62d-44a8-8ec7-b11ed52cc99e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

we finally conclude that the best way to make use of the distributed data storage design of Amazon EFS is to use multiple threads which makes it faster

### EFS - I/O Size and Sync Frequency

1.write a 2GB file to EFS using 1MB block size and sync once after each file. Record time to complete.

write a 2 GB file to EFS using 16MB block size and sync once after each file. Record time to complete.

write a 2GB file to EFS using 1MB block size and sync after each block. Record time to complete.

write a 2 GB file to EFS using 16MB block size and sync after each block. Record time to complete.

![Step 15 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/2141e092-de5e-4daf-aab2-b504fd96d39f/50449420-5c87-43fd-b9d2-6580a6ae0b35.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

we therefore draw a conclusion that Syncing after each block dramatically decreases the performance of the file system. Optimal performance is obtained by syncing after each file.

### EFS - Multi-threaded

1.write 2GB of data to EFS using 1MB block size and 4 threads. Record time to complete.

![Step 16 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/225e36ed-f03b-415a-8c3c-cc326dd9802d/dd953c45-1a32-4c9b-94db-5ebe2d620c70.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2.write 2GB of data to EFS using 1MB block size and 16 threads. Record time to complete.

![Step 17 screenshot](https://images.tango.us/workflows/b1343072-3757-475a-a0ea-806d34996d45/steps/02224b43-eaa6-4d66-9c2c-52c4dce116c4/0a06370f-0a9e-439c-a3f2-a034e8ae06d1.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

we finally conclude that:By parallelization your writes to EFS by increasing the number of threads, you can increase the overall throughput and IOPS to EFS.

## DAY 3 OF WEEK 4

## AWS BACKUP