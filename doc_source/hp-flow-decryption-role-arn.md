# Role ARN<a name="hp-flow-decryption-role-arn"></a>

During your initial setup, you created an IAM role with permission to read the secret that you stored in AWS Secrets Manager and you [defined MediaConnect as a trusted entity](https://docs.aws.amazon.com/mediaconnect/latest/ug/encryption-static-key-set-up.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow#encryption-static-key-set-up-create-iam-role) that can assume the role\. By doing that, you allowed MediaConnect to have read access to your secret\. This field indicates the ARN of the IAM role that you created\. MediaConnect needs that ARN to gain access to the secret\. 

From the drop\-down menu, choose the ARN of the IAM role that you created\. MediaConnect populates the drop\-down menu based on IAM roles that meet all of the following criteria: 
+ The role is associated with your account
+ You have at least read permission for the role
+ MediaConnect is set up as a trusted entity for the role

If a role doesn't meet all three of those criteria, it won't appear in the drop\-down menu\. However, you can manually input the ARN of the role even if it's not in the list\. MediaConnect can still use that role to decrypt the content, as long as MediaConnect is set up as a trusted service for the role\.

## Learn more<a name="hp-flow-decryption-role-arn-learn"></a>
+ [Data protection](https://docs.aws.amazon.com/mediaconnect/latest/ug/data-protection.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Setting up static key encryption](https://docs.aws.amazon.com/mediaconnect/latest/ug/encryption-static-key-set-up.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)