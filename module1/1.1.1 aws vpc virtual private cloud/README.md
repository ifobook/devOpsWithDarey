# AWS VPC - Virtual Private Cloud

# Network Mastery with AWS VPC mini project
In this session, we'll explore the core concepts of Amazon Weeb Services (AWS), focusing specifically on Virtual Private Cloud (VPCs). Our objective is to understand the fundanmental components of VPC infrastructure, including subnets, gateways, and routing tables. Through practical demostrations and interactive exercises, we will navigate the AWS management console to deploy and manage these critical components effectively.

Before we proceed with seeting up VPCss, it's essential to ensure a solid understanding of cloud networking basics.

## Project Goals:
- Understand the fundamentals of Virtual Private Cloud (VPC)and its components.
- Gain hands-on experience in setting up and configuring VPC, subnets, internet gateway, NAT gateway, and VPC peering connections.
- Learn how to enable internet connectivity security within a VPC.
- Implement outbound internet access through the NAT gateway.
- Establish direct communication between VPCs using VPC peering.

## Learning Outcomes:
- Acquired knowledge about VPC and its essential components, such aas subnets, gateways, and route tables.
- Developed skills in creating and configuring VPC resources using AWS Management Console.
- Learned how to set up routing tables to enable internet connectivity and outbound internet access securely.
- Gained understanding of VPC peering and its significance in connecting muiltiple VPCs within the same or different regions.

## What is VPC, Subnets, Internet Gateway, NAT Gateway?
You can imagine you're building a virtual space for the company GatoGrowFast.com's so that the computers can communicate securely. That's what VPC, or Virtual Private Cloud, is all about. It's like creating a private room in the cloud just for GatoGrowFast.com's use.

**Here's an example:** Think of GatoGrowFast.com's office building. Inside, there are different departments like HR, Finance, and IT. Each department has its own area with specific access rules. Similarly, in a VPC, GatoGrowFast.com can create different sections, called subnets, for different parts of the business.

Now, let's say GatoGrowFast.com wants to connect the flow of data in and out of the building. In a VPC, GatoGrowFast.com has something similar called an internet gateway. It lets their VPC communicate with the internet securely.

NAT (Network Address Translation) Getway as a secret agent between GatoGrowFast.com's computers and the internet. When a computer inside their virtual office wants to talk to the internet, the NAT Gateway steps in. It translates the computer's message and sends it out, but it hides who sent it. It's like sending s letter without your return address. This way, the internet only sees the NAT Gateway's address, keeping GatoGrowFast.com's computers safe and anonymous online.

**Note:** A router is a device that directs data packets between computer networks. Think of it ad a traffic cop for internet. When data is sent from one device to another access a network, it's broken down into smaller packets need to find their way to the correct destination, and that's where the router comes in.

Imagine you're sending a letter to a friend across the country. You drop it in a mailbox, and it's picked up by a postal worker. The postal worker knows which roads to take and which sorting centers to pass through to ensure your letter reaches its destination. Similarly, a router knows how to send data packets from your device to the right destination on the internet. Routers use router tables, which are like maps of the internet, to determine the best path for data packets to take. They analyze information in the packets, such as destination IP addresses, to make these decisions. Once the packets reach their destination, the router ensures they're delivered to the correct device.

## What is an IP Address?
An IP address is like a phone number for your computer. It's unique set of numbers that helps computers find and talk to each other on a network, like the internet.
There are two main types of IP addresses: public IP addresses and private IP addresses. However, each type has different versions, with IPv4 and IPv6 being the most common.
**Public IP Address:** This is like your home address. It's unique and helps other computers on the internet find yours. Just like how people send letters to your house using your address, data packets are sent to your computer using its public IP address.
- A public IP address is globally unique, and is assigned by your Internet Service Provider (ISP).
- It allows your computer to communicate with other devices on the internet.
- Public IP addresses can be static (fixed) or dynamic (changing over time). Periodically, often each time a device reconnects to the internet, while static IPs remain constant. Static IPs are typically used for servers or devices that need a consistent address, while dynamic IPs are common for regular home users.

