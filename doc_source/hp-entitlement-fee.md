# Data transfer subscriber fee percent<a name="hp-entitlement-fee"></a>

You can specify that the subscriber is responsible for all or part of the entitlement data transfer fee\. AWS bills your account for the remainder\. For example, if you specify 15, AWS bills the subscriber's account for 15% of the entitlement data transfer fee and your account for the remaining 85%\. When you provide details of the entitlement to the subscriber, be sure to specify the percentage of the data transfer fee that will be billed to the subscriber's account\.

You can't change this value after you create the entitlement, even if the subscriber hasn't created a flow yet\.

**Note**  
Even if you specify that the subscriber is responsible for a portion or all of the entitlement data transfer fee, the subscriber will not incur fees until they create and start a flow that is based on this entitlement\.

## Learn more<a name="hp-entitlement-fee-learn"></a>

[Use case: Entitlements](https://docs.aws.amazon.com/mediaconnect/latest/ug/use-cases-entitlements.html?icmpid=docs_mediaconnect_help_panel)

[Sharing content with other AWS accounts](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements-originator.html?icmpid=docs_mediaconnect_help_panel)

[Granting an entitlement on a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/entitlements-grant.html?icmpid=docs_mediaconnect_help_panel)