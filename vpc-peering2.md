# Guide: Setting Up VPC Peering Connections Between Two Amazon VPCs using AWS Management Console

Amazon Virtual Private Cloud (VPC) peering empowers you to link two Amazon VPCs through an Amazon VPC peering connection, expanding network connectivity and facilitating communication across resources in separate VPCs. This detailed guide navigates through the steps of establishing a VPC peering connection between two Amazon VPCs via the AWS Management Console, with a focus on configuring security groups for secure traffic flow between instances in the peered VPCs.

## Objective

In this mini project, you will gain hands-on experience in establishing a Virtual Private Cloud (VPC) peering connection between two Amazon VPCs using the AWS Management Console. Additionally, you will configure security groups to enable specific traffic flow between instances in the peered VPCs.

**1. Create Two VPCs:**

- Navigate to the AWS Management Console.
- Access the VPC dashboard.
- Create two separate VPCs with non-overlapping CIDR blocks (VPC-A and VPC-B).

**2. Initiate VPC Peering Connection:**

- In the VPC dashboard, navigate to "Peering Connections" under "Virtual Private Cloud."
- Click on "Create Peering Connection."
- Name the peering connection and select VPC-A as the requester and VPC-B as the accepter.
- Click "Create Peering Connection."

**3. Accept VPC Peering Connection:**

- After creating the peering connection, select it from the list in the VPC dashboard.
- Click "Actions" and then "Accept Request" to accept the peering request in VPC-B.

**4. Configure Security Groups:**

- Go to the EC2 dashboard and navigate to "Security Groups."
- Create new security groups or modify existing ones for instances in VPC-A and VPC-B.
- Configure security group rules to allow specific traffic (e.g., HTTP, SSH) from the CIDR blocks of the peered VPCs.
- Apply these security groups to the relevant instances in each VPC.

**5. Verify Connectivity:**

- Launch instances in both VPC-A and VPC-B.
- Ensure that the security group rules allow the necessary traffic flow between instances in the peered VPCs.
- Use tools like ping, traceroute, or SSH/RDP to verify connectivity between instances in VPC-A and VPC-B based on the configured security group rules.

By completing this mini project, you will have a solid understanding of setting up VPC peering connections and configuring security groups to enable secure and specific communication between instances in different VPCs within AWS.

### Step 1: Environment Setup

1. Log into your AWS Management Console.
2. Access the VPC dashboard.
3. Create the VPCs:
   - If not created already, establish two distinct VPCs (VPC-A and VPC-B).
   - Note and ensure non-overlapping CIDR blocks for each VPC.

### Step 2: Create VPC Peering Connection

1. In the VPC dashboard, navigate to “Peering Connections” under “Virtual Private Cloud.”
2. Click “Create Peering Connection.”
3. Specify a unique name for the peering connection, choose the requester VPC (VPC-A), and the accepter VPC (VPC-B).
4. Click “Create Peering Connection.”

### Step 3: Accept Peering Connection

1. After creation, select the peering connection from the list.
2. Click “Actions” and then “Accept Request.”

### Step 4: Update Route Tables

1. Access the route table associated with each VPC.
2. Add a route for the peer VPC’s CIDR block pointing to the peering connection.

### Step 5: Configure Security Groups

1. In the EC2 dashboard, navigate to “Security Groups.”
2. Create new or modify existing security groups for instances or subnets in both peered VPCs, allowing traffic from each other’s CIDR blocks based on application needs (permitting all traffic or specific ports/protocols).
3. Apply these updated security groups to relevant instances within each peered VPC.

### Configuration Details

    VCP A
    - CIDR: 10.0.0.0/16
    - Availability zone: us-east-1a
    - Route Table: RT-A

    public-subnet-A
     - CIDR: 10.0.0.0/16

    VCP-B
     - CIDR: 192.168.0.0/16
     - Availability zone: us-east-1a
     - Route Table: RT-B

    public-subnet-B
     - CIDR: 192.168.0.0/17


    EC2A
     - Public IPV4 Address: 3.239.16.187
     - Private IPV4 Address: 10.0.40.136

    EC2B
     - Public IPV4 Address: 34.201.20.162
     - Private IPV4 Address: 192.168.53.17

    name of vpc-peering
     - VPC-A to VPC-B

## Testing Connectivity

1. Launch instances in both peered VPCs.
2. Verify security group rules permit necessary traffic.
3. Test connectivity using ping, traceroute, or SSH/RDP connections as applicable.

## VPC Peering Significance and Security Groups

- VPC peering enables secure communication between instances in different VPCs within AWS, bypassing the public internet.
- Security groups control inbound and outbound traffic, authorizing communication between resources in peered VPCs based on defined rules.

## Insights

- VPC peering connects VPCs within the same or different AWS accounts, utilizing AWS's network backbone for efficient communication.
- Choose the "Requester VPC" and "Accepter VPC" during peering setup, facilitating bidirectional private IP address communication.
- VPC peering options extend to connections within the same account, across different AWS accounts, and between VPCs in various AWS Regions.

## References

- NetworkProGuide: [Create AWS VPC Peering Connection](https://networkproguide.com/create-aws-vpc-peering-connection/)
- YouTube: [VPC Peering Connection Tutorial](https://www.youtube.com/watch?v=an4t2B7qXTY)
- Image Reference: [Maxresdefault](https://i.ytimg.com/vi/an4t2B7qXTY/maxresdefault.jpg)
- <https://docs.aws.amazon.com/vpc/latest/peering/create-vpc-peering-connection.html#same-account-same-region>
- <https://www.youtube.com/watch?v=36qsohuPzMQ>
