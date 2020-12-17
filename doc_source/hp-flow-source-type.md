# Source type<a name="hp-flow-source-type"></a>

To create a flow, you start by choosing a source type\. Unless you have an entitlement that was granted to you by another AWS account, your choice is always **Standard source**\.

**Note**  
You can't change the source type for a flow after you create it\.

## Standard source<a name="hp-flow-source-type-standard"></a>

You have a standard source if your content comes from a non\-entitlement source\. This is most commonly an on\-premises encoder, but can also include a cloud\-based encoder\.

If you want to specify redundant sources for failover, create the flow with one of the sources\. After the flow is created, update it to enable failover on the source and add the second source to the flow\. Because MediaConnect treats both sources as the primary source, it doesn't matter which one you specify when you first create the flow\.

## Entitled source<a name="hp-flow-source-type-entitled"></a>

You have an entitled source if another AWS account \(content originator\) has granted an entitlement to your account from one of their flows\. This permits you to use the originator's content as the source for your flow\. Before you create a flow with an entitled source, contact the content originator for the following information:
+ The entitlement ARN
+ The AWS Region that the originator created the flow in
**Note**  
You must create your flow in the same Region that the originator's flow is in\.
+ The encryption key and algorithm \(if the originator set up encryption on the entitlement\)
+ The percentage of the entitlement data transfer fee that you are responsible for

## Learn more<a name="hp-flow-source-type-learn"></a>
+ [Creating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Updating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-update.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Entitlements](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Sharing content with other AWS accounts](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements-originator.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Subscribing to content provided by another AWS account](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements-subscriber.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)