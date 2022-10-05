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

# Using security groups
- Security groups are dynamic

1. You can assign multiple security groups to an instance.
This can be helfpul to combine certain configurations and get sine reusability from your security group definitions.

2. You can change the security group(s) assigned to an instance at any time.

3. Individual rules in your security group can be modified

4. Any changes you make to the security group are applied immediately


# Security Group Rules

## Rule Composition
1. Type A type is a predefined protocol and port combination
2. Protocol, rules define the protocol of the traffic, e.g. 
- TCP(Transmission control protocol )
- UDP(User Datagram Protocol) 
- ICMP(Internet Control Message Protocol)
3. Port Range, specifies which ports are allowed as part of the rule


## Source/Destination
- You can specify a few different things as a source or destination of a rule
1. You can use a security group
    - This will be the ID of another security group in your VPC or a peered VPC.
    - When you set a security group as a source or destination, you are saying that, 
    any machine that is assigned to that security group can then have access over the port and protocol that you've defined and allowed through that rule.
2. IP Address
    - IPv4 or IPv6 CIDR(Classless Inter-Domain Routing) blocks e.g.: 
        - The range of IP addresses from a certain subnet in your VPC
        - Single IP address of a person or machine that needs to have access through that security group. For a single IPv4 address, use `/32` at the end, and for a single IPv6 address, use `/128`

- Outbound rules follow the same format as inbound rules, only that it uses Destination instead of Source

Examples:
 1. Inbound rule on port `80` with  `0.0.0.0/0` as a source means any source.
    - Anything from anywhere can access port 80 on this machine with this rule



# Port 80
Port 80 is the port number assigned to commonly used internet communication protocol, Hypertext Transfer Protocol (HTTP). It is the default network port used to send and receive unencrypted web pages.

When a client attempts to connect to a server and make a request, it needs to know both the server's IP address and which network service will be used to transfer data. To make it convenient for programmers, most popular network services are assigned "well-known" port numbers by default. This strategy began back in 1991 when Tim Berners-Lee's original specification for HTTP stated that if there was no port assigned to an HTTP connection, Port 80 should be used.

# Security Group Rule Description
- Acts as documentation. Your future self will thank you!
- Always document explicitly describing what this security group is for!