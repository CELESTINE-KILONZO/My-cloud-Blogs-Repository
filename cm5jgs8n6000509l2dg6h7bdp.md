---
title: "Besa program:Week 03-Getting started  with Amazon Bedrock"
datePublished: Sun Jan 05 2025 10:22:50 GMT+0000 (Coordinated Universal Time)
cuid: cm5jgs8n6000509l2dg6h7bdp
slug: besa-programweek-03-getting-started-with-amazon-bedrock
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1732513941684/bc37610d-1969-486a-a015-0923567b61d0.png

---

## What is Amazon Bedrock?

This is an AWS service that provides easiest way to build and scale generative AI applications with foundation models.

## Simple White boarding

imagine that you have an insurance company and you have a website for the same.People who have bought new cars will come in your website wanting to create a claim.Others might have made an accident and want to initiate a claim.At some point these tasks may be too much and human agents may not be able to serve all the customers.This is where the virtual agents come in.They are in a position to do all the asks which a human agent can do.This is the point where Amazon bedrock comes in.

## Features of Amazon Bedrock

Playground-Help one to choose the model which fits their use case.it is at the playground where One can check if the model fulfills there use case before deploying it.

Model customization-this apples when you get a model which was trained a while ago.One can be able to train the model using their own current data

Retrieval Augmented Generation (RAG)-This is whereby one feeds in their data to the model to make it respond to their questions as they expect.

This service furthermore provides virtual Agents that execute multi step tasks

## Amazon Bedrock simplifies:

Choice

Customization

Integration

Security and governance

## Examples Amazon Bedrock Models

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735998394282/8050fdf2-ce11-4a30-bed9-5a9dfe894ab7.png align="center")

Each model in AWS has its own specialty for instance one uses anthropic clot to create chat application and titanic or stability diffusion generate images.

## Model evaluation in Amazon Bedrock

Models are evaluated so that one can choose the best for their use case

### ways of evaluating models

Automatic evaluation method-This method of model evaluation is accurate and prevents robustness

Using human evaluation method-this method one uses their team or AWS team to evaluate the model

## Approach for customizing foundational models

Prompt engineering-A prompt is a inquiry which one does in a chatbot.One makes use of curated prompts

and provide context i their prompt.The quality of their prompts shall determine the output

RAG-One attaches external source to the application and it is going to pick up context from there

Fine-tuning-one keeps on tuning a model to make it do a particular task well.labelled data is used.

Continued pre training-one trains their model using unlabeled data to increase its accuracy

## How RAG works

One connects RAG to their data source e.g S3

Whatever data comes in to your data source is chunked in to small pieces

The chunked data is then embedded.**embedding** as a way to convert words, sentences, or even images into numbers that a computer can understand. Instead of storing words as plain text, we turn them into **vectors**

The embedded data is now then taken to the vector store.e.g Open Search serverless

when one asks a query,a search is made at the knowledge base and still at the vector store

After a search is made,the user input and the query are now augmented and then later sent to the model

The model then gives a response

in case you want a managed service which does the RAG part for you,then knowledge basis Amazon bedrock is there for you.

## Summary Diagram

![](https://img001.prntscr.com/file/img001/Do0WeRpFTdePhKhUV3bE7g.png align="left")

## New data sources for Amazon Bedrock Knowledge Bases

Web crawler-one can send a crawler to a static website and index the data as your input

Atlassian Confluence

Microsoft Share Point

Salesforce

## Amazon Bedrock agents

Agents are used to break down complex tasks to simple tasks.

![](https://img001.prntscr.com/file/img001/mc17dELgTWC4XDSQjt8AjQ.png align="left")

To learn more about agents [click here](https://aws.amazon.com/blogs/machine-learning/automate-the-insurance-claim-lifecycle-using-amazon-bedrock-agents-and-knowledge-bases/).

## Amazon Bedrock Guardrails

Amazon Bedrock protects the model from hallucination.i also preventing people from entering bad prompts to the model.

### step by step procedure on how Guardrails works:

Evaluate prompts and model responses for agents, knowledge bases, FMs in Amazon Bedrock, and custom or third-party FMs

Configure thresholds to filter harmful content, jailbreaks and prompt injection attacks

Define and disallow denied topics with short natural language descriptions

Remove personally identifiable information (PII) and sensitive information in gen AI apps

Filter hallucinations by detecting groundedness and relevance of model responses based on context

## Amazon Bedrock Security

Amazon bedrock security keeps your data application and data both secure and private.

None of the customer’s data is used to train the underlying models.

All data is encrypted in transit and at rest; data used for customization is securely transferred through customer’s VPC

Data remains in the Region where the API is processed.

Bedrock is conformant with FedRAMP High, GDPR, SOC, ISO, and CSA compliance support and HIPAA eligibility.

The above ensures security while using amazon bedrock.

## Amazon Bedrock Pricing

Amazon Bedrock pricing depends on your input and output tokens.

### On demand

Pay-as-you-go, no commitment

Pricing is based on input and output token count for LLMs

Great for prototyping, POCs, and small workloads with more relaxed requirements for throughput and latency

Requests per minute (RPM) and tokens per minute (TPM) limits enforced

### Provisioned throughput

Provision sufficient throughput to meet your application’s performance requirements

Throughput (input and output tokens per minute) reserved at a fixed cost Flexible commitment term of 1 month or 6 months

Hourly PT (2MU), no commitment, across different models

Hourly rate, discounted for extended commitment

Great for production workloads or inference on custom models

## Batch inference

Amazon Bedrock offers select FMs from leading AI providers like Anthropic, Meta, Mistral AI, and Amazon for batch inference at 50% of on-demand inference pricing

Efficiently run model inference on large volumes of data

Avoids throttling when running large jobs

Used when you are getting a large number of request and you want to aggregate those responses and analyze in batch.

## Amazon Bedrock Studio

This is a web based interface made for rapid prototyping for developers so as to build,evaluate and share generative AI applications.

it has easy-to-use playground

Provide project-based collaboration

Provides access with corporate SSO

it was such a nice and enlightening session🔥🔥🔥.

💪 #Besa #AWS Bedrock #AWS #Technology #Innovation #ContinuousLearning