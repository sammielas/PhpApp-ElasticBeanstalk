# Deploying a PHP App on AWS using Elastic Beanstalk

## Overview
This repository contains a step-by-step guide on how to deploy a PHP application on AWS using Elastic Beanstalk. The guide covers the essential setup and configurations needed to launch and manage a PHP application on the AWS cloud infrastructure. You will learn to create networking components, set up a database, and integrate with AWS services like S3 and Systems Manager Parameter Store.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Step-by-Step Deployment Guide](#step-by-step-deployment-guide)
   - [Step 1: Create a VPC](#step-1-create-a-vpc)
   - [Step 2: Create a NAT Gateway](#step-2-create-a-nat-gateway)
   - [Step 3: Create Security Groups for the Database](#step-3-create-security-groups-for-the-database)
   - [Step 4: Create an RDS Instance](#step-4-create-an-rds-instance)
   - [Step 5: Create IAM Role for Elastic Beanstalk](#step-5-create-iam-role-for-elastic-beanstalk)
   - [Step 6: Add Parameters in Parameter Store](#step-6-add-parameters-in-parameter-store)
   - [Step 7: Create an S3 Bucket](#step-7-create-an-s3-bucket)
   - [Step 8: Create an Elastic Beanstalk Application](#step-8-create-an-elastic-beanstalk-application)
   - [Step 9: Package the Application Code](#step-9-package-the-application-code)
   - [Step 10: Deploy the Code](#step-10-deploy-the-code)
   - [Step 11: Clean Up Resources](#step-11-clean-up-resources)
3. [How to Use](#how-to-use)
4. [Contributors](#contributors)
5. [License](#license)
6. [Further Reading](#further-reading)

## Prerequisites
Before starting, ensure you have the following tools and resources:
- An AWS account
- AWS CLI installed and configured
- PHP application ready for deployment
- Basic knowledge of AWS services such as VPC, RDS, S3, IAM, and Elastic Beanstalk
- Access to AWS Elastic Beanstalk and RDS services

## Step-by-Step Deployment Guide

### Step 1: Create a VPC
- Set up a Virtual Private Cloud (VPC) with **public and private subnets** across two availability zones (AZs). This ensures high availability for your application.

### Step 2: Create a NAT Gateway
- In the public subnets of your VPC, set up a **NAT gateway**. This allows instances in private subnets to access the internet while remaining secure.

### Step 3: Create Security Groups for the Database
- Create and configure **security groups** to control access to your RDS instance. The security group will define which traffic is allowed to and from the database.

### Step 4: Create an RDS Instance
- Launch a **Relational Database Service (RDS)** instance to serve as the backend database for your PHP application.

### Step 5: Create IAM Role for Elastic Beanstalk
- Create an **IAM role** that allows Elastic Beanstalk to interact with other AWS services like S3 and the Systems Manager Parameter Store.

### Step 6: Add Parameters in Parameter Store
- Use the **AWS Systems Manager Parameter Store** to store configuration details and secrets (such as database credentials) that your application will access securely.

### Step 7: Create an S3 Bucket
- Set up an **S3 bucket** to store files uploaded through your PHP application’s form.

### Step 8: Create an Elastic Beanstalk Application
- Create and configure a new **Elastic Beanstalk application** to host your PHP app.

### Step 9: Package the Application Code
- **Zip** your PHP application code and ensure all dependencies and configurations are included for deployment.

### Step 10: Deploy the Code
- Upload the zipped code to Elastic Beanstalk and deploy the application. Elastic Beanstalk will handle provisioning, load balancing, and scaling.

### Step 11: Clean Up Resources
- Once the application is deployed and tested, remember to delete unused AWS resources (VPCs, RDS instances, S3 buckets, etc.) to avoid unnecessary charges.

## How to Use
1. Follow the step-by-step guide to configure your AWS environment.
2. Ensure your PHP application is zipped and ready for deployment before proceeding to the Elastic Beanstalk steps.
3. After deployment, use the AWS console to monitor and manage the application’s performance and logs.
4. Clean up the resources after completing the deployment to avoid ongoing charges.

## Further Reading
- [AWS Elastic Beanstalk Documentation](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html)
- [PHP on AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/php.html)
- [AWS VPC Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
