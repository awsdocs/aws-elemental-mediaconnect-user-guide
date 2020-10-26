# Flows<a name="hp-flows"></a>

A MediaConnect flow is a transport between a source and one or more destinations\. Each flow has one source, a name, and an Availability Zone\.

After you create a flow, you can add outputs to indicate where you want your content to be sent and how you want it transported\. You can also grant entitlements to share your content with other AWS accounts, called subscriber accounts\. A user of a subscriber account can then create a new flow using your flow as the source\. When this happens, MediaConnect generates an output on your flow to represent the stream that feeds the subscriber's flow\.

When you start your flow, MediaConnect transports content from the source to any outputs that exist on the flow\. This includes outputs that you created, as well as outputs that the service created when subscriber accounts create flows based on entitlements that you granted\. Stopping the flow disrupts the stream to outputs and entitlements immediately\.

From this page, you can do the following:
+ Create a flow
+ Start and stop existing flows
+ Update an existing flow \(update the source, add outputs, and grant entitlements\)

## Learn more<a name="hp-flows-learn"></a>

[Flows](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows.html?icmpid=docs_mediaconnect_help_panel_hp-flows)

[Creating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html?icmpid=docs_mediaconnect_help_panel_hp-flows)

[Updating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-update.html?icmpid=docs_mediaconnect_help_panel_hp-flows)