# Sharing Content with Other AWS Accounts<a name="entitlements-originator"></a>

You can grant an entitlement to share the content in your AWS Elemental MediaConnect flow with another AWS account \(subscriber account\)\. When the subscriber sets up a flow based on the entitlement, the service generates an output on your flow to represent the stream from your flow to the subscriber's flow\. This output is counted as part of the 50 maximum outputs that you can have on your flow\. 

You can grant, update, and revoke entitlements at any time, even on an active flow\. You can also specify the percentage of the entitlement data transfer fee that you want the subscriber to be responsible for\.

After you grant an entitlement, you provide information about the entitlement \(name, AWS Region, and encryption details\) to the subscriber\. The subscriber uses this information to create an AWS Elemental MediaConnect flow that uses your flow as the source\. The subscriber's flow must be in the same AWS Region as your flow\. If the subscriber wants a flow in a different Region, they must create a second flow in the new Region\. The following illustration shows this process\.

![\[This illustration shows the setup for sharing content across AWS Regions.\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/)

**Topics**
+ [Granting an Entitlement on a Flow](entitlements-grant.md)
+ [Updating an Entitlement](entitlements-update.md)
+ [Managing Tags on an Entitlement](entitlements-manage-tags.md)
+ [Revoking an Entitlement](entitlements-revoke.md)