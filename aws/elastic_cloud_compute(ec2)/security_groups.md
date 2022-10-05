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

- When troubleshooting access problems, often it is helpful to begin at the security group
then work your way up the stack looing for problems in your configuration

# Security Group vs Network Access Control List(NACL)

## Security Group
- operates at instance level and is assigned to individual instances
- Allow rules only
- evaluate all rules before allowing traffic - All
- Stateful: return traffic automatically allowed regardless of any rules,
for example, if you had an allow rule on port 80 to let traffic in,
any response would be allowed to go out regardless of any outbound rule or lack of rules
- Applies to instance only if instance is associated with security group. It could be possible to create an instance and forget to associate it with the correct security groups, be careful on this one!
# NACL
- operates at subnet level. You don't have to remember to assing an instance to it.
- Allow or deny rules
- Rules are processed in numeric order until there is a match - Any
- Stateless: return traffic must be explicitly allowed by rules. Just because there was an allow rule inbound does not automatically allow that same traffic to go outbound 
- Automatically applies to all instances in subnets associated with the NACL