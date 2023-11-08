---
title: "How to Install CloudLinux on CentOS 8 with AWS EC2 and Plesk"
author: mdomocos
date: 2023-11-08 09:00:00 +0200
categories: [Linux, Tutorials, Server Management]
tags: [cloudlinux, centos, aws, ec2, plesk, server setup, linux]
math: false
mermaid: false
pin: false
---

Installing CloudLinux on CentOS 8 within an AWS EC2 environment requires careful planning and execution. This guide will walk you through the deployment steps, including setting up security groups and disk configuration. Additionally, we'll cover how to install Plesk on your new system.

## Prerequisites
Before you begin, ensure that you have the following:
- An AWS account
- A basic understanding of AWS services
- Familiarity with SSH and command-line interface (CLI)

## Step 1: Set Up AWS EC2 Instance
1. **Log into your AWS Management Console** and navigate to the EC2 Dashboard.
2. **Launch a new instance** by selecting the "Launch Instance" option.
3. **Choose an AMI** - Select the CentOS 8 Amazon Machine Image (AMI) from the AWS Marketplace.
4. **Select an Instance Type** - Choose an instance type that meets the requirements of CloudLinux and Plesk.
5. **Configure Instance Details** - Set up the network and subnet. Enable auto-assign public IP if required.
6. **Add Storage** - Allocate sufficient disk space. CloudLinux and Plesk recommend at least 40GB.

## Step 2: Configure Security Groups
1. **Create a new security group** for your instance.
2. **Set rules** to allow SSH (port 22), HTTP (port 80), HTTPS (port 443), and any other ports required by specific services you plan to use.

## Step 3: Launch and Connect to Your Instance
1. **Review and launch** the instance.
2. **Connect to your instance** using SSH with your instance's public IP address and the private key associated with your instance.

## Step 4: Convert CentOS to CloudLinux
1. **Purchase a CloudLinux license** from the CloudLinux website.
2. **Install the CloudLinux OS** by running the CloudLinux installation script provided after the purchase.

   ```bash
   wget https://repo.cloudlinux.com/cloudlinux/sources/cln/cldeploy
   sh cldeploy -k <your_activation_key>
   reboot
   ```

## Step 5: Install Plesk
1. Download the Plesk installer script.
   ```bash
   wget https://installer.plesk.com/plesk-installer
   ```

2. Add execution permissions to the script.
   ```bash
   chmod +x plesk-installer
   ```

3. Run the Plesk installer.
   ```bash
   ./plesk-installer
   ```

4. Follow the on-screen instructions to complete the installation. Select the components you wish to install and configure according to your preferences.

## Step 6: Finalize Installation and Setup
1. Access Plesk using your browser by navigating to `https://your_server_ip:8443`.
2. Complete the initial setup by configuring the administrator's contact information and setting up the administrator password.
3. Secure your Plesk panel by obtaining a Let's Encrypt SSL certificate through the Plesk control panel, and follow the prompts to secure your panel.

## Conclusion
You have successfully set up a CloudLinux system on AWS EC2 with Plesk installed. This setup provides you with a robust platform for hosting websites and web applications. Ensure that you configure backups and monitor your system's performance regularly to maintain a healthy and secure server environment.
