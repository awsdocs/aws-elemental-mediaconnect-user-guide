# Key Management in AWS Elemental MediaConnect<a name="key-management"></a>

You can protect your content from unauthorized use through encryption\. Store your encryption keys in AWS Secrets Manager, and then give AWS Elemental MediaConnect permission to obtain the encryption keys from your Secrets Manager account\.

You must store your encryption keys if any of the following apply:
+ You want to create a flow that uses an encrypted source
+ You want to create a flow based on an entitlement that uses encryption
+ You want to encrypt the output of your flow

## Storing Encryption Keys in AWS Secrets Manager<a name="key-management-store-encryption-keys"></a>

The Secrets Manager secret that stores your encryption keys must be created using the same AWS account that creates the flow\. AWS Elemental MediaConnect does not support cross\-account sharing of secrets\.

**Note**  
You must create the secret in the same AWS Region as your flow\. If you are using two flows to distribute video from one AWS Region to another, you must create two secrets: one secret in each Region\. 

**To store encryption keys in Secrets Manager \(console\)**

1. Sign in to the AWS Secrets Manager console at [https://console\.aws\.amazon\.com/secretsmanager/](https://console.aws.amazon.com/secretsmanager/)\.

1. Choose **Store a new secret**\.

1. In the **Select secret type** section, choose **Other type of secrets**\.

1. In the **Specify the key/value pairs to be stored in this secret** section, choose **Plaintext**\.

1. Clear any text in the box and replace it with the password value\.

1. Keep the **Select the encryption key** set to **DefaultEncryptionKey**\.

1. Choose **Next**\.

1. For **Secret name**, specify a name for your password\. For example, **2018\-12\-01\_baseball\-game\-source**\.

1. Choose **Next**\.

1. In the **Configure automatic rotation** section, choose **Disable automatic rotation**\.

1. Choose **Next**, and then choose **Store**\.

   The details page for your new secret appears, showing information such as the secret ARN\. You will need this value when you create a flow that uses the encryption key that you just stored\.