**Private IP Address:** Think of this like an internet extension number in a big office building. It's used for communication within a specific network, like your home Wi-Fi network or an office network. Devices within the same network can talk to each other using their private IP addresses, but these addresses aren't visible to the outside world.
- Private IP addresses are typically assigned by a router or a DHCP (Dynamic Host Configuration Protocol) server within a local network.
- Devices within the same private network communicate with each other using their private IP addresses.
- These addresses are not routable on the internet, meaning they can't be accessed directly from outside the local network.
- It is not globally unique and can be reused in different private networks without conflict.

IPv4 Address:
- IPv4 (Internet Protocol version 4) addresses are the most common type of IP addresses used today.
- They are 32-bit numbers, typically represented in four sets of decimal numbers separated by periods (e.g.192.168.01).
- IPv4 addresses are divided into five classes: A,B,C,D, and E, with Class A, B, and C being used for addressing hosts on networks.
- Each octet in an IPv4 address can have a value between 0 and 255. This is because each octet is made up off eigth bits, and the maximum value that can be represented with eight bits is 255 (11111111 in binary).

IPv6 Address:
- IPv6 (Internet Protocol version 6) addresses are the next generation of IP addresses, designed to replace IPv4 due to the exhaustion of available IPv4 addresses.
- They are 128-bit numbers, typically represented in eight groups of four hexadecimal digits separated by colons (e.g. 2001:0db8:85a3:0000:0000:8a2e:0370:7334).
- IPv6 addresses provide a significantly larger address space compared to IPv4, allowing for a virtually unlimited number of unique addresses.

## What is CIDR?
CIDR (Classless Inter-Domain Routing) CIDR, or Classless Inter-Domain Routing, makes it easier to talk about of IP addresses on the internet. instead of naming each address one by one, CIDR uses a simple shortcut. It's like saying "All the houses on Main Street" instead of listing each house seperately.
For example, let's say you have the IP address 192.168.10/24. The "/24" part tells us that we are talking about all the houses on that street from 192.168.1.0 to 192.168.1.255
So, CIDR helps us manage and organize IP addresses on the internet on the internet in a way that's easy to understand and work with. It's like having a shorthand for talking about big groups of addresses.
Determining the number of available IP addresses in a CIDR block to determine the number of available IP addresses in a CIDR block, you calculate it using the formula:
```
2^(32 - CIDR notation)- 2
```
The "-2" is for excluding the network address and the broadcast address.
** Example:**
Let's say we have a CIDR block of "192.168.1.0/24".
Using the formula, we calculate:
```
2^(32 - 24) - 2 
= 2^8 - 2 
= 256 - 2 
= 254
```
## What is a gateway?
Gateways are like doorways between different networks. They help data travel between your local network and other networks, like the internet. Just like a gate lets you go from your backyard to the neighborhood park, a gateway lets your data go from your computer to the internet and block again. It's like the traffic cop of the internet, directing your data where it needs to go.
For example - Imagine you live in a city with different neighborhoods, each with its own set of houses. You're in one neighborhood, lets call it A, and you want to visit a friend who lives in a different neighborhood B. To get from you neighborhood to your friend's neighborhood, you need to go through a gateway-a special gate that connects the two neighborhoods. This gateway acts as a bridge between the two areas, allowing people and things to pass back and forth.
So, when you leave your house in Neighborhood A, you walk to the gateway, pass through it, and then find your friend's house in Neighborhood B. The gateway helps you navigate from one neighborhood to another, just like how a gateway helps data travel between different networks.

## What is a Route Table?
A route table is like a map that helps data find its way around a network. just like a map shows you the best routes to get from one place to another, a route table tells devices on a network how to send data packets to their destinations.
In simpler terms, a route table lists different destinations and the paths (or "routes") to reach them. When a device receives data that it needs to send somewhere, it consults the route table to figure out where to send it.
For example, if your computer wants to send data to a website, it looks at its route table to find out which gateway to use to reach the internet. The route table might say, "To reach the internet, send data to the router." Then, the router knows how to forward the data to the next stop on its journey, eventually reaching its destination.
Think of route table as the navigation system for data on a network, helping it find the fastest and most efficient paths to where it needs to go.

## Connection between Gateway and Route table
Gateways:
- Gateways are devices (like routers or firewalls) that serve as entry and exit points between different networks.
- They connect networks with different IP address ranges, such as your local network and the internet.
- Gateways receive incoming data packets and determine where to send them next based on routing information.

