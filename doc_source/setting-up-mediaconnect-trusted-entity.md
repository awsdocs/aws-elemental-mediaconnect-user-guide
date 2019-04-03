# Step 5\. Set Up AWS Elemental MediaConnect as a Trusted Entity<a name="setting-up-mediaconnect-trusted-entity"></a>

After you set up a policy that allows read access to secrets that you save in Secrets Manager, you create a role and assign the policy that you created to that role\. You also need to identify AWS Elemental MediaConnect as a trusted entity\.

**To set up permissions for AWS Elemental MediaConnect**

1. In the navigation pane of the IAM console, choose **Roles**\.

1. On the **Role** page, choose **Create role**\. The **Create role** page appears\.

1. For **Select type of trusted entity**, choose **AWS service** \(the default\)\.

1. For **Choose the service that will use this role**, choose **EC2**\. 

   You choose EC2 because AWS Elemental MediaConnect is not currently included in this list\. Choosing EC2 lets you create a role\. In a later step, you change this role to include AWS Elemental MediaConnect instead of EC2\.

1. Choose **Next: Permissions**\.

1. For **Attach permissions policies**, enter the name of the policy that you created in the previous step, such as **SecretsManagerForMediaConnect**\. 

1. Select the check box next to **SecretsManagerReadWrite**, and then choose **Next: Review**\.

1. For **Role name**, enter a name\. We highly recommend that you don't use the name `MediaConnectAccessRole` because it is reserved\. Instead, use a name that includes `MediaConnect` and describes this role's purpose, such as **MediaConnect\-ASM**\.

1. For **Role description**, replace the default text with a description that will help you remember the purpose of this role\. For example, **Allows MediaConnect to view secrets stored in AWS Secrets Manager\.**

1. Choose **Create role**\.

1. In the confirmation message that appears across the top of your page, choose the name of the role that you just created\.

1. Choose **Trust relationships**, and then choose **Edit Trust Relationship**\.

1. For **Policy Document**, change `ec2.amazonaws.com` to `mediaconnect.amazonaws.com`\. 

   The policy document should now look like this: 

   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": {
           "Service": "mediaconnect.amazonaws.com",
         },
         "Action": "sts:AssumeRole",
       },
     ],
   }
   ```

1. Choose **Update Trust Policy**\.

1. On the **Summary** page, make a note of the value for **Role ARN**\. It looks like this: `arn:aws:iam::111122223333:role/MediaConnectASM`\.