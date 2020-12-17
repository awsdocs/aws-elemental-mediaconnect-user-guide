# Alerts<a name="hp-alerts"></a>

You can see the full list of alerts for a flow in Amazon CloudWatch\. However, the **Alerts** tab on the MediaConnect console displays a list of alerts that occurred when you started or stopped the current flow\. 

The types of alerts that the service displays on this tab include the following:
+ The entitlement that this flow is based on is already in use\. This can occur if you create more than one flow based on the entitlement, for example, Flow A and Flow B\. If you started Flow A already, MediaConnect displays an alert if you try to start Flow B\.
+ The entitlement that this flow is based on no longer exists\. This can occur if the account that granted the entitlement \(the content originator\) revoked the entitlement\.
+ The entitlement that this flow is based on does not have an active source\. This can occur if the originator's flow is deleted or stopped\. When you start your flow based on that entitlement, there is no content coming from the originator's flow\.
+ The decyrption or encryption information for the flow isn't valid\. This can happen for a number of reasons\. For example, the decryption key doesn't match the type for the specified algorithm\. Or, your flow is based on an entitlement that uses SPEKE encryption and MediaConnect can't contact the conditional access \(CA\) platform key provider\.
+ Your flow is based on an entitlement, and the content originator's flow already has the maximum number of outputs\. 

## Learn more<a name="hp-alerts-learn"></a>

[Monitoring MediaConnect with Amazon CloudWatch metrics](https://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch.html??icmpid=docs_mediaconnect_help_panel_alerts)

[Viewing the details of a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-view-details.html?icmpid=docs_mediaconnect_help_panel_alerts)