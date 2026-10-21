# Event-Driven File Processing with AWS S3 and SQS

A small **serverless integration exercise** demonstrating event-driven processing with **Amazon S3, Amazon SQS, and AWS Lambda**.

## Architecture

1. A CSV file is uploaded to an S3 bucket.
2. An S3 `ObjectCreated` event invokes the `s3listener` Lambda.
3. A separate `sqslistener` Lambda consumes messages from an SQS queue.

The repository is a learning/reference implementation, rather than a production-ready deployment.

## Technology

- Node.js and AWS Lambda
- Amazon S3 and Amazon SQS
- Serverless Framework
- LocalStack and Serverless Offline for local experimentation

## Getting started

Install the dependencies with `npm install`. Review `serverless.yml`, update environment-specific resources, and configure valid AWS credentials before attempting an AWS deployment.

The `package.json` includes scripts for running Serverless Offline and invoking the S3 and SQS listeners locally.

> **Compatibility note:** This project was originally built using the Node.js 12.x Lambda runtime and older Serverless tooling. Treat it as a historical architecture exercise and update its runtime, dependencies, resource names, and IAM policies before deploying it.

## What this demonstrates

Separating storage events from queue consumption is a useful foundation for decoupled workflows, buffering, and asynchronous processing. For a production implementation, additional considerations include retries, dead-letter queues, idempotency, observability, and least-privilege IAM.
