# Entitlements<a name="hp-entitlements"></a>

You can grant an entitlement to share the content in your MediaConnect flow with another AWS account \(subscriber account\)\. When the subscriber sets up a flow based on the entitlement, the service generates an output on your flow to represent the stream from your flow to the subscriber's flow\. This output is counted as part of the 50 maximum outputs that you can have on your flow\. Although you can grant up to 50 entitlements on a flow, the service doesn't allow subscribers to create new flows based on an entitlement after your flow reaches the maximum 50 outputs\.

After you grant an entitlement, you provide information about the entitlement \(name, AWS Region, data transfer subscriber fee, and encryption details\) to the subscriber\. The subscriber uses this information to create a MediaConnect flow that uses your flow as the source\.

If you want to temporarily stop streaming content to the subscriber’s flow, disable the entitlement\. Later, you can enable it to start streaming content again\. If you want to permanently stop streaming content to the subscriber’s flow, revoke the entitlement,

By default, AWS bills your account for the cost for the data transfer between your account and the subscribing account\. However, you can specify that the subscriber is responsible for all or part of that fee\. When you grant the entitlement, you specify the percentage of the entitlement data transfer fee that the subscriber is responsible for\. AWS bills your account for the remainder\. 

## Learn more<a name="hp-entitlements-learn"></a>

[Use case: Entitlements](https://docs.aws.amazon.com/mediaconnect/latest/ug/use-cases-entitlements.html?icmpid=docs_mediaconnect_help_panel)

[Sharing content with other AWS accounts](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements-originator.html?icmpid=docs_mediaconnect_help_panel)

[Granting an entitlement on a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements-grant.html?icmpid=docs_mediaconnect_help_panel)