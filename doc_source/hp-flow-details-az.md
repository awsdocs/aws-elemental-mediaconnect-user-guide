# Availability Zone<a name="hp-flow-details-az"></a>

An Availability Zone is a distinct location in an AWS Region\. Each Availability Zone is isolated, but the Availability Zones in a Region are connected to each other with low latency, high throughput, and highly redundant networking\. 

If you create multiple flows for redundancy, choose a different Availability Zone for each flow\. 

If your source comes from your virtual private cloud \(VPC\), we recommend that you leave this as **Any** and let the service ensure that the Availability Zone is set correctly\.

If you leave the Availability Zone set to **Any**, MediaConnect assigns a random Availability Zone within the current AWS Region, or if your source comes from a VPC, the service assigns the Availability Zone of the VPC subnet to the flow\.

**Note**  
You can't change the Availability Zone for a flow after you create it\.

## Learn more<a name="hp-flow-details-az-learn"></a>
+ [Flows](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Creating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Updating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-update.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)