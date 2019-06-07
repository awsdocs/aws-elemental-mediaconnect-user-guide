# Setting Up AWS Elemental MediaConnect<a name="setting-up"></a>

Before you start using AWS Elemental MediaConnect, you must sign up for AWS \(if you don’t already have an AWS account\) and create IAM users and roles to allow access to AWS Elemental MediaConnect\. This includes creating an IAM role for yourself\. If you want to use encryption to protect your content, you also must store your encryption keys in AWS Secrets Manager, and then give AWS Elemental MediaConnect permission to obtain the keys from your Secrets Manager account\.

This section guides you through the steps required to configure users to access AWS Elemental MediaConnect\. For background and additional information about identity and access management for AWS Elemental MediaConnect, see [Identity and Access Management for AWS Elemental MediaConnect](security-iam.md)\.

**Topics**
+ [Step 1\. Sign Up for AWS](setting-up-aws-sign-up.md)
+ [Step 2\. Create an Admin IAM User](setting-up-IAM-admin-user.md)
+ [Step 3\. Create Non\-Admin IAM Users](setting-up-create-nonadmin-IAM-users.md)
+ [Step 4\. Set Up a Policy for AWS Elemental MediaConnect](setting-up-policy-for-mediaconnect.md)
+ [Step 5\. Set Up AWS Elemental MediaConnect as a Trusted Entity](setting-up-mediaconnect-trusted-entity.md)
+ [Step 6\. Set Up Encryption \(optional\)](setting-up-encryption.md)
+ [Step 7\. Install the AWS CLI \(optional\)](setting-up-install-cli.md)