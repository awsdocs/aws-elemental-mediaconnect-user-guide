# Granting an Entitlement on a Flow<a name="entitlements-grant"></a>

You can add an entitlement to an existing flow to share your content with another AWS account \(the subscriber account\)\. The subscriber can create an AWS Elemental MediaConnect flow, using your flow as the source\. When this happens, the service generates an output on your flow to represent the video stream from your flow to the subscriber's flow\.

**Important**  
If you want to encrypt the video as it is sent from your flow to the subscriber's flow, [store the encryption key](key-management.md#key-management-store-encryption-keys) in AWS Secrets Manager before you begin this procedure\. 

The subscriber can use an entitlement only once\.

**To add an entitlement on a flow \(console\)**

1. Open the AWS Elemental MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. On the **Flows** page, choose the name of the flow that you want to grant an entitlement on\.

   The details page for that flow appears\.

1. Choose the **Entitlements** tab\.

1. Choose **Grant entitlement**\. The **Grant entitlement** page appears\.

1. For **Name**, specify a name for the entitlement that will help you and the subscriber differentiate this flow from other flows\. The name also becomes part of the entitlement ARN, which is visible to the subscriber\.

1. For **Subscriber account ID**, specify the subscriber's 12\-digit AWS account ID\. Don't include hyphens in the ID\.

1. For **Description**, specify a description that will help you identify this entitlement later\. The description is visible only on the AWS Elemental MediaConnect console for your account\.

1. If you want to encrypt the video as it is sent from your flow to the subscriber's flow, do the following:

   1. In the **Encryption** section, choose **Enable**\.

   1. For **Encryption type**, choose **Static key**\.

   1. For **Role ARN**, specify the ARN of the role that you created during setup \(when you [set up AWS Elemental MediaConnect as a trusted entity](setting-up-mediaconnect-trusted-entity.md)\)\.

   1. For **Secret ARN**, specify the ARN that AWS Secrets Manager assigned when you [created the secret to store the encryption key](key-management.md#key-management-store-encryption-keys)\.

   1. For **Encryption algorithm**, choose the type of encryption that you want to use to encrypt the source\.

1. At the bottom of the page, choose **Grant entitlement**\.

1. On the **Entitlements** tab, locate the new entitlement in the list\.

1. Make a note of the entitlement ARN\.

1. Provide the following information to the subscriber:
   + The entitlement ARN
   + The AWS Region that you created the flow in
   + The encryption key and algorithm if you set up encryption on the entitlement