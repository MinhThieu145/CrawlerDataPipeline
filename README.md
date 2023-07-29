# CrawlerDataPipeline: Automated Web Crawler Deployment and Data Processing on AWS

## Summary
CrawlerDataPipeline is a comprehensive project that addresses the challenges of manual web crawler deployment, testing, and updates by providing an automated pipeline for efficient management of web crawlers on AWS resources. The system facilitates simultaneous testing, storage, and deployment of multiple web crawlers, significantly streamlining the entire process.

## Objectives
The main objectives of CrawlerDataPipeline are as follows:
1. Develop an automated deployment system for web crawlers on AWS.
2. Provide a seamless testing environment for web crawlers across various websites.
3. Implement an efficient data storage mechanism to handle the results obtained from web crawlers.
4. Utilize containerization to enhance scalability and portability of web crawlers.
5. Establish a user-friendly interface for accessing and visualizing the web crawler results.

## Tools and Technologies
CrawlerDataPipeline utilizes a powerful set of tools and technologies to achieve its objectives:
- **AWS Services:** The project leverages various AWS services, including CodeBuild, AWS Batch, S3, Lambda, EventBridge, EC2, ECR, and VPC, to facilitate automated deployment and data processing.
- **Infrastructure as Code (IaC):** AWS Cloud Development Kit (CDK) is employed to define the cloud resources as code, enabling easier management and version control.
- **Containerization:** Docker is used to containerize the web crawlers, allowing for seamless deployment and scalability.
- **Programming Language:** Python is the language of choice for writing the web crawlers and other associated components.

## Tutorial
For those interested in setting up the CrawlerDataPipeline, a comprehensive tutorial is available [here](https://s3.console.aws.amazon.com/s3/buckets/awsworkshop1?region=us-east-1&tab=properties). This tutorial guides users through the step-by-step process of building the system, offering clear instructions and explanations for each component.

## Architecture
CrawlerDataPipeline employs a robust and scalable architecture to ensure efficient deployment and data processing:

1. **Continuous Integration and Continuous Deployment (CI/CD):**
   - Use AWS CodeBuild to fetch the web crawler code from your version control repository (e.g., GitHub).
   - Define the build specification to install necessary dependencies and prepare the crawler code for containerization.

```yaml
# buildspec.yml
version: 0.2
phases:
  install:
    commands:
      - pip install -r requirements.txt
  build:
    commands:
      - python prepare_crawler.py
artifacts:
  files:
    - crawler_code/
