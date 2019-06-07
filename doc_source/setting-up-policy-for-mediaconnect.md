# Step 4\. Set Up a Policy for AWS Elemental MediaConnect<a name="setting-up-policy-for-mediaconnect"></a>

If any of your sources or outputs are encrypted, you must store your encryption keys in secrets that you save in AWS Secrets Manager\. To allow other services, like AWS Elemental MediaConnect, to read secrets that you save in Secrets Manager, set up a policy that allows read access to those secrets\.

**To set up a policy for AWS Elemental MediaConnect**

1. In the navigation pane of the IAM console, choose **Policies**\.

1. Choose **Create policy**, and then choose the **JSON** tab\.

1. Enter a policy that uses the following format:

   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Action": [
           "secretsmanager:GetResourcePolicy",
           "secretsmanager:GetSecretValue",
           "secretsmanager:DescribeSecret",
           "secretsmanager:ListSecretVersionIds"
         ],
         "Resource": [
           "arn:aws:secretsmanager:us-west-2:111122223333:secret:aes128-1a2b3c",
           "arn:aws:secretsmanager:us-west-2:111122223333:secret:aes192-4D5e6F",
           "arn:aws:secretsmanager:us-west-2:111122223333:secret:aes256-7g8H9i"
         ]
       }
     ]
   }
   ```

   In the `Resource` section, each line represents the ARN of a different secret that you have created\. For more examples, see [IAM Policy Examples for Secrets in AWS Secrets Manager](iam-policy-examples-asm-secrets.md)\.

1. Choose **Review policy**\.

1. For **Name**, enter a name for your policy such as **SecretsManagerForMediaConnect**\.

1. Choose **Create policy**\.