# Security Groups
- Security groups belong to a VPC- assigned at instance level
- can use same security group in different subnets in same VPC
- Same subnet can have different security groups
- Security groups control access to and from your EC2 instancesdd

A security group is a virtual firewall for your EC2 instance to control inbound and outbound traffic to and from your instance.

- made up of a set of inbound and outbound rules.

# Traffic flow to individual instance
1. Traffoc will come from either an internet gateway or a virtual private network(vpn)
2. Then it will go to the router
3. Then the route table is the next step to determine what to do with that traffic
4. Then next is Network Access Control List or NACL
5. Finally, the traffic will go to the instance Security Group and specifically the inbound rule of the security group
6. If the traffic is allowed by the inbound rule, then and only then, will it go to the instance.