# Source whitelist<a name="hp-source-whitelist"></a>

Specify a range of IP addresses that should be allowed to contribute content to your source\. These IP addresses must be in the form of a Classless Inter\-Domain Routing \(CIDR\) block; for example, 10\.0\.0\.0/16\. The source needs to be in the range covered by this CIDR block\. Any IP address within this range is allowed to send content to this flow\.

It is important to be as precise as possible when you specify the CIDR block\. Include only the IP addresses that you want to contribute content to your flow\. If you specify a CIDR block that is too wide, it allows for the possibility of outside parties sending content to your flow\.

## Learn more<a name="hp-source-whitelist-learn"></a>
+ [Creating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Updating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-update.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)