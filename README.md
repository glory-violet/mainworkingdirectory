# Automated-EC2-MongoDB-Scheduled-Backup-Solution
#### This GitHub repository hosts the Source Code and Documentation for an automated backup solution designed to simplify and enhance MongoDB data backup processes running on Amazon Elastic Compute Cloud (EC2) instances.





## Project - "Overview":
#### • Providing an automated and Efficient Backup Solution that runs automatically on a pre-defined, scheduled time reducing human interventions for backup, and saving time and efforts.

#### • This project aimed to create a comprehensive MongoDB backup solution on an EC2 Instance within the AWS Environment.

#### • It involves several components and steps to ensure a robust system for MongoDB database hosted on an Amazon Web Service (AWS) EC2 Instance.

#### • It covers the setup of AWS resources, the installation of MongoDB, the configuration of an S3 bucket for storing backups, and the automation of the backup process.






## Project - "Problem Statement":
#### Mr. John Williams is an employee at an IT Company, He works on the Cloud Technology in the IT department. 

#### The IT company He is working in has many business divisions and as well as many domains hosted on the cloud. Mr.John has hosted a website on AWS EC2 instance along with MongoDb database. but taking backup manually is time consuming.

#### So Mr. John wants to automate taking database backup continuously without getting bogged down in different backup and failure scenarios in MongoDB database systems, He wants to utilize the time he spends on the backup task to do more productive work.







## Project - "Deliverables":
#### Mr.John wants a solution on the effective Automatic MongoDB Backup Method so that Mr.John will no longer need to spend hours on the MongoDB backup process.






## Project - "Solution":
#### To address Mr. John Doe's requirement of automating MongoDB database backups for his website hosted on an AWS EC2 instance, we can create a comprehensive solution by leveraging a combination of AWS resources and scripting tools:

### AWS Resources:

#### • Amazon Elastic Compute Cloud (EC2) for hosting the Website, MongoDB, and backup scripts.

#### • Amazon Simple Storage Service (S3) for storing MongoDB backups securely.

#### • Amazon Identity and Access Management (IAM) for managing access permissions.

#### • MongoDB for database management.

### Scripting Tools:
#### • Cron jobs for scheduling and automating backup tasks.

#### Following this project solution, Mr. John Doe will have a reliable and automated MongoDB backup system in place, allowing him to focus on more productive tasks while ensuring the safety and availability of his website's data.


............................................................................................................................................................................................................................

# Project Execution _Guide:
#### The Project of Automating MongoDB Backups on EC2 involves using multiple applications and integration methods.

#### This project is devided into "6 Main PARTS" in order to make it easy to understand.

#### "For detailed project guidance and step-by-step execution instructions, please refer to the comprehensive project guide provided below."


## PART-1
## [Creating an AWS Account _Tutorial](https://www.youtube.com/watch?v=SFaSB6vgp8k&t=13s)  
#### About Amazon Web Services:
> AWS (Amazon Web Services) is a comprehensive and widely used cloud computing platform that offers a wide range of scalable and on-demand computing services, including storage, databases, machine learning, and more.

#### Use Cases:
> Creating an AWS account is the initial step because AWS provides the infrastructure and services required for hosting the EC2 instance and S3 bucket, etc.


### - 1.1 - To access the [AWS Sign-Up page](https://portal.aws.amazon.com/billing/signup?nc2=h_ct&src=header_signup&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start/email)








## PART-2
### Setting up AWS IAM Crdentials _Tutorial:
#### About AWS IAM:
> AWS IAM (Identity and Access Management) Credentials are authentication and authorization settings that define who can access AWS resources and what actions they can perform, ensuring secure and controlled access to AWS services and data.

#### Use Cases:
> Setting up IAM credentials is essential to ensure secure access to AWS resources. IAM enables fine-grained control over who can perform actions on resources.

### - 2.1 - Creating an IAM User
### - 2.2 - Creating an IAM Group
### - 2.3 - Creating an Assigning Permisions. e.g. EC2 Full Access, and S3 Full Access.
### - 2.4 - Creating Access Credentials.
### - 2.5 - Loggin in with the IAM User Credentials.





## PART-3
### Launching an EC2-Ubuntu Instance and Establishing SSH Connection _Tutorial:
#### About Amazon Elastic Compute Cloud:
> An EC2 (Elastic Compute Cloud) instance is a virtual server in Amazon Web Services (AWS) that can be configured and used to run applications, perform computing tasks, and host various software systems in a cloud-based environment.

#### Use Cases:
> Launching an EC2 instance is necessary because it provides the virtual computing environment where MongoDB will run.

### - 3.1 - Navigate to EC2 section in the AWS Management Console.
###    - 3.2 - Click on "Launch Instances" 
###    - 3.3 - Define the EC2 Instance Name.
###    - 3.4 - Select the AMI as Ubuntu and the Version is 20.04 LTS.
###    - 3.5 - Select the Instance type as Free-Tier.
###    - 3.6 - Create the Key-pair.
###    - 3.7 - Create the Security Group.
###    - 3.8 - Click on "Launch Instance"






## PART-4
### Installing MongoDB and its Dependencies on EC2 _Tutorial:
#### About MongoDB:
> MongoDB is a popular NoSQL database management system developed by MongoDB Inc. It stores data in a flexible, JSON-like format and is known for its scalability, performance, and ability to handle unstructured or semi-structured data.

#### Use Cases:
> Installing MongoDB on the EC2 instance is required to set up the database system that stores the application's data.

### - 4.1 - Installing MongoDB




## PART-5
### Creating an S3 bucket and configuring it as the destination for MongoDB backups from EC2 _Tutorial:
#### About Amazon Simple Storage Service:
> Amazon S3 (Simple Storage Service) is a highly scalable and secure object storage service provided by Amazon Web Services (AWS) for storing and retrieving data, often used for backup, data archiving, and serving static assets for websites and applications.

#### Use Case: 
> Creating an S3 bucket serves as the destination for storing MongoDB backups. S3 offers scalable, secure, and durable object storage, making it an ideal choice for backup storage.

### - 5.1 - Creating S3 bucket
### - 5.2 - Creating a "backup" fodler in the S3 bucket.
### - 5.3 - Enabling MongoDB Backup from the EC2 to S3.
### - 5.4 - Testing the backup configuration.





## PART-6
### Automating MongoDB Backup _Tutorial:
