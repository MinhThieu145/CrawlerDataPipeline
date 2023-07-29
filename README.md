CrawlerDataPipeline: Automated Web Crawler Deployment and Data Processing on AWS
Summary

CrawlerDataPipeline is a comprehensive project that addresses the challenges of manual web crawler deployment, testing, and updates by providing an automated pipeline for efficient management of web crawlers on AWS resources. The system facilitates simultaneous testing, storage, and deployment of multiple web crawlers, significantly streamlining the entire process.
Objectives

The main objectives of CrawlerDataPipeline are as follows:

    Develop an automated deployment system for web crawlers on AWS.
    Provide a seamless testing environment for web crawlers across various websites.
    Implement an efficient data storage mechanism to handle the results obtained from web crawlers.
    Utilize containerization to enhance scalability and portability of web crawlers.
    Establish a user-friendly interface for accessing and visualizing the web crawler results.

Tools and Technologies

CrawlerDataPipeline utilizes a powerful set of tools and technologies to achieve its objectives:

    AWS Services: The project leverages various AWS services, including CodeBuild, AWS Batch, S3, Lambda, EventBridge, EC2, ECR, and VPC, to facilitate automated deployment and data processing.
    Infrastructure as Code (IaC): AWS Cloud Development Kit (CDK) is employed to define the cloud resources as code, enabling easier management and version control.
    Containerization: Docker is used to containerize the web crawlers, allowing for seamless deployment and scalability.
    Programming Language: Python is the language of choice for writing the web crawlers and other associated components.

Tutorial

For those interested in setting up the CrawlerDataPipeline, a comprehensive tutorial is available here. This tutorial guides users through the step-by-step process of building the system, offering clear instructions and explanations for each component.
Architecture

CrawlerDataPipeline employs a robust and scalable architecture to ensure efficient deployment and data processing:

    Continuous Integration and Continuous Deployment (CI/CD):
        The code for the web crawlers is fetched using AWS CodeBuild.
        The code is containerized to create a Docker image, which is then uploaded to the Elastic Container Registry (ECR).

    CI/CD Architecture

    Daily Scheduled Web Crawling:
        AWS EventBridge is configured to trigger a Lambda function on a daily schedule.
        The Lambda function initiates a batch job on AWS Batch, which executes the web crawlers.
        Upon completion, the results obtained from the crawlers are stored in an S3 bucket.

    Daily Scheduled Web Crawling

    Web Application for Data Visualization:
        The system includes a two-tier, high availability application that uses Streamlit for result visualization.
        The application is deployed on a public EC2 instance within an Auto Scaling Group to ensure scalability and fault tolerance.
        An Elastic Load Balancer is employed to evenly distribute incoming traffic between EC2 instances to prevent overloading.
        The EC2 instances securely load the requested data from the S3 bucket using the S3 Gateway.

    Web Application Architecture

Conclusion

CrawlerDataPipeline is a comprehensive solution that automates the deployment, testing, and data processing of web crawlers on AWS. By utilizing advanced technologies and best practices, the project enables users to efficiently manage and analyze data from multiple web sources, significantly reducing manual efforts and enhancing productivity.
