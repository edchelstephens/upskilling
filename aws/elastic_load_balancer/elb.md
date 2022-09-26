# Elastic Load Balancing
- provides a way to distribute incoming traffic to EC2 instances where auto-scaling groups of EC2 instances, containers, IP addresses, Lambda functions or serverless computing as well as on-premises resources if you're running a hybrid which combines cloud and on-premises.

- Elastic Load Balancing is designed for high availability.
It's auto-scaling, so there's no need to provision more to handle more traffic. Once you created an elastic load  balancer, it will handle the traffic and scale up and down as needed.

# Load Balancer Types
1. Application Load Balancer
- The application load balancer can handle HTTP and HTTPS traffic
- Layer 7 routing(request level)
- User aiuthentication(identity provider)
- Sticky sessions
- Redirects

For Security;
- support HTTPS termination and certificate management
- SSL/TLS decryption
- User authentication via direct connect to identity provider


2. Network Load Balancer
- Operates on TCP and TLS protocols.
- Layer 4 routing(connection level)
- Millions of request per second
- Very low latency
- Long-lived TCP connections
- Listeners:
    - Protocol
    - Port.

Internall or externally facing
Internal meaning only receiving raffic from your private subnets
External meaning receiving traffic from the outside internet.
You can define your listeners by protocol and port and indicate which availability zones your load balancer will service.

The `target group` is how you identify where you will send the traffic, 
be it instances, Lambdas, whatever it is that you're distributing the traffic to goes in the target group.





## TCP or Transmission Control Protocol
- a communications standard that enables application programs and computing devices to exchange messages over a network. It is designed to send packets across the internet and ensure the successful delivery of data and messages over networks

## TLS or Transport Layer Security
- a cryptographic protocol designed to provide communications security over a computer network. The protocol is wisely used in applications such as email, instant messaging, and voice over IP, but its use in securing HTTPS remains the most publicly visible.

## SSL - Secure Sockets Layer
- standard  technology for keeping an internet connection secure and safeguarding any senstive data that is being sent between two systems.
TLS or Transport Layer Security is the upgraded version of SSL
