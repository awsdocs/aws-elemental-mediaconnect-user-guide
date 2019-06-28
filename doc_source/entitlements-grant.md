# Granting an Entitlement on a Flow<a name="entitlements-grant"></a>

You can add an entitlement to an existing flow to share your content with another AWS account \(the subscriber account\)\. The subscriber creates an AWS Elemental MediaConnect flow in the same AWS Region, using your flow as the source\. When this happens, the service generates an output on your flow to represent the video stream from your flow to the subscriber's flow\.

The subscriber can use an entitlement only once\.

**Prerequisites**  
Before you can grant an entitlement, you must do the following:
+ Obtain the subscriber's AWS account number\.
+ If you want to encrypt the video as it is sent from your flow to the subscriber's flow, set up encryption using [static key encryption](encryption-static-key-set-up.md) or [Secure Packager and Encoder Key Exchange \(SPEKE\)](encryption-speke-set-up.md)\. 

**To add an entitlement on a flow \(console\)**

1. Open the MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. On the **Flows** page, choose the name of the flow that you want to grant an entitlement on\.

   The details page for that flow appears\.

1. Choose the **Entitlements** tab\.

1. Choose **Grant entitlement**\. The **Grant entitlement** page appears\.

1. For **Name**, specify a name for the entitlement that will help you and the subscriber differentiate this flow from other flows\. The name also becomes part of the entitlement ARN, which is visible to the subscriber\.

1. For **Subscriber account ID**, specify the subscriber's 12\-digit AWS account ID\. Don't include hyphens in the ID\.

1. For **Description**, specify a description that will help you identify this entitlement later\. The description is visible only on the AWS Elemental MediaConnect console for your account\.

1. If you want to encrypt the video as it is sent from your flow to the subscriber's flow, choose one of the following tabs:

------
#### [ Static key encryption ]

   1. In the **Encryption** section, choose **Enable**\.

   1. For **Encryption type**, choose **Static key**\.

   1. For **Role ARN**, specify the ARN of the role that you created when you [set up encryption](encryption-static-key-set-up.md#encryption-static-key-set-up-create-iam-role)\.

   1. For **Secret ARN**, specify the ARN that AWS Secrets Manager assigned when you [created the secret to store the encryption key](encryption-static-key-set-up.md#encryption-static-key-set-up-store-key)\.

   1. For **Encryption algorithm**, choose the type of encryption that you want to use to encrypt the source\.

------
#### [ SPEKE encryption ]

   1. In the **Encryption** section, choose **Enable**\.

   1. For **Encryption type**, choose **SPEKE**\.

   1. For **Encryption algorithm**, choose the type of encryption that you want to use to encrypt the source\.

   1. For **Role ARN**, enter the Amazon Resource Name \(ARN\) of the IAM role that provides you access to send your requests through API Gateway\. You created this role when you [set up encryption](encryption-speke-set-up.md#encryption-speke-set-up-create-iam-role)\.

      The following example shows a role ARN:

      ```
      arn:aws:iam::111122223333:role/SpekeAccess
      ```

   1. For **Resource ID**, enter an identifier for the content\. The service sends this to the key server to identify the current endpoint\. How unique you make this depends on how fine\-grained you want access controls to be\. The resource ID is also known as the content ID\. 

      The following example shows a resource ID:

      ```
      MovieNight20171126093045
      ```

   1. For **Device ID**, enter the value of one of the devices that you configured with your conditional access \(CA\) platform key provider\. 

   1. For **URL**, enter the URL of the API Gateway proxy that you set up to talk to your key server\. The API Gateway proxy must reside in the same AWS Region as AWS Elemental MediaConnect\.

      The following example shows a URL: 

      ```
      https://1wm2dx1f33.execute-api.us-west-2.amazonaws.com/SpekeSample/copyProtection
      ```

   1. \(Optional\) For **Constant initialization vector** enter a 128\-bit, 16\-byte hex value represented by a 32\-character string, to be used with the key for encrypting content\.

------

1. At the bottom of the page, choose **Grant entitlement**\.

1. On the **Entitlements** tab, locate the new entitlement in the list\.

1. Make a note of the entitlement ARN\.

1. Provide the following information to the subscriber:
   + The entitlement ARN
   + The AWS Region that you created the flow in
   + The encryption key and algorithm if you set up encryption on the entitlement