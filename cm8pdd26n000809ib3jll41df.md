---
title: "Text to Audio Conversion  Using Amazon Polly"
datePublished: Wed Mar 26 2025 03:32:47 GMT+0000 (Coordinated Universal Time)
cuid: cm8pdd26n000809ib3jll41df
slug: text-to-audio-conversion-using-amazon-polly
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1742955708265/ce58c18a-5f4a-49c6-9542-f4238693a0a6.png
tags: aws-aiml

---

## What is Amazon Polly?

Amazon polly is an ML service in aws cloud which converts text in to audio.Amazon polly can be very useful to people who really prefer listening to staff rather than reading.

### 1.Create a source and destination bucket

![Step 1 screenshot](https://images.tango.us/workflows/2ffe0c2d-be76-4892-a97e-3c318a97d883/steps/d96580d7-5160-40b0-859d-89d109ec02af/57b58dca-ed32-4158-934b-46029d5acb57.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 2.create a policy which shall allow lambda to access both s3 and polly

![Step 2 screenshot](https://images.tango.us/workflows/2ffe0c2d-be76-4892-a97e-3c318a97d883/steps/7723338c-eb9e-4c14-9ef1-7fac27a5b4c7/292f8960-e58f-4e27-96dd-196ee5f44f5b.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=236&mark-y=407&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05MzYmaD05OCZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 3\. Attatch the policy created together with AWSLambdaBasicExecutionRole policy to a single role

![Step 3 screenshot](https://images.tango.us/workflows/2ffe0c2d-be76-4892-a97e-3c318a97d883/steps/aeae5e34-c36d-4b1f-96ea-a64a59b2259f/36d81aca-fd61-4d76-ba8e-ad4c095aac0e.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=281&mark-y=268&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz01NSZoPTE5JmZpdD1jcm9wJmNvcm5lci1yYWRpdXM9MTA%3D align="left")

### 4\. create a Lambda function for this case its called Textspeechfunction

![Step 4 screenshot](https://images.tango.us/workflows/2ffe0c2d-be76-4892-a97e-3c318a97d883/steps/717ca0b0-ba3a-4025-80dd-e9609c27bbc7/c2aa4023-0dd7-4f09-9de8-9d167eada442.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=16&mark-y=161&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz05MjkmaD0yNDAmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

### 5.Click on Add trigger by selecting the service which initiates the trigger. For this case we are going to use S3

![Step 6 screenshot](https://images.tango.us/workflows/2ffe0c2d-be76-4892-a97e-3c318a97d883/steps/f961e3c2-2890-4089-96c3-9caf5d99b35f/a74144b4-48b4-4c03-a36f-e302e409bbcf.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=23&mark-y=308&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz0xMTYmaD0zMSZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw align="left")

### 6.configure a trigger which initiates the lambda function incase a .txt file is uploaded in the source s3 bucket

![Step 5 screenshot](https://images.tango.us/workflows/2ffe0c2d-be76-4892-a97e-3c318a97d883/steps/46c53539-073d-42f6-8d2e-2ae3b5a998b6/ca89353e-9dfb-4608-ae13-0344f0d23c08.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n align="left")

### 7\. Enter the code which shall be used by the Textspeechfunction

![Step 7 screenshot](https://images.tango.us/workflows/2ffe0c2d-be76-4892-a97e-3c318a97d883/steps/a3541c90-c2dc-404b-9e88-fae0b04b1352/55ea8abb-95c6-406b-b9cc-92796c3ecb02.png?crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=283&mark-y=150&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTMlMkNGRjc0NDImdz02NjImaD00NjMmZml0PWNyb3AmY29ybmVyLXJhZGl1cz0xMA%3D%3D align="left")

9.Navigate to S3 and upload a .txt file at the source bucket.After a while, a corresponding .mp3 file shall appear at the destination bucket.Download the audio and listen.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1742958790434/fe97c6ad-91f7-4557-8cfb-3c35587afd7e.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1742958840404/bb0717ef-4e40-4e05-82dd-f9b69e6b38f1.png align="center")