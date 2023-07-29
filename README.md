# CrawlerDataPipeline

## Summary
CrawlerDataPipeline is a comprehensive project that streamlines the process of deploying web crawlers to AWS resources automatically. The motivation behind this project stems from the challenges faced while testing web crawlers on various websites. As the number of web crawlers grew, managing and updating them manually became increasingly cumbersome. To address this issue, CrawlerDataPipeline offers an automated pipeline that facilitates testing, storage, and deployment of multiple web crawlers concurrently.

## Tools and Technologies
The CrawlerDataPipeline leverages a combination of powerful tools and cutting-edge technologies to achieve its objectives:

- AWS Services: The project makes use of several AWS services, including CodeBuild for fetching code, AWS Batch for processing batch jobs, S3 for data storage, Lambda for executing functions, EventBridge for scheduling tasks, EC2 for running the application, ECR for container image storage, and VPC for networking.

- Infrastructure as Code (IaC): AWS Cloud Development Kit (CDK) is utilized to define and provision the AWS infrastructure in a programmable manner, enabling easy management and reproducibility.

- Containerization: Docker containers are employed to package the web crawlers and their dependencies, ensuring consistency across different environments.

- Language: The primary language used for implementing the project is Python, known for its versatility and extensive libraries that support web crawling and data processing.

## Tutorial
For those interested in recreating the CrawlerDataPipeline system, a detailed step-by-step tutorial is available at the following link: [CrawlerDataPipeline Tutorial](https://s3.console.aws.amazon.com/s3/buckets/awsworkshop1?region=us-east-1&tab=properties)

## Architecture
The architecture of CrawlerDataPipeline consists of several interconnected components, facilitating a seamless and efficient workflow:

1. CI/CD Deployment: The Continuous Integration and Continuous Deployment (CI/CD) process is initiated through CodeBuild, which fetches the latest code. The fetched code is containerized into a Docker image and subsequently uploaded to the Elastic Container Registry (ECR) for versioning and storage.
![image](https://github.com/MinhThieu145/CrawlerDataPipeline/assets/88282475/30d6f5d6-cd16-4641-abc2-fba056687483)


2. Daily Task Execution: EventBridge, a serverless event bus, is utilized to trigger a Lambda function on a scheduled basis. This Lambda function orchestrates the process of pulling data and dispatching batch jobs to AWS Batch for execution. Upon completion of the batch job, the results are securely stored in an S3 bucket.
![image](https://github.com/MinhThieu145/CrawlerDataPipeline/assets/88282475/6fc05b8e-4dd2-4c71-822a-059693e5bb21)

3. High Availability Application: The CrawlerDataPipeline incorporates a two-tier, high availability application to facilitate result visualization. The application is built using Streamlit and is hosted on a public EC2 instance residing within an Auto Scaling Group. An Elastic Load Balancer (ELB) is employed to evenly distribute incoming traffic among multiple EC2 instances, ensuring the system remains resilient and scalable. The EC2 instances securely connect with the S3 bucket using the S3 Gateway, allowing them to retrieve the requested data for display.
![image](https://github.com/MinhThieu145/CrawlerDataPipeline/assets/88282475/c7f2d4df-a61b-4197-bb6b-225d65c18684)

