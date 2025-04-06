# wazuh-siem-project


# SIEM Project with Wazuh on AWS EC2

## Overview
This project involves setting up and configuring a Security Information and Event Management (SIEM) system using Wazuh on an Amazon EC2 instance. The project is hosted on Amazon Linux 2 with a t2.micro instance type, ensuring it stays within the AWS Free Tier limits. 

The main goal was to configure Wazuh Manager and test its functionality by logging into the EC2 instance with an incorrect PEM key, which was then logged by Wazuh.

## Steps

### 1. Launching EC2 Instance
- Created a t2.micro EC2 instance on AWS using Amazon Linux 2.
- Configured security groups to allow necessary traffic (e.g., SSH, HTTP, and custom ports for Wazuh).
- Downloaded the necessary PEM key for secure SSH login.
- Successfully set up instance ![Instance Page](screenshots/EC2_Instance_Page.png)

### 2. Installing Wazuh Manager
- Installed Wazuh Manager on the EC2 instance. This was done by following the installation guide provided via https://documentation.wazuh.com/current/installation-guide/wazuh-server/step-by-step.html
- Configured the manager to collect security-related logs, such as login attempts and system activity.
- ![Wazuh Manager Status](screenshots/Wazuh_Manager_Status.png)
- Ensured Wazuh was correctly processing and analyzing logs.

### 3. Testing Configuration
- Attempted logging in with an incorrect PEM key to simulate an unauthorized access attempt.
- ![Intentional Incorrect Login](screenshots/SSH_Wrong_Connection.png)
- The failed login attempt was successfully logged and flagged by Wazuh, confirming the system's functionality.

## Logs and Observations
- Upon attempting to log in with the wrong PEM key, Wazuh captured the event and recorded the failed login attempt in the logs. This demonstrates Wazuh's ability to monitor and alert for potential security incidents.
- ![Login Failure](screenshots/SSH_Alert.png)

## Requirements
- AWS account with access to EC2.
- Wazuh Manager installation on Amazon Linux 2.
