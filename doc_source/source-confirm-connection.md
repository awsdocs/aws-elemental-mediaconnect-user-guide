# Confirming the Connection of a Flow to Its Source<a name="source-confirm-connection"></a>

On the AWS Elemental MediaConnect console, you can view the status of the connection between a flow and its source\.

**To confirm the connection of a flow to its source \(console\)**

1. Open the AWS Elemental MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. On the **Flows** page, choose the name of the flow\.

1. Choose the **Source** tab\.

1. View the **Source health** field\. There are two possible values:
   + **Connected** indicates that the flow is connected successfully to its source\.
   + **Disconnected** indicates that the flow is not connected to its source\. To resolve this issue, verify that the source is actually sending content\. Also, check the source settings on the flow such as the whitelist CIDR and the protocol configuration\.