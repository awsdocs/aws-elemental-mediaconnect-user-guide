# AWS CLI commands for AWS Elemental MediaConnect<a name="cli-commands"></a>

The following table shows the AWS CLI commands that you can use to create or modify flows in AWS Elemental MediaConnect\.


| Command | Applies to | Description | 
| --- | --- | --- | 
| Entitlements | grant\-flow\-entitlements | Grants entitlements on a flow\. | 
| Entitlements | list\-entitlements | Displays a list of all entitlements that have been granted to this account\. | 
| Entitlements | revoke\-flow\-entitlement | Revokes the specified entitlement from a flow\. After an entitlement is revoked, the content becomes unavailable to the subscriber and the associated output is removed\. | 
| Entitlements | update\-flow\-entitlement | Updates the specified entitlement on the specified flow\. You can change an entitlement's description, subscriber account ID, and encryption\. If you change the subscriber account ID, the service removes the output that was generated when the original subscriber set up their flow\. | 
| Flows | create\-flow | Creates a flow\. | 
| Flows | delete\-flow | Deletes a flow\. You must stop a flow before you can delete it\. | 
| Flows | describe\-flow | Retrieves information about a flow in your account\. | 
| Flows | list\-flows | Lists all the flows that are associated with your account\. | 
| Flows | start\-flow | Starts a flow\. | 
| Flows | stop\-flow | Stops a flow\. | 
| Outputs | add\-flow\-outputs | Adds outputs to a flow\. | 
| Outputs | remove\-flow\-output | Removes the specified outputs from a flow\. | 
| Outputs | update\-flow\-output | Updates the specified output of a flow\. | 
| Source | update\-flow\-source | Updates the source of a flow\. | 