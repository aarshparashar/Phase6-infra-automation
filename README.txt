## Three-Tier Web Application Deployment - MERN Stack WA

# Automation
Deploy the infra using Terraform modules from official AWS Github repositories here https://github.com/terraform-aws-modules. 
Resources to be created using these terraform modules
VPC
3 X MongoDB instances
NodeJS AMI using Packer
NodeJS ASG
NodeJS ALB
Specifications for HA deployment
VPC with 3 tiers of subnets - public, private and database subnets
Set up MongoDB 3-node replica set on 3 X EC2 instances using private IP addresses. Enable login authentication and Use the correct Mongo_URI string in application.
Test the mongodb deployment by stopping a node and then starting it. it should recover and primary should also change to a healthy host.
Understand the election process and heartbeat in the mongo cluster. https://www.mongodb.com/docs/manual/core/replica-set-elections/
Set up NodeJS backend  ( using PM2 ). Understand pm2.json , environments, logs etc. 
Configure AWS Auto Scaling Based on both CPU and Memory Utilization https://aws.plainenglish.io/hello-everyone-2eeb0515c0f5 .
use spot allocation strategy in ASG
End-to-end TLS encryption with ALB and nginx/apache. Since ALB has strict name checking disabled by default, we can use any self signed certificate in the webserver config
Frontend deployment using AWS Amplify

# CI/CD
Using .env files in above repositories
Getting env values from aws secrets-manager and creating .env file using template
Pass value of backend endpoint as environment variable in Amplify and use it inside amplify.yaml.
pipeline notifications on slack 

# Observability
Setup monitoring of Network, Servers, ASGs , ALB and Database. Configure alerts to slack
Setup Retention policies for log groups ,metric filter and notification using SNS
Ship logs of pm2 services to cloudwatch logs
