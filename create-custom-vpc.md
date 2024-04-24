# Creating a VPC on the AWS Management Console

## Purpose

In this mini project, you will learn how to create a Virtual Private Cloud (VPC) on AWS using the AWS Management Console. The project will guide you through the process of defining a VPC and configuring its basic setttings.

## Objectives

1. Create a VPC

- Learn how to create a VPC with a specified Ip address range.

Sure, here's a step-by-step guide to creating a VPC on the AWS Management Console:

1. **Log in to the AWS Management Console:**
   - Open your web browser and go to the AWS Management Console at <https://aws.amazon.com/console/>.
   - Log in using your AWS account credentials.

2. **Navigate to the VPC service:**
   - Once logged in, you'll land on the AWS Management Console dashboard.
   - In the search bar at the top, type "VPC" and select the "VPC" service from the search results. Alternatively, you can find VPC under the "Networking & Content Delivery" section.

3. **Access "Your VPCs" section:**
   - In the VPC dashboard, locate the "Your VPCs" option in the left navigation pane and click on it. This will show you a list of existing VPCs (if any).

4. **Create a new VPC:**
   - To create a new VPC, click on the "Create VPC" button located at the top of the "Your VPCs" page.

5. **Fill in VPC details:**
   - In the "Create VPC" wizard, you'll be prompted to enter details for your new VPC.
   - **VPC name:** Give your VPC a meaningful name to identify it easily.
   - **IPv4 CIDR block:** Enter the IPv4 CIDR block for your VPC. This block defines the range of IP addresses that can be used within your VPC. For example, you can use `10.0.0.0/16` for a large VPC or `10.0.0.0/24` for a smaller one.
   - **IPv6 CIDR block:** Optionally, you can also specify an IPv6 CIDR block if you want to enable IPv6 for your VPC.
   - **Tenancy:** Choose whether the instances launched in this VPC should be dedicated or shared. For most cases, you can leave this as the default "Default" tenancy.
   - Click on the "Create" button to create your VPC.

Once the VPC is created, you'll see it listed under "Your VPCs" in the VPC dashboard. You can then proceed to configure additional settings like subnets, route tables, security groups, and network ACLs as per your requirements.

## Details for my VPC

- VPC Name: darey.io-vpc-demo
- IPv4 CIDR block: 10.0.0.0/16
- IPv6 CIDR block (not applicable here)
- Tenancy: default
- Any other specific settings or configurations you made during the creation process.

## Observations, Challenges Faced, and Insights Gained

- Observations: Every region has a default VPC. A VPC spans mutiple availabitity zones in a region while a subnet can only span one availability zone. The IP Address range generated from the CIDR block is only for the private IP addresses in the VPC. The Main route table and Main network ACL are automatically created along with a VPC.
- Challenges Faced: Understanding and defining CIDR blocks.
- Insights Gained: Virtual Private Clouds (VPCs) are crucial in AWS for network isolation, security, and control. They allow you to define a virtual network environment that closely resembles a traditional network but with added benefits like scalability and flexibility.

## Importance of VPCs

VPCs provide network isolation, allowing you to create logically isolated sections of the AWS cloud.
They enable you to define your own IP address range, control routing, and set up security groups and network ACLs.
Properly configured VPCs enhance security, scalability, and manageability of your AWS resources.
Remember that VPCs are fundamental building blocks in AWS, and understanding their configuration is crucial for successful cloud infrastructure deployment.
