# Subnets<a name="hp-vpc-subnets"></a>

Subnets are a range of IP addresses in your VPC\. When you create your VPC, you specify a range of IPv4 addresses for the VPC in the form of a Classless Inter\-Domain Routing \(CIDR\) block; for example, 10\.0\.0\.0/16\. This is the primary CIDR block for your VPC\. When you create a subnet for your VPC, you specify the CIDR block for the subnet, which is a subset of the VPC CIDR block\.

**Important**  
The subnets that you use across all VPC interfaces on the flow must be in the same Availability Zone as the flow\.

## Learn more<a name="hp-vpc-subnets-learn"></a>
+ [Setting up MediaConnect as a trusted service](https://docs.aws.amazon.com/mediaconnect/latest/ug/security-iam-trusted-entity.html?icmpid=docs_mediaconnect_help_panel_hp-vpc-role)
+ [Policy example: Allow MediaConnect to create and manage network interfaces in your VPC](https://docs.aws.amazon.com/mediaconnect/latest/ug/security_iam_resource-based-policy-examples.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow#iam-policy-examples-for-mediaconnect-vpc)