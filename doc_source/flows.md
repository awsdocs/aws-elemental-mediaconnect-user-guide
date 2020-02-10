# Flows in AWS Elemental MediaConnect<a name="flows"></a>

A flow is a transport between a source and one or more destinations\. When you create a flow, you specify one source, a name, and an Availability Zone\. After you create a flow, you can add up to 50 outputs to indicate where you want your content to be sent and how you want it transported\.

If you want to share your content with another AWS account, grant an entitlement on the flow\. A user of the subscriber account can then create a new AWS Elemental MediaConnect flow using your flow as the source\. When this happens, the service generates an output on your flow to represent the stream that feeds the subscriber's flow\. 

It is important to manage the number of outputs and entitlements that you create on a flow\. Each flow can only have 50 outputs\. Although you can grant up to 50 entitlements on a flow, each of those entitlements will generate an output\. For example, you create a flow named **BasketballGame** and you add 40 outputs that send content to on\-premises encoders\. You also grant 30 entitlements to share your content with other AWS accounts\. When your subscribers create flows using **BasketballGame** as their source, the service generates new outputs for each of those subscribers\. After the first 10 subscribers create flows, your **BasketballGame** flow reaches its maximum number of outputs \(40 for the original outputs that you created and another 10 that the service created for the subscribing flows\)\. When the 11th subscriber tries to create a flow using **BasketballGame** as a source, the service returns an error\.

**Topics**
+ [Creating a Flow](flows-create.md)
+ [Viewing a List of Flows](flows-view-list.md)
+ [Viewing the Details of a Flow](flows-view-details.md)
+ [Starting a Flow](flows-start.md)
+ [Stopping a Flow](flows-stop.md)
+ [Updating a Flow](flows-update.md)
+ [Managing Tags on a Flow](flows-manage-tags.md)
+ [Deleting a Flow](flows-delete.md)