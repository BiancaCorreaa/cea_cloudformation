AWS Network Project: Building a Secure VPC with Code

In this project, I built a professional network environment on AWS using CloudFormation. Instead of setting everything up manually, I used Infrastructure as Code (IaC) to make the deployment fast, consistent, and easy to manage.

The Goal of the Project
The main idea was to create a network that is both secure and reliable. I designed it to keep the most important parts of the application hidden from the internet while making sure the system stays online even if a data center has a problem.

Key Features
Reliability (Multi-AZ) I spread the resources across two different Availability Zones. This means that if one AWS data center fails, the application can keep running in the second one.

Network Organization I divided the network into three layers:

Public Layer: For things that need to talk to the internet.

Application Layer: For the main code and logic.

Data Layer: For sensitive information and databases.

Security First I followed a "safety-first" approach:

Private Servers: The application servers are in private sections. They do not have public IP addresses, so they cannot be reached directly from the internet.

The Bastion Host: I set up a "front door" server called a Bastion Host. This is the only way to access the private servers for maintenance.

Restricted Access: I configured the security rules so each part of the system only talks to the parts it absolutely needs to.

Why This Matters for a Business
Using code to build a network like this saves time and prevents human error. It also makes the environment much harder to hack because the most important parts are hidden behind multiple layers of security.

This project shows my ability to plan a cloud network, automate the setup, and follow industry security standards.

How to Run It
You can deploy this entire setup using the AWS CLI with this simple command:

Bash

aws cloudformation create-stack \
--stack-name my-vpc-stack \
--template-body file://template.yaml \
--capabilities CAPABILITY_NAMED_IAM
