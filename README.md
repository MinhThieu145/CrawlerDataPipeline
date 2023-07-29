# CrawlerDataPipeline

## Summary
This projects creates a pipeline for auto deployments of web crawlers to AWS resources. I have been testing my web crawler ability on several websites. But over time, building and updating those web crawlers manually become quite difficult. That why I create a pipeline for auto testing, storing and deployment several web crawler at the same time. 
## Tool and technology
- AWS: CodeBuild, Batch, S3, Lambda, EventBridge, Ec2, ECR
- IaC: AWS CDK
- Containerization: Docker
- Language: Python

## Architecture
For CI/CD deployment. Utilize codebuild go fetch code, containerize to create Docker image and upload to Ecr
![image](https://github.com/MinhThieu145/CrawlerDataPipeline/assets/88282475/3f2778d3-6732-4fc6-8fa3-a2c166caf2ff)

To run tasks on a daily basis: EventBridge can trigger Lambda function on schedule to pull and send batch job to AWS Batch. After the Batch job is done, the result will be stored in S3
![image](https://github.com/MinhThieu145/CrawlerDataPipeline/assets/88282475/08f086a1-85b0-47b8-9409-a3ca4b9484da)

