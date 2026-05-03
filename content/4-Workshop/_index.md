---
title: "Workshop"
date: "2025-12-07"
weight: 40
chapter: false
pre: " <b> 4. </b> "
---

# Serverless Student Management System on AWS

## Overview

**Serverless Student Management Platform** is a cloud-based student management solution, cost-effective and flexible scalability thanks to the use of **AWS Serverless** services (Lambda, DynamoDB, API gateway...). The platform supports up to 50-100 students initially, with the ability to flexibly expand to 500–1000 students without major infrastructure changes.

Core services: API Gateway (REST), Lambda handles business logic, DynamoDB stores data, Amplify (frontend React), Cognito (user authentication), CloudWatch (monitoring), combined with modern DevOps CI/CD processes.

## Contents

1. [System Overview and Architecture](5.1-Workshop-overview/) - Understand the serverless architecture and key components
2. [Environment Preparation & AWS Account Setup](5.2-Prerequiste/) - Install tools and configure AWS credentials
3. [Backend Deployment: DynamoDB, Lambda, API Gateway, Cognito](5.3-Backend/) - Deploy backend infrastructure and services
4. [Frontend Development: Amplify, Route 53, CloudFront, WAF](5.4-Frontend/) - Build and deploy React frontend with CDN
5. [CI/CD Pipeline](5.5-CI-CD/) - Set up automated build, test, and deployment
6. [CloudWatch Monitoring](5.6-Cloud-Watch/) - Configure logging, dashboards, and alarms
7. [Clean up](5.7-Clean-up/) - Properly remove AWS resources to avoid costs

## Experience Objectives

- Understand and implement multi-tier serverless architecture on AWS, operate with key services.
- Master authorization and user authentication with Cognito.
- Practice building CRUD functions.
- Experience modern DevOps process: automate build, test, deploy through CI/CD pipeline.