Route Tables:
- Route tables are tables maintained by networking devices (like routes or switches) that contain information about how to route data packets to their destinations.
- Each entry in a route table specifies a destination network and the next hop (gateway) to reach that network.
- Devices consult the route table to determine the best path for forwarding data packets based on their destination IP addresses.

Connection:
- When a device (like a computer or server) wants to send data to a destination outside of its local network, it checks its route table.
- The route table provides the information needed to determine the next hop (gateway) for reaching the destination network.
- The device then forwards the data packet to the specified gateway, which continues the process until the packet reaches its final destination.
In summary, gateways and route tables work together to facilitate the routing of network traffic between different networks. Gateways serve as the entry and exit points between networks, while route tables provide the necessary routing information to determine how data packets should be forwarded to their destinations.

Now let's come to the practical part,
## Steps -
1. Setting Up a Virtual Private Cloud.
2. Configuring Subnets within the VPC
3. Creating Internet Gateway and attaching it to PVC
4. Enabling Internet Connectivity with the internet Gateway by setting up Routing tables
5. Enabling Outbound Internet Access through NAT Gateway
6. Establishing VPC peering Connections.

Let's come to the first one which involves Setting Up a Virtual Private Cloud (VPC)
1. Navigate to the search bar
Enter "VPC" upon locating the relavant result, proceed to click on it, directing you to the Virtual Private Cloud (VPC)page.
![image](assets/image1.png)

2. Please navigate to the "Create VPC" option and click on it.
![image](assets/image2.png)
3. PLease select "VPC only" option, specify the IPv4 CIDR block, and proceed clicking on the "Create VPC" button.
![image](assets/image3.png)

VPC block created successfully
![image](assets/image4.png)
You are done with the part 1 now, let's move to part 2 which is Configuring Subnets within the VPC.

## Part -2
1. Navigate to the "Subnets" option located on the left sidebar
(a)Upon clicking, you will be directed to the "Subnets" page
(b) From there, proceed to click on the "Create subnet" button.
![image](assets/image5.png)
2. PLease select the ID of the VPC that you created in previous step (Part 1)
![image](assets/image6.png)
3. Now, enter the subnet name, and specify the IPv4 CIDR for the subnet
(a) Choose the availability zone
(b) And specify the IPv4 CIDR for the subnet.
(c) To create another subnet, click on the "Add subnet" button
![image](assets/image7.png)
(d) Repeat the same steps for the second subnet
(e) ensuring to specify the subnet name, choose the availability zone and provide the IPv4 CIDR.
(f) Once completed, click on the "Create" button to create the subnet.
To maintain consistency with our intention of creating both a public and private subnet, ensure that the naming convention reflects this distinction appropriately.
![image](assets/image8.png)

Here you'll see your subnets being created
![image](assets/image9.png)
With the creation of subnets, the second part of the task is now completed. Let's proceed to the next part, which involves the creation of an Internet Gateway and attaching it to VPC.

## Part 3
1. Navigate to the "Internet Gateway" option on the left sidebar.
(a) Upon clicking, you will be directed to the Internet Gateway page.
(b) From there, proceed to click on the "Create Internet Gateway" button
![image](assets/image5.png)
2. Specify the name of the Internet Gateway
(a) proceed by clicking on the "Create Internet Gateway" button
![image](assets/image10.png)
Now your Internet gateway is being successfully created.
![image](assets/image11.png)
Now, you will notice that it is currently detached, indicating that it is not associate with any VPC you have previously created.
![image](assets/image12.png)
![image](assets/image13.png)
Now, attach it to VPC
![image](assets/image14.png)
![image](assets/image15.png)
Now, let's come to the next part which is Enabling Internet Connectivity with the Internet Gateway by setting up Routing table

## Part 4
1. Proceed to the "Route Tables" option located on the left sidebar.
(a) Once there, click on the "Create route table" button.
![image](assets/image16.png)
2. Enter the name of the route table and select the VPC you previously create.
(a) Finally, click on the "Create route table" button to proceed.
![image](assets/image17.png)
(b) Next, click on "Subnet associations" followed by "Edit subnet association" to associate the subnet with this route table, We'll associate the public subnet with this route table.
![image](assets/image18.png)
3. Choose the public subnet and click on save association.
![image](assets/image19.png)

