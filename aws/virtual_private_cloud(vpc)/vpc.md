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


# VPC subnets
- futher way to group your resources and assign different rules to each
for example:
VPC 1 
    - private subnet
    - public subnet

The private subnet would house your database and application instances.
The private subnet would have no access to the internet at all, keeping it quite secure

The public subnet, on the other hand, would have access tot he internet and could utilize security groups to make it secure.