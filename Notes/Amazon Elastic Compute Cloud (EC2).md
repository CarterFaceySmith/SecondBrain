On-premise servers for use in [[Cloud Computing]] deployment, uses [[AWS]].

Provides [[Virtual Machines]] referred to as EC2 instances, which gives you control over the guest [[Operating Systems]], these can be any size anywhere in the world available zones.

Launched from Amazon Machine Images (AMIs), note any modifications made to these can be "captured" and used as a new modified AMI later on if desired.

## How to launch an EC2 instance

1. Open your AWS Management Console Launch Instance Wizard from your Management Console
2. Key choices:
	1. AMI: A template used to create an EC2 instance with an OS - Quick Start is standard for basic 
	2. Instance type
		1. Consider *how* your EC2 instance will be used, this choice determines your available resources
		2. E.g. t3.large means t family gen 3 large size instance
		3. If you need to maximise networking performance of your instance and you have interdependent instances you should consider launching them in a cluster placement to reduce latency
			1. Also enable enhanced networking
	3. Specify your network settings
		1. Consider where the instance should be deployed, identify your VPC and optionally the subnet
		2. Do you need a public IP address to make it internet accessible?
	4. Attach IAM role (optional)
		1. Does the software need to interact with other AWS services?
	5. Specify your user data script (optional)
		1. These run the first time your instance starts and can be used strategically to reduce the number of custom AMIs you build and maintain (i.e. by auto-updating or the like)
	6. Specify your storage: Configuring the root vol, additional storage and how those volumes are configured
		1. Options:
			1. [[Amazon Elastic Block Store (EBS)]]
			2. Amazon EC2 Instance Store: ephemeral, data deleted post-instance
			3. Mount [[Amazon Elastic File System (EFS)]]
			4. Connect to [[Amazon Simple Storage Service (S3)]]
	7. Add necessary tags
	8. Add security group settings: A set of firewall rules that control traffic to the instance, exists *outside the instance's guest OS*
	9. Identify or create your key pair to enable secure connection from local machine to EC2 instance

Can be done via CLI: `aws ec2 run-instances --image-id <id> --count 1 --instance-type <type> --key-name MyKeyPair --security-groups MySecGroup --region <region>`

### Note

Consider using an elastic IP address, rebooting of an instance will not change any [[IP Address]]es or [[DNS]] hostnames, but when the instance is stopped then started again they will change (note private IPv4 address and internal DNS hostname don't change).

If a persistent public IP is required, associate an elastic IP, this remains allocated to your account until you choose to release it.

### Metadata and Monitoring

You can navigate to a connected instance IP/latest/metadata to view it and configure or manage ongoing instances.

[[Amazon Cloudwatch]] can be used to monitor EC2 instances and provide metrics if needed.

