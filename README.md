# Automated-EC2-MongoDB-Scheduled-Backup-Solution
#### This GitHub repository hosts the Source Code and Documentation for an automated backup solution designed to simplify and enhance MongoDB data backup processes running on Amazon Elastic Compute Cloud (EC2) instances.


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





## Project - "Overview":
#### • Providing an automated and Efficient Backup Solution that runs automatically on a pre-defined, scheduled time reducing human interventions for backup, and saving time and efforts.

#### • This project aimed to create a comprehensive MongoDB backup solution on an EC2 Instance within the AWS Environment.

#### Here is a diagram providing a high-level overview of the project:
<img src="https://github.com/glory-violet/mainworkingdirectory/assets/137056419/9eab7e1a-08f0-491e-95bb-028ebc558106" width="750" height="500">

#### • It involves several components and steps to ensure a robust system for MongoDB database hosted on an Amazon Web Service (AWS) EC2 Instance.

#### • It covers the setup of AWS resources, the installation of MongoDB, the configuration of an S3 bucket for storing backups, and the automation of the backup process.

............................................................................................................................................................................................................................

# Project Execution _Guide:
#### The Project of Automating MongoDB Backups on EC2 involves using multiple applications and integration methods.

#### This project is devided into "6 Main PARTS" in order to make it easy to understand.

#### "For detailed project guidance and step-by-step execution instructions, please refer to the comprehensive project guide provided below."


## PART-1: [Creating an AWS Account _Tutorial](https://www.youtube.com/watch?v=SFaSB6vgp8k&t=13s)  
#### About Amazon Web Services:
> AWS (Amazon Web Services) is a comprehensive and widely used cloud computing platform that offers a wide range of scalable and on-demand computing services, including storage, databases, machine learning, and more.

#### Use Cases:
> Creating an AWS account is the initial step because AWS provides the infrastructure and services required for hosting the EC2 instance and S3 bucket, etc.


### - 1.1 - To access the [AWS Sign-Up page](https://portal.aws.amazon.com/billing/signup?nc2=h_ct&src=header_signup&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start/email)








## PART-2 [Setting up AWS IAM Crdentials _Tutorial:]
#### About AWS IAM:
> AWS IAM (Identity and Access Management) Credentials are authentication and authorization settings that define who can access AWS resources and what actions they can perform, ensuring secure and controlled access to AWS services and data.
To know more, visit [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

#### Use Cases:
> Setting up IAM credentials is essential to ensure secure access to AWS resources. IAM enables fine-grained control over who can perform actions on resources.

### 2.1 - Creating an AWS IAM User Credentials:
- Create an IAM User
- Create an IAM Group
2.3 - Creating an Assigning Permisions. e.g. EC2 Full Access, and S3 Full Access.
- Creating Access Credentials.
- Loggin in with the IAM User Credentials.

### 2.2 - Loggin in with the IAM User Credentials:




## PART-3 [Launching an EC2-Ubuntu Instance and Establishing SSH Connection _Tutorial:]
#### About Amazon Elastic Compute Cloud:
> An EC2 (Elastic Compute Cloud) instance is a virtual server in Amazon Web Services (AWS) that can be configured and used to run applications, perform computing tasks, and host various software systems in a cloud-based environment. To know more, visit [AWS EC2 Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)

#### Use Cases:
> Launching an EC2 instance is necessary because it provides the virtual computing environment where MongoDB will run.

### - 3.1 - Navigate to EC2 section in the AWS Management Console.
- Click on "Launch Instances" 
- Define the EC2 Instance Name.
- Select the AMI as Ubuntu and the Version is 20.04 LTS.
- Select the Instance type as t2.micro (Free-Tier Eligible).
- Create the Key-pair.
- Create the Security Group.
    - Allow SSH Connection Port: 22
- Click on "Launch Instance"

### 3.2 - SSH onto the EC2 Instance using Git-BASH:

- [Download Git-BASH](https://git-scm.com/downloads)
- Open the Git-BASH Terminal 
- Navigate to the location of you Key-Pair.pem file.
    - Example: cd downloads or cd desktop
- Change the Key-pair.pem file permissions.
```bash
chmod 400 "Key-pair.pem"
```
- Once the EC2 Instance is launched successfully, click on that instance ID.
- Click on "Connect"
- Select "SSH Client" option
- Copy the SSH Code that Amazon provides.
- Enter this code in Git-BASH to establish a SSH connection onto the EC2.
Below is the "Sample SSH Code"
```bash
ssh -i "MongoDB-key.pem" ubuntu@ec2-44-201-89-38.compute-1.amazonaws.com
```
- Type "Yes" for the confirmation.
- Now you will be successfully connected to the EC2-Ubuntu Instance.



## PART-4 Installing MongoDB and its Dependencies on EC2 _Tutorial:
#### About MongoDB:
> MongoDB is a popular NoSQL database management system developed by MongoDB Inc. It stores data in a flexible, JSON-like format and is known for its scalability, performance, and ability to handle unstructured or semi-structured data.
To Know more, visit [MongoDB Official Documentation](https://www.mongodb.com/docs/)

#### Use Cases:
> Installing MongoDB on the EC2 instance is required to set up the database system that stores the application's data.

#### Add all the below commands one after the other in sequence to start installing required packages for MongoDB on EC2-Ubuntu home directory:

### 4.1 MongoDB repository and associated GPG key Configuration:

```bash
sudo apt-get update
```

```bash
sudo apt-get install gnupg
```

```bash
wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
```

```bash
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
```

```bash
sudo apt-get upgrade
```

### 4.2 Installing MongoDB:
```bash
sudo apt-get install -y mongodb-org
```

#### Copy all the below commands at once and paste it in the EC2 terminal:
```bash
echo "mongodb-org hold" | sudo dpkg --set-selections
echo "mongodb-org-database hold" | sudo dpkg --set-selections
echo "mongodb-org-server hold" | sudo dpkg --set-selections
echo "mongodb-org-shell hold" | sudo dpkg --set-selections
echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
echo "mongodb-org-tools hold" | sudo dpkg --set-selections
```

#### Start the MongoDB:
```bash
sudo systemctl start mongod
```

#### If you get any ERROR!!!, run the below command, if not you can skip the command:
```bash
sudo systemctl daemon-reload
```

#### To check the status of MongoDB:
```bash
sudo systemctl status mongod
```
#### If it has been installed successfully, you will see the MongoDB status as "Active Running"
<img src="https://github.com/glory-violet/mainworkingdirectory/assets/137056419/6f6d4002-551e-43c0-8676-dee0bcde2b85" width="650" height="150">


#### CTRL + C to exit out of the MongoDB Status.

#### Run the below command if there is any trouble with the MongoDB (Optional Commands):
```bash
sudo systemctl enable mongod
```

```bash
sudo systemctl restart mongod
```

### 4.3 Install the MongoDB Shell:
> Installing the MongoDB shell to interact with MongoDB databases using a command-line interface.

> MongoDB Shell will allows us to query, manipulate, and manage data directly from the terminal.

#### The below command will enable MongoDB Shell to interact with MongoDB Database:
```bash
mongosh
```
#### To exit press "CTRL + C".

### 4.4 To Create a MongoDB Table and Insert Data: 
#### To see the Database Tables available in the MongoDB:
```bash
mongo 
show dbs
```


To create a new DB named "Sales":
```bash
use Sales
```

To see the DBS available in MongoDB:
```bash
show dbs
```
#### Note: That it is not showing the Sales DB Table created in the list.

#### Insert data in to the "Sales" DB:
```bash
db.createCollection("myCollection")
db.myCollection.insert({ name: "Sample Document" })
```


To see the DBS available in MongoDB again:
```bash
show dbs
```
#### Now you will be able to see Sales DB.
#### To exit the MongoDB Shell press "CTRL + C"







## PART-5 Creating an S3 bucket and configuring it as the destination for MongoDB backups from EC2 _Tutorial:
#### About Amazon Simple Storage Service:
> Amazon S3 (Simple Storage Service) is a highly scalable and secure object storage service provided by Amazon Web Services (AWS) for storing and retrieving data, often used for backup, data archiving, and serving static assets for websites and applications. To know more, visit [Amazon S3 Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)

#### Use Case: 
> Creating an S3 bucket serves as the destination for storing MongoDB backups. S3 offers scalable, secure, and durable object storage, making it an ideal choice for backup storage.

### - 5.1 - Creating S3 bucket:
- Navigate to the S3 section in AWS Management Console.
- Click on "Ceate bucket"
- Define S3 bucket name. e.g Mongodb-bucket
- Scroll all the way down and click on "Create bucket"
- Once the bucket is created successfully.
- Click on the bucket name.
- Click on "Create folder" option.
- Create a folder named backup. e.g. "backup"
- Scroll down and click on "Create folder"

#### Now you will be having a S3 Bucket with the Name: MongoDB-Bucket, and a folder within that bucket which named "backup" (All in lower case).

### - 5.2 - Enabling MongoDB Backup from the EC2 to S3.
> In EC2 terminal create a new file with the .sh extension as shown in the example below:
e.g. "task.sh" or "example.sh"
- Command to create a new file on EC2 /home/ubuntu/:
```bash
sudo nano task.sh
```
> The above code will create a file and enables it to be edited:
- Once the task.sh file is editable copy and paste the entire script from below into the task.sh file:
```shell
#!/bin/sh

# S3 bucket name
BUCKET=mongosb-s3-bucket-30.09/backup/ 
BACKUPBUCKET=mongosb-s3-bucket-30.09/backup/

# Linux user account
USER=ubuntu

# Backup directory
DEST=/home/$USER/backup/dump

# Dump z2p & poststodos
mongodump --db sales --out $DEST

# File name
TIME=`/bin/date --date='+5 hour 30 minutes' '+%d-%m-%Y-%I-%M-%S-%p'`

# Tar file of backup directory
TAR=$DEST/../$TIME.tar

# Create tar of backup directory
/bin/tar cvf $TAR -C $DEST .

# Upload tar to s3
/usr/bin/aws s3 cp $TAR s3://$BUCKET
#/usr/bin/aws s3 cp $TAR s3://$BACKUPBUCKET

# Remove tar file locally
/bin/rm -f $TAR

# Remove backup directory
/bin/rm -rf $DEST
```

- To save and exit the file:
```bash
CTRL + o + ENTER, CTRL + X
```

### 5.3 Create files and directories:
> The directory structure and the empty file are being created to establish a designated location for storing backups and data files in a specified directory
```bash 
mkdir -p /home/ubuntu/backup/dump/
```
```bash
touch /home/ubuntu/backup/dump/myfile.txt
```

### 5.4 Installing the AWS CLI:
```bash
sudo apt install awscli
```

> Once the AWS CLI is installed, type the below code to start configure it with the AWS Access Credentials:
```bash
aws configure
```
> Below are the sample of details you need to enter:

```bash
COPY AND PASTE THE ACCESS KEY ID:  "Copy and paste the AWS Access Key ID"
COPY AND PASTE THE SECRET ACCESS KEY ID: "Copy and paste the AWS Aecret Access Key ID"
ENTER THE DEFAULT REGION NAME: "e.g. us-east.1"
DEFAULT OUTPUT FORMAT: "JSON"
```

- To see if the configure is done properly enter the command below to call s3:
```bash
aws s3 ls
```
> If the command above is giving you the list of AWS S3 buckets than the AWS Access Key configuration is successfull.

### - 5.5 - Testing the backup configuration.
- Run the task.sh file in order to check the backup connection with S3.
```bash
bash task.sh
```

> After executing the above command check the S3 bucket and you can find a backup file with execution date and time.

- Run the command "bash task.sh" again in order to see the changed time stamp of the backup files:
bash task.sh




## PART-6 Automating MongoDB Backup _Tutorial:
