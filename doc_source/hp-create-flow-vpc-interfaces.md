# VPC interfaces<a name="hp-create-flow-vpc-interfaces"></a>

A virtual private cloud \(VPC\) is a virtual network dedicated to your AWS account\. You create a VPC using Amazon Virtual Private Cloud \(Amazon VPC\)\. A VPC closely resembles a traditional network that you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS\.

In MediaConnect, you can add an interface with your VPC to establish a connection between your VPC and your flow\. After you make that connection, you can use your VPC as a source for the flow\. You can also add an output to send your content to the VPC\. This can be valuable when you want to stream content directly between your VPC and MediaConnect without going over the public internet\.

You can add two VPC interfaces to each flow\. 

Each VPC interface is composed of the following information:
+ VPC interface name – A unique name for each VPC interface within the flow\. 
+ Role ARN – The ARN of the IAM role that you created when you set up MediaConnect as a trusted service\. 
+ VPC – The ID of the VPC that you want to connect with your flow\.
+ Subnets – A range of IP addresses in your VPC\. When you create your VPC, you specify a range of IPv4 addresses for the VPC in the form of a Classless Inter\-Domain Routing \(CIDR\) block; for example, 10\.0\.0\.0/16\. This is the primary CIDR block for your VPC\. When you create a subnet for your VPC, you specify the CIDR block for the subnet, which is a subset of the VPC CIDR block\.
**Important**  
The subnets that you use across all VPC interfaces on the flow must be in the same Availability Zone as the flow\. If you don't specify an Availability Zone for the flow, MediaConnect automatically creates the flow in the same Availability Zone that the subnets are in\.
+ Security groups – A virtual firewall to control inbound and outbound traffic\.

## Learn more<a name="hp-create-flow-vpc-interfaces-learn"></a>
+ [Creating a flow that uses a VPC source](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create-vpc-source.html?icmpid=docs_mediaconnect_help_panel_hp-vpc-interfaces)
+ [Adding a VPC source to an existing flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/source-adding-vpc.html?icmpid=docs_mediaconnect_help_panel_hp-vpc-interfaces)
+ [Adding a VPC output](https://docs.aws.amazon.com/mediaconnect/latest/ug/outputs-add-vpc.html?icmpid=docs_mediaconnect_help_panel_hp-vpc-interfaces)
+ [Setting up MediaConnect as a trusted service](https://docs.aws.amazon.com/mediaconnect/latest/ug/security-iam-trusted-entity.html?icmpid=docs_mediaconnect_help_panel_hp-vpc-role)