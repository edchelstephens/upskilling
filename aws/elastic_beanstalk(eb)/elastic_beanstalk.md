# Elastic Beanstalk (EB)
- an application service that makes it easy to run your code and scale it on AWS
- under the covers, it's simply running your code on EC2 instances but it takes the typical use case of runing an application and adds a lot of conveniences that makes AWS much easier to work with.
- Elastic Beanstalk is a free AWS service but you pay for:
    - the ec2 instances
    - load balancers
    - s3 
    which are being used in your elastic beanstalk application environment

# EB structure - Application
- The main abstract structure in elastic beanstalk is an "Application"
- Application is the root-level organization
- Inside of each application can be many application versions
- Application version is the actual code that will run your application
- Application versions are stored in S3
- Each application has a limit of 1000 versions, if you hit this limit then go and delete old uneeded versions of the application

# EB structure - Environment
- With an application version of your code, you can deploy it to an "Environment"
- An environment is the rules and configuration that manages the actual EC2 instances your app is running on.
- Each environment can run with a different platform, like Java or Node or python and can be configured with certain EC2 instance types.
- Configuring each environment in Elastic Beanstalk is where you'll spend most of your time since you can setup the deployment, load balancing and scaling rules there.

- elastic beanstalk provisions resources and runs your application

# .ebextension files
- JSON or YAML format files located in `.ebextension` folder of your application bundle
- They must bo of `.config` file type and if there are multiple files, **ones that are first alphabetically are first applied**, meaning that they have the lowest precedence priority.