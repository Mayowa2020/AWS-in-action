# Creating subnets within an Amazon Virtual Private Cloud (VPC)

1. **Sign in to AWS Console:**
   Go to the AWS Management Console at <https://console.aws.amazon.com/> and sign in using your AWS account credentials.

2. **Navigate to the VPC Dashboard:**
   Once logged in, type "VPC" in the search bar at the top of the console and select "VPC" from the search results to open the VPC Dashboard.

3. **Create a VPC:**
   If you don't have a VPC already, follow the steps outlined earlier to create a VPC. Note down the VPC ID as you'll need it for creating subnets.

4. **Create Public Subnet:**

   - In the VPC Dashboard, click on "Subnets" in the left-hand navigation pane.
   - Click on "Create subnet."
   - Enter a name tag for the subnet as PublicSubnet.
   - Select the VPC you created earlier.
   - Choose an availability zone from the dropdown menu: us-east-1a.
   - Specify an IPv4 CIDR block for the subnet as 10.1.1.0/24.
   - Click on "Create" to create the public subnet.

5. **Create Private Subnet:**

   - Follow the same steps as above to create a private subnet within the same VPC.
   - Enter a name tag for the subnet as PrivateSubnet.
   - Select the same VPC as before.
   - Choose a different availability zone from the dropdown menu.
   - Specify an IPv4 CIDR block for the subnet as 10.1.2.0/24
   - Click on "Create" to create the private subnet.

6. **My Subnet Details:**

   - VPC

     - Name: darey.io-vpc-demo
     - IPv4 CIDR Block: 10.1.0.0/16

   - Public Subnet: darey.io-demo-public
     - Subnet ID:
     - Availability Zone: us-east-1a
     - CIDR Block: 10.0.1.0/24
   - Private Subnet: darey.io-demo-private
     - Subnet ID
     - Availability Zone: us-east-1a
     - CIDR Block: 10.0.2.0/24

7. **Role of Subnets in Network Segmentation**:

   - Subnets allow you to segment your VPC into smaller address spaces.
   - Public subnets typically host resources like load balancers, bastion hosts, and publicly accessible services.
   - Private subnets are used for backend servers, databases, and other internal services.
   - Network ACLs and security groups control traffic between subnets.

8. **Observations and Insights**:
   Subnets play a crucial role in network segmentation within a VPC. They allow you to organize and isolate resources based on their security requirements.
   Public subnets are typically used for resources that need direct internet access (e.g., web servers), while private subnets are used for resources that should not be directly accessible from the internet (e.g., databases).
   Availability Zones provide redundancy and fault tolerance. Distributing subnets across multiple Availability Zones ensures high availability

Remember to associate each subnet with an appropriate route table to control outbound traffic. - Pay attention to the CIDR block size to ensure sufficient IP addresses for your resources. - Consider high availability by distributing subnets across multiple AZs. - Test connectivity between subnets and verify routing configurations.

Subnets play a crucial role in organizing your network resources within a VPC. Properly designed subnets enhance security, scalability, and manageability.

## References

https://www.youtube.com/watch?v=ydxEeVAqVdo&list=RDCMUC7p4oXcPbgk_yTSHK7QlkSg&start_radio=1
