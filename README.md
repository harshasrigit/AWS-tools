# AWS-tools 

# Scenario: AWS Cloud Infrastructure Setup for a New Application
Your team has been assigned the task of setting up the foundational AWS infrastructure for a new web application that will be deployed in AWS. The application will require resources like IAM groups for different teams, EC2 instances for computing, S3 for static content, and a secure VPC networking setup.
Company Requirement:
The company has three different teams—Monitoring, Security, and Cloud Team—each with distinct roles and responsibilities. They need the appropriate IAM groups and permissions set up to manage and access specific AWS resources. The web application itself will be hosted on EC2 instances with attached EBS volumes, and the static content will be stored in an S3 bucket. For networking, the VPC should be configured with both public-facing and private subnets, along with secure connectivity between two regions via VPC peering.

# Task Breakdown:

1. IAM Setup for Different Teams
The company has defined three core groups that need specific permissions based on their job functions:
Monitoring Team: They are responsible for monitoring the health and performance of AWS resources and applications. You need to create an IAM group for them with read-only access to monitoring services like CloudWatch and IAM.
Security Team: This team handles security configurations and audits. They need full access to manage security settings, IAM, and encryption keys. You must create an IAM group with necessary permissions to handle these tasks.
Cloud Team: The Cloud Team manages the deployment, infrastructure setup, and maintenance. This team requires full administrative access to all AWS resources.
Deliverables:
Create IAM groups for Monitoring, Security, and Cloud teams.
Attach appropriate policies to these groups to reflect the job functions.



2. EC2 and EBS Setup
The web application requires a compute resource and data storage:
The application will run on a t2.micro EC2 instance using an Amazon Linux 2 AMI.
The application will store its data on an EBS volume of 10 GiB. This volume should be backed up using snapshots to ensure data resilience.
To allow scaling and reuse, create an AMI from the running EC2 instance for future launches.
Deliverables:
Launch an EC2 instance (t2.micro) with Amazon Linux 2 AMI.
Attach a 10 GiB EBS volume to this instance.
Create a snapshot of the attached EBS volume.
Create an AMI from the running EC2 instance.

3. S3 Setup for Static Website and Data Lifecycle Management
The application also includes static web content (like images, CSS, JavaScript), which will be hosted on S3. In addition to this, version control and lifecycle management are necessary to optimize storage costs.
Create an S3 bucket that will serve as a static website, hosting files such as index.html and error.html.
Enable versioning on the bucket to keep track of file changes.
Implement a lifecycle policy that moves objects to Glacier after 30 days and deletes them after 1 year to manage long-term costs.
Deliverables:
Create an S3 bucket with static website hosting enabled.
Upload a sample index.html file to test the website.
Enable versioning on the bucket.
Implement a lifecycle policy for moving objects to Glacier after 30 days and deleting them after 365 days.

4. VPC Networking Setup with Peering
To support the application's network needs, a custom VPC is required. The VPC needs two public subnets and one private subnet to host different tiers of the application. Additionally, the company has resources in another region, so VPC peering is required to establish a connection between your new VPC and a default VPC in another AWS region.
Create a VPC with the CIDR block 10.10.10.0/24.
Set up two public subnets and one private subnet within the VPC.
Attach an Internet Gateway to allow the public subnets to communicate with the internet.
Set up a NAT Gateway in one of the public subnets to allow private subnets to access the internet.
Establish a VPC peering connection with a default VPC in a different region. Update routing tables accordingly to ensure communication between the VPCs.
Deliverables:
Create a VPC with three subnets: two public and one private.
Attach an Internet Gateway for public internet access.
Set up a NAT Gateway for private subnet internet access.