4. Navigate to "Routes" and then click on 'Edit route"
![image](assets/image20.png)
5. Click on add route
![image](assets/image21.png)
6. Select "Destination" as "0.0.0.0/0" indicating that every IPv4 address can access this subnet.
7. In the "Target" field, choose "Internet Gateway" and then select the Internet Gateway you created. Finally, save the changes.
![image](assets/image22.png)
The route table has now been configured to route traffic to the internet Gateway,allowing connectivity to the Internet. Since only the subnet named "my-public-subnet-1" is associated with this route table, only resources within that subnet can access the internet.
![image](assets/image23.png)
Now, let's come to the next part which is Enabling Outbound Internet Access through NAT Gateway, (by attaching NAT Gateway to the subnet and attaching the route table)

## Part 5
1. Navigate to the "NAT Gateways" section, then click on "Create NAT Gateway"
![image](assets/image24.png)
2. Then mention the name of the NAT Gateway
![image](assets/image25.png)
3. Now, choose the Private subnet
4. Now, select the connectivity type as Private.

5. Then click on Create NAT Gateway
![image](assets/image26.png)
Your NAT Gateway is being created successfully.
![image](assets/image27.png)
6. Select your NAT Gateway
7. Then navigate to the "Details" tab.
8. From there, locate the subnet ID and click on it.
![image](assets/image28.png)
9. In the subnet page, navigate to the "Route Table" section.
10.  Then click on the "route table ID" -in our case- 1"rtb-0c7a305f74ca510d2"
![image](assets/image29.png)
11.  Proceed to the"Routes" section then click on "Edit route"
![image](assets/image30.png)
12.  Then click on "Add routes"
![image](assets/image32.png)

(a) Select "Destination" as "0.0.0.0/0"
(b) In the "Target" field, choose "NAT Gateway"
(c) Then select the NAT Gateway you created
(d) Finally, save the changes.
![image](assets/image31.png)
Now, 13. On the subnet asscociation section, click on edit subnet association.
![image](assets/image33.png)
(a) Choose the private subnet and click on "Save association"
![image](assets/image34.png)
Now, the subnet has been successfully attached with the route table.
![image](assets/image35.png)


## Difference between Internet Gateway and NAT Gateway.
## Internet Gateway:
Think of it like a door to the internet for your subnet. When you attach an Internet Gateway to a subnet, it allows the resources in that subnet (like EC2 instances) to reach out to the internet and also allows internet traffic to reach those resources. It's like having a door both to enter and exit the subnet

## NAT Gateway:
Imagine it as a one-way street sign for your subnet's traffic. When you attach a NAT Gatway to a subnet, it lets the resource in that subnet (like EC2 instances) access the internet, but it doesn't allow incoming traffic from the  internet to reach those resources. It's like the resources can go out to the internet, but the internet traffic can't directly come in.
Now, let's proceed further and come to our next part that involves Establishing VPC Peering Connections. For this let’s first understand some terms-

**Note:** An EC2 instance is a virtual server in AWS that you can use to run applications. It offers flexible computing power and can be easily scaled up or down. EC2 instances are widely used for hosting websites, running software, and processing data in the cloud.

## What is VPC Peering?

VPC peering is like connecting two virtual offices in the cloud so they can talk to each other directly. Just imagine two neighboring offices sharing files and chatting without going through a middleman.

- By default, EC2 instances in different VPCs cannot communicate with each other.
- To enable communication between EC2 instances in different VPCs, you can set up VPC peering, VPN connections, or AWS Direct Connect.
- VPC peering establishes a direct network connection between the VPCs, allowing EC2 instances in one VPC to communicate with EC2 instances in the other VPC.

## Why do we need VPC Peering?

We need VPC peering when we want different parts of our cloud network(s) to work together smoothly. Maybe you have one VPC for your development team and another for your marketing team, and you want them to share data securely. That’s where VPC peering comes in handy—it lets these VPCs communicate directly, making things easier for everyone.

Additionally, there are some key points that you should be aware of:

- Two VPCs cannot connect to each other. You need to set up VPC peering or use a VPN or Direct Connect to establish connectivity between VPCs.
- Subnets within the same VPC can communicate with each other by default. AWS sets up route tables to allow communication within the same VPC.
- EC2 instances in the same subnet can communicate with each other by default, assuming they have proper security group rules allowing the desired traffic.
- EC2 instances in different subnets within the same VPC can also communicate with each other by default, as long as their associated route tables are configured to allow traffic between subnets.
Now come to the practical part

## Part 6
1. Let's begin by creating two VPC in the same region. Alternatively, you may choose a different region if needed.
![image](assets/image36.png)
![image](assets/image37.png)
2. Navigate to the "Peering Connectivity" option on the left sidebar.
(a) Upon clicking, you'll be directed to the VPC peering page.
(b) From there, proceed to click on the "Create Peering Connection" button
![image](assets/image38.png)
3. Now, provide a name for the VPC peering connection.
(a) select the requester VPC
(b) Choose the account "My account" since the VPCs  are in our AWS account\
(c) Ensure to use the same region, "This Region (ap-southeast-1)," as the VPCs were created in the same region 
(d) Next, select the accepter VPC
(e) proceed by clicking on the "Create Peering Connection" button.
![image](assets/imaage39.png)

Then you'll see this
![image](assets/image40.png)
4. In the Peering Connection page, locate the 'Actions" option on the right side
(a) Click on it, then select "Accept Request."
![image](assets/image41.png)
(b) Click on Accept request
![image](assets/image42.png)
5. Choose the route table.
(a) then navigate to the "Routes" section.
(b) Click on "Edit route"
![image](assets/image43.png)
(c) Click on add me
![image](assets/image44.png)
6. Go to the VPC page
(a) select the requester VPC
(b) In the details tab, you'll find the IPv4 CIDR, (in this case - 192.168.0.0/16)
(c) Copy this CIDR and paste it in the "Destination" field when adding a route
![image](assets/image45.png)
(d) In the larger, choose VPC peering and then choose the peering connection you have created. Click on the save chnages
7. Now, copy the IPv4 CIDR of the accepter VPC (in this case - 172.16.0.0/16)
![image](assets/image46.png)
8. Now, click on Main route table ID of the requester VPC.
![image](assets/image47.png)
9. Choose the route table, then navigate to the "Routes" section. Click on "Edit route"
![image](assets/)
10. Click on add route
(a) Paste the CIDR in the "Destination" field.
(b) In the target, choose VPC peering
(c) Then choose the peering connection you have created

The connection have been successfully established. Now, resources in the accepter VPC can connect to resources in the requester VPC, and vice versa

Let's see some points that you need to know about VPC Peering, VPC Peering Basics: VPC peering allows direct communication between two VPCs using private IP addresses. Region compatibility: VPC peering can be set up between VPCs in the same AWS region or different regions and the same AWS account or different AWS accounts.

For more reference, you can go through the Create a VPC peering connection.

**CIDR Blocks:** The CIDR blocks of the VPCs involved in the peering connection should not overlap or conflict with each other. Each VPC must have a unique CIDR block.

**IP Addressing:** Resources in one VPC can communicate with resources in the peered VPC using their private IP addresses.

**Security Groups and NACLs:** Ensure proper configuration of Security Groups and Network Access Control Lists (NACLs) to allow traffic between peered VPCs.

**Direct Communication:** Resources in one VPC can directly communicate with resources in the peered VPC without requiring internet access.

**Transitive Traffic:** Traffic cannot flow through a VPC peering connection to reach other VPCs not directly peered.

**Routing:** Update route tables in both VPCs to allow traffic to flow through the peering connection. Each VPC's route table must contain a route entry for the CIDR block of the peer VPC, pointing to the peering connection.

**Limitations:** There are limits on the number of VPC peering connections that can be established per VPC, as well as limitations on the number of route entries per route table.

Now, let's understand some more terms,

### What is VPC endpoint?

Think of a VPC endpoint like a dedicated, secure tunnel between your house (VPC) and a library (AWS service). Instead of going through the bustling streets (public internet), you have a direct pathway from your home to the library. This pathway ensures that only you and authorized users can access the library's resources, like books or documents, without exposing them to outside risks. It's a private, efficient way to access what you need, keeping your data safe from prying eyes on the internet.
