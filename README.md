# Node.js-deployment-on-AWS

This repository contains the necessary steps and scripts to deploy a Node.js application on an AWS EC2 instance.

Prerequisites
Before you begin, ensure you have the following:

* An AWS account
* AWS CLI installed and configured
* An EC2 instance running Ubuntu
* Node.js installed on your EC2 instance
* SSH access to your EC2 instance
  Setup:

•Step 1: Launch EC2 Instance
Log in to the AWS Management Console.
Navigate to EC2 Dashboard and click "Launch Instance".
->Select an Amazon Machine Image (AMI). We recommend using Ubuntu.
->Choose an instance type (e.g., t2.micro for free tier).
->Configure the instance details, add storage, and configure security group to allow SSH (port 22).
->Launch the instance and download the key pair.
•Step 2: Connect to EC2 Instance
Use the key pair to SSH into your EC2 instance:

Run this command

ssh -i "your-key-pair.pem" ubuntu@your-ec2-public-dns
Step 3: Install Node.js
Install Node Version Manager (nvm):

Run this command

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc
Install the latest LTS version of Node.js:

Run this command

nvm install --lts
Step 4: Clone the Repository
Clone your Node.js application repository to the EC2 instance:

Run this command

 gitclonegit@github.com:mrmonarch20/Node.js-deployment-on-AWS.git
cd Node.js-deployment-on-AWS
Step 5: Install Dependencies
Install the required Node.js dependencies:

Run this command

npm install
Step 6: Start the Application
Start your Node.js application:

Run this command

npm start
Step 7: Set Up SSH Key for GitHub (if needed)
Generate a new SSH key:

Run this command

ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
Follow the prompts to save the key (default location is fine).

Add the SSH key to the ssh-agent:

Run this command

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
Copy the SSH key to your clipboard:

Run this command

cat ~/.ssh/id_rsa.pub
Add the SSH key to your GitHub account:

Go to GitHub > Settings > SSH and GPG keys > New SSH key.
Paste the key and save.
Additional Resources
For more detailed instructions, refer to the following resources:

AWS EC2 Setup Guide
Deploying Node.js Apps to AWS
