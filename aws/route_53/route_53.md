# Route 53
- Amazon's service for DNS management, both insed and outside of AWS
- It allows you to easliy configure domain names to resolve to internal AWS services.
- works by first setting up a hosted zone
- A "hosted" zone is basically a root domain name, like example.com, google.com, djangoboys.dev etc
- you can use Route53 to setup subdomains like www.example.com or mail.example.com and configure them to route to AWS resources

# Domain Name System(DNS)
- System that translates human-readable URLs to IP addresses

- When most people think of DNS, the Domain Name System, they think of a very specific use case: you want to visit a website and in order to do so, you have to connect to its IP address, but IP addresses are hard to remember, names however are easy to remember. So DNS creates a mapping between an easy to remember name to a hard to remember IP address.
This is the most familiar use case of DNS, BUT it is not the only use case.

- In DNS terms, you're looking up a name to locate a type of a resource. 

# You can think of DNS as a database

Example:
Domain name:
example.com

Resource type
A(IP address)

Resource data:
93.184.215.21

- Together, `example.com` and the resource type `A` form a pairing.
- DNS associates this pairing with some value called the `resource data`, which in the case above is an IP address.
- Together the domain name, `example.com`, resource type `A` and the resource data which is an IP address of `93.184.215.21` form part of a resource record.

# What is a Domain Name?
- you may think of `example.com` or `company.ph`,
but more generally, you may think of a domain name in the format of `string.string` or `<string>.<string>`. Believe it or not `string.string` is a valid domain name. 

A domain name is just a list of labels separated by dots. But the labels are not arbitrary. They are organized into a tree structure.

e.g.:

`web.example.com`

Tree structure:

`com`
`example`
`web`

- There is actually one more label, which is a null zerolength label a the root of the tree. This is called the root label and it's ofent represented as just a dot `.` This is always implied.

So the actual tree structure, with domain name:

Tree                        Domain Name
`.`                             - `.`
`com`                       - `com.`
`example`                - `example.com.`
`web`                       - `web.example.com.`

The entire tree structure is called the `Domain Name Space`. Every node connected tot he root and the root itself is part of the domain name space.

# Domain name
- The list of labels on the path from the node to the root of the tree(RFC 1034)
- In other words, a domain name describes a node on the tree by tracing the node all the way back to the root. Every label along that path becomes part of the domain name.

- You can use `google.com.` or just `google.com`
the root domain `.` is implied.

# DNS is a database for storing resource records.
# DNS is scalable in 2 respects:
1. Can store an increasing and ever changing set of nodes
2. It's not necessarily controlled by a single person or group