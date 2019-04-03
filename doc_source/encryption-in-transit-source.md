# Setting Up Encrypted Sources in AWS Elemental MediaConnect<a name="encryption-in-transit-source"></a>

If your source is encrypted, you must save the encryption key in AWS Secrets Manager\. You must also make sure that the IAM policy that you created during setup includes this new secret\.

**Note**  
Encryption is supported only for sources that use Zixi protocol\.

**To set up an encrypted source \(console\)**

1. Obtain the encryption key from the entity that manages the source\.

1. [Store the encryption key](key-management.md#key-management-store-encryption-keys) in Secrets Manager\.

1. Make a note of the secret ARN from Secrets Manager\. You will need this information later in this procedure\.

1. Open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. Make sure that the [IAM policy that you created during setup](setting-up-policy-for-mediaconnect.md) includes the new secret that you just created\.

1. Open the AWS Elemental MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. [Create your flow](flows-create.md)\. When you specify the source details, choose to decrypt the source\. You will need the ARN of the secret that you created earlier in this procedure\.