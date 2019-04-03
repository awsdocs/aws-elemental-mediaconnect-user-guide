# Outputs in AWS Elemental MediaConnect<a name="outputs"></a>

Each flow can have up to 20 outputs\. You can add and remove outputs at any time, even when the flow is active\. These outputs are sent to the IP address that you specify\. This option is useful if you intend to send your content to an on\-premises encoder\.

Another way outputs can be added to a flow is from an entitlement\. You can [grant an entitlement](entitlements-grant.md) to share your content with another AWS account \(subscriber account\)\. When the subscriber creates a flow using your content as the source, AWS Elemental MediaConnect generates an output on your flow\.

**Topics**
+ [Adding Outputs to a Flow](outputs-add.md)
+ [Viewing a List of Outputs of a Flow](outputs-view-list.md)
+ [Updating Outputs on a Flow](outputs-update.md)
+ [Removing Outputs from a Flow](outputs-remove.md)