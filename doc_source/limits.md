# Limits in AWS Elemental MediaConnect<a name="limits"></a>

The following table describes limits in AWS Elemental MediaConnect\. For information about limits that can be changed, see [AWS Service Limits](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html)\.


| Resource | Default Limit | Comments | 
| --- | --- | --- | 
| Entitlements | 50 per flow | The maximum number of entitlements that you can grant on a flow\. | 
| Flows | 20 per AWS Region |  The maximum number of flows that you can create in each AWS Region\. You can [request a limit increase](https://console.aws.amazon.com/support/cases#/create?issueType=service-limit-increase)\.  | 
| Outputs | 20 per flow | The maximum number of outputs that a flow can have\. | 
| Sources | 1 per flow | The maximum number of sources that you can assign to a flow\. | 

**Note**  
To optimize performance, we recommend that you set up your workflow for an aggregate output bandwidth of 400 Mb/s or less\. For more information, see [Best Practices](best-practices.md)\.