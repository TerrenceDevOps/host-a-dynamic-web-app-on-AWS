# Hosting a Dynamic Website on AWS

This repository contains the resources and scripts used to deploy a dynamic website on Amazon Web Services (AWS). The project leverages various AWS services to ensure high availability, scalability, and security for the application.

## Architecture Overview
![Alt text](/3._Host_a_Dynamic_Web_App_on_AWS.png)
The dynamic website is hosted on EC2 instances within a highly available and secure architecture that includes:

1. **Virtual Private Cloud (VPC):** Configured with both public and private subnets across two Availability Zones for fault tolerance and high availability.
2. **Internet Gateway:** Enables communication between instances in the VPC and the internet.
3. **Security Groups:** Act as a virtual firewall to control inbound and outbound traffic.
4. **Public Subnets:** Used for infrastructure components like the NAT Gateway and Application Load Balancer, facilitating external access and load balancing.
5. **Private Subnets:** Web servers (EC2 instances) are placed within private subnets to enhance security.
6. **EC2 Instance Connect Endpoint:** Provides secure SSH access to instances within both public and private subnets.
7. **NAT Gateway:** Allows instances in private Application and Data subnets to access the internet.
8. **EC2 Instances:** Hosts the website and serves application requests.
9. **Application Load Balancer:** Used to distribute incoming web traffic across multiple EC2 instances within an Auto Scaling Group.
10. **Auto Scaling Group:** Automatically adjusts the number of EC2 instances based on traffic, ensuring scalability and resilience.
11. **AWS Certificate Manager:** Secures application communications with SSL/TLS certificates.
12. **Amazon Route 53:** Manages domain name registration and DNS records for the website.
13. **Amazon Simple Notification Service (SNS):** Sends alerts related to Auto Scaling Group activities.
14. **Amazon S3:** Stores application code and static assets efficiently.

## Deployment Steps

### 1. Setting Up the Environment
- Configure a Virtual Private Cloud (VPC) with public and private subnets.
- Deploy an Internet Gateway to enable external connectivity.
- Set up Security Groups for access control.
- Implement EC2 Instance Connect Endpoint for secure connections.

### 2. Deploying the Application
- Launch EC2 instances within the private subnet.
- Install and configure required software (Apache, Nginx, PHP, or other backend services).
- Store application code in an S3 bucket for efficient deployment.
- Configure an Auto Scaling Group and Application Load Balancer to manage traffic.
- Secure the application using AWS Certificate Manager.

### 3. Domain Setup
- Register a domain name via Route 53.
- Configure DNS records to point to the Application Load Balancer.

### 4. Monitoring and Notifications
- Set up Amazon SNS to send alerts about scaling activities.
- Implement CloudWatch monitoring for performance and security insights.

## Lessons Learned

During this project, I encountered challenges setting up Route 53 for DNS management. However, after troubleshooting, I successfully configured the DNS records, ensuring proper domain resolution. This experience deepened my understanding of AWS networking, domain name systems, and infrastructure automation.

## How to Use

1. Clone this repository to your local machine.
2. Follow the AWS documentation to create the required resources (VPC, subnets, Internet Gateway, etc.) as outlined in the architecture overview.
3. Use the provided scripts to set up the application on EC2 instances within the VPC.
4. Configure the Auto Scaling Group, Load Balancer, and other services.
5. Access the website through the Load Balancer's DNS name or the configured domain name in Route 53.

## Contributing

If you would like to contribute to this project, please submit a pull request with improvements or additional features.

