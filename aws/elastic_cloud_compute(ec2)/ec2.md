# Amazon Machine Image(AMI)
- Operating system and sfotware used on an EC2 instance
- An image is a combination of an operating system and
some preinstalled applications, typically things like Java, Python or the AWS CLI tools.
- Once an instance is created with an image, Amazon won't be updating that instance's software. You need to manually do it yourself.
- AWS only updates the images


# Storage in EC2
- Storage in ec2 is conceptualized by the term Elastic Block Storage(EBS)
- EBS is essentially a storage service that makes it easy to reason about and calculate charges for storage
- Lives independently from your ec2 instance. Can be retained or deleted when the ec2 instance is deleted.
- Use EBS for EC2 file systems, add volumes with volume size
- EBS is not the same as Simple Storage Service(S3)
- EBS is specifically for using with EC2