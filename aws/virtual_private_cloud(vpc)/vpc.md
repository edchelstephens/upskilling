# Virtual Private Cloud(VPC)
- allows you to secure your resources into groups that follow access rules and share a logical space.
- vpc is commonly used when launching EC2 instances, wether in the service of Elastic Beanstalk, RDS or by themselves in order to easily secure and control access to them.
- Inside of each VPC are one or more subnets
- VPC is free in AWS, just use them in your aws services
- VPC is a logically isolated piece of the AWS cloud, it's like your own private data center
- The VPC is the foundation for all EC2 instances, meaning if you're going to use an EC2 or compute instance, all of the virtual machines offered by Amazon, you will be using a VPC
- VPC is where you can define:
    - Subnets
    - IP address range for instances
    - Access control to and from instances

- VPC belongs to a region, it spans all availabilty zones
- You can have multiple VPCs within the same region
- VPCs contain one or more subnets
    - a subnet is tied to a single availability zone
    - ec2 instances launched into subnets

- When you create an AWS account, Amazon creates a default VPC for you in each region. This allows you to launch virtual machines for the EC2 service withouth really having to configure or think about anything.

## IPv4 address range required for VPC
- This is specified using classless inter-domain rougint or CIDR blocks
- In AWS, the allowed block size is between `/16` and `/28`.
This translates to:
`10.0.0.0/16` - 65,536 possible addressess(`10.0.0.0 - 10.0.255.255`)
`10.0.0.0/28` - 16 possible addresses (`10.0.0.0 - 10.0.0.15`)

For each subnet block, AWS reserves the first four and the last address.
`10.0.0.0/20`
// Reserved:
10.0.0.0
10.0.0.1
10.0.0.2
10.0.0.3
10.0.15.255


## Each subnet CIDR block must be a subset of your VPC CIDR and your subnets cannot overlap

e.g 
- VPC 10.0.0.0/16
 - subnet 1: 10.0.0.0/20 (10.0.0.4 - 10.0.15.254)
 - subnet 2: 10.0.16.0/20 (10.0.16.4 - 10.0.31.245)

As you desing your VPCs, be sure that you have enough capacity for all instances that you will need to launch on in your VPC and subnets

When instances are launched, their IP address is determined by the subnet CIDR.

External IP addresses are not assigned by default
You must specify if you want a public IP on instance creation.

This external IP address is assigned by AWS form their pool of public IP addresses.
If you stop your instance then start it again, this IP address can and usually does change.
If you want to keep the same IP address for an instance that you know you will be stopping and starting,  you can use an `elastic IP`. An `elastic IP` stays assigned to an instance unti you unassign it.

# Ingress(entering) and Egress(leaving) Control
- `Security Groups` are one of the most heavily used methods of determining allowed traffic to and from your instances. In security groups, you can specify ports, protocols, sources and desitnations that are aloowed to access your instance.

- `Network Access Contorl Lists(NACL)` are also available to specify allow or deny rules for traffic in and out of a subnet. You can define a network access control list then associate one or more subnets with that control list.

- VPC can also be peered to allow traffic to flow from one VPC to another as if they were in the same network

- VPCs can be accessed via virtual private network(VPN).
You can define route tables in your VPC to control traffic in and out of subnets.
AN internet gateway can be associated with your VPC to provide access to the external public internet.

- If your private subnet neeeds access tot he external public internet, you can use a NAT gateway to provide that access.
- A NAT gateway is a `Network Adress Translation(NAT) service. You can use a NAT gateway so that instances in a private subnet can connect to services outside your VPC but external services cannot initiate a connection with those instances.





# VPC subnets
- futher way to group your resources and assign different rules to each
for example:
VPC 1 
    - private subnet
    - public subnet

The private subnet would house your database and application instances.
The private subnet would have no access to the internet at all, keeping it quite secure

The public subnet, on the other hand, would have access tot he internet and could utilize security groups to make it secure.