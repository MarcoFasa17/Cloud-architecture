CloudFormation Test Task: Simple 3-Tier AWS Architecture

This project provides a simple, well-structured, three-tier architecture deployed using a single AWS CloudFormation YAML template (template.yaml). The architecture consists of one public subnet (hosting a web server) and one private subnet (hosting a database), demonstrating foundational AWS networking and resource configuration.

🎯 Architecture Objective

The primary goal was to deploy the following components within a custom VPC using CloudFormation:

Networking: VPC, Internet Gateway, and a simplified two-subnet model (one Public, one Private).

Web Tier (Public): A simple EC2 instance running a basic HTTP server, accessible via the public internet.

Data Tier (Private): An RDS MySQL instance placed in the private subnet, secured by a Security Group that allows inbound traffic only from the EC2 instance's Security Group.

Storage Tier: An S3 Bucket for general storage, with a compliant, all-lowercase name generated using !Sub.

📂 Project Files

Architecture_diagram.png # this architecture 
resources.png andoutput.png # shoe sandbox results
diagram.html #general architecture standard
infrastracture_composer #AWS extensions integrated in VS code that generates a diagraf of all the resources used
template.yaml #run it in AWS cloud formation as new stack

The complete CloudFormation YAML template defining all resources and their dependencies, as per the task requirements.

infrastructure_diagram.png

Infrastructure diagram automatically generated from template.yaml.

aws_console_screenshot.png

Screenshot verifying the successful stack deployment and outputs.

🚀 Post-Deployment Access

Upon successful deployment, you can verify the EC2 web server is running:

Navigate to the Outputs tab of the CloudFormation stack.

Copy the value of the EC2PublicIP output (e.g., http://X.X.X.X).

Paste this IP address directly into your web browser (e.g., Google Chrome) to view the static HTML page provisioned by the UserData script.

🖼️ Documentation and Verification

To ensure the template correctly translates into the intended architecture, the following documentation artifacts have been created:

1. Infrastructure Diagram

The architectural diagram (infrastructure_diagram.png) was auto-generated from the provided template.yaml using the Infrastructure Composer feature of the AWS Toolkit extension on VS Code. This visual representation confirms the correct relationships between the Public Subnet (EC2) and the Private Subnet (RDS).

2. Successful Deployment Screenshot

The aws_console_screenshot.png file provides visual proof of the successful stack deployment in the Sandbox environment. This confirms the resources, including the VPC, EC2, and the S3 Bucket (with its now compliant, all-lowercase name), were created without error.