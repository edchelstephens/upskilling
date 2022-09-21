# Virtual Private Cloud(VPC)
- allows you to secure your resources into groups that follow access rules and share a logical space.
- vpc is commonly used when launching EC2 instances, wether in the service of Elastic Beanstalk, RDS or by themselves in order to easily secure and control access to them.
- Inside of each VPC are one or more subnets
- VPC is free in AWS, just use them in your aws services
# VPC subnets
- futher way to group your resources and assign different rules to each
for example:
VPC 1 
    - private subnet
    - public subnet

The private subnet would house your database and application instances.
The private subnet would have no access to the internet at all, keeping it quite secure

The public subnet, on the other hand, would have access tot he internet and could utilize security groups to make it secure.