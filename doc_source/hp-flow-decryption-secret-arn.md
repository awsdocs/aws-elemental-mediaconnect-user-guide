# Secret ARN<a name="hp-flow-decryption-secret-arn"></a>

Earlier, you created a secret in AWS Secrets Manager where you stored the encryption key\. This field indicates the ARN that was assigned to the secret that you created\.

From the drop\-down menu, choose the ARN of the secret that you created\. MediaConnect populates the drop\-down menu based on secrets that meet all of the following criteria:
+ The secret is associated with your account
+ You have at least read permission for the secret
+ MediaConnect is set up as a trusted entity for the secret

If a secret doesn't meet all three of those criteria, it won't appear in the drop\-down menu\. However, you can manually input the ARN of the secret even if it's not in the list\. MediaConnect can still use that secret to decrypt the content, as long as MediaConnect is set up as a trusted service for the role\.

## Learn more<a name="hp-flow-decryption-secret-arn-learn"></a>
+ [Data protection](https://docs.aws.amazon.com/mediaconnect/latest/ug/data-protection.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Setting up static key encryption](https://docs.aws.amazon.com/mediaconnect/latest/ug/encryption-static-key-set-up.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)