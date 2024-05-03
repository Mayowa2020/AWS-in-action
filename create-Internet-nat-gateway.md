# Creating Internet Gateway and NAT Gateway with Route Table Configuration

## Purpose: In this mini project, you will learn how to create an internet Gateway, a NAT Gateway, and configure route tables for a public subnet and a private subnet within an Amazon VPC using the AWS Management Console

## Objectives

1. **Create an Internet Gateway**

   - Learn how to create an Internet Gateway to allow communication between the VPC and the Internet.

2. **Create a NAT Gateway**

   - Set up a NAT Gateway to enable private subnet
   - instances to initiate outbound traffic to the internet.

3. **Configure Route Tables**

   - Define route tables for both public and private
   - subnets to control traffic flow.


Creating Internet Gateway, NAT Gateway, and Configuring Route Tables:

1. **Create an Internet Gateway:**
   - In the VPC dashboard, click on "Internet Gateways" in the left navigation pane.
   - Click the "Create Internet Gateway" button.
   - Provide a name for your Internet Gateway (e.g., MyIGW) and click "Create."

2. **Attach Internet Gateway to VPC:**
   - Select the newly created Internet Gateway.
   - From the "Actions" dropdown menu, choose "Attach to VPC."
   - Select your VPC from the dropdown list and click "Attach."

3. **Create a NAT Gateway:**
   - Navigate to "NAT Gateways" in the VPC dashboard.
   - Click on "Create NAT Gateway."
   - Choose the subnet for your NAT Gateway (typically a public subnet).
   - Allocate an Elastic IP address or select an existing one.
   - Click "Create NAT Gateway."

4. **Configure Route Tables:**
   - Go to "Route Tables" in the VPC dashboard.
   - You'll see default route tables for your VPC. Click on the route table associated with your private subnet.
   - Edit the route table and add a new route with the destination as "0.0.0.0/0" (for IPv4) or "::/0" (for IPv6) and the target as your NAT Gateway.
   - Save the route table configuration.

5. **Configure Public Subnet Route Table:**
   - Similarly, edit the route table associated with your public subnet.
   - Add a route with the destination "0.0.0.0/0" (for IPv4) or "::/0" (for IPv6) and the target as your Internet Gateway.
   - Save the route table configuration.

6. **Document your configurations:**
   - In your documentation, note down the details of your Internet Gateway, NAT Gateway, and the configuration of route tables for both public and private subnets.

7. **Observations and Insights:**
   - Internet Gateways provide a crucial link between your VPC and the internet, allowing resources in public subnets to communicate with external services.
   - NAT Gateways enable private instances to access the internet while maintaining security by preventing inbound connections.
   - Route tables play a vital role in directing traffic within your VPC, ensuring that it reaches the right destinations.

## References

https://www.youtube.com/watch?v=43tIX7901Gs