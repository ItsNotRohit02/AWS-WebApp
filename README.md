# Web Application Deployment on AWS

This repository contains the code and infrastructure setup for deploying a scalable and secure web application using AWS services, including Elastic Beanstalk, Amazon RDS, Amazon ElastiCache, and Amazon MQ. The project demonstrates a complete cloud infrastructure deployment, running within a custom VPC.

## Project Overview

The project involves the following key components:

- **Amazon Elastic Beanstalk:** Platform-as-a-Service (PaaS) for deploying and managing the web application.
- **Amazon RDS (MySQL):** Relational Database Service for managing the MySQL database.
- **Amazon ElastiCache:** Caching service to enhance application performance.
- **Amazon MQ:** Managed message broker service for asynchronous messaging.
- **Amazon Certificate Manager (ACM):** For SSL/TLS certificate management, linked to a domain hosted on GoDaddy.

## VPC Configuration

The application is deployed within a custom VPC in the `us-west-1` region, with the following configurations:

- **CIDR Block:** `172.20.0.0/16`
- **Subnets:**
  - **2 Public Subnets:** `172.20.1.0/24`, `172.20.2.0/24`
  - **2 Private Subnets:** `172.20.3.0/24`, `172.20.4.0/24`
- **Internet Gateway:** Enables internet access for resources in public subnets.
- **NAT Gateway:** Provides internet access to resources in private subnets.
- **Elastic IP:** Attached to the NAT Gateway for outbound traffic.
- **Route Tables:** 
  - **Public Route Table:** Routes traffic to the internet gateway.
  - **Private Route Table:** Routes traffic through the NAT gateway.
