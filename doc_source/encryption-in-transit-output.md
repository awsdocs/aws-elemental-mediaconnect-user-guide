# Setting Up Encrypted Outputs in AWS Elemental MediaConnect<a name="encryption-in-transit-output"></a>

If you want to encrypt your flow output, you must save the encryption key in AWS Secrets Manager\. You must also make sure that the IAM policy that you created during setup includes this new secret\.

**Note**  
Encryption is supported only for outputs that use Zixi protocol\.

**To set up an encrypted output \(console\)**

1. Determine the encryption key that you want to use to encrypt the output\.

1. [Store the encryption key](key-management.md#key-management-store-encryption-keys) in Secrets Manager\.

1. Make a note of the secret ARN from Secrets Manager\. You will need this information later in this procedure\.

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. Make sure that the [IAM policy that you created during setup](setting-up-policy-for-mediaconnect.md) includes the new secret that you just created\.

1. Open the AWS Elemental MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. [Create an output](flows-create.md) on your flow\. When you specify the source details, choose to encrypt the output\. You will need the ARN of the secret that you created earlier in this procedure\.