# Decryption<a name="hp-flow-decryption"></a>

If the source is encrypted, MediaConnect must decrypt it to distribute the content to outputs\. Before you complete this section, store the encryption key in AWS Secrets Manager and make note of the following information:
+ The ARN of the IAM role that you created during [setup](https://docs.aws.amazon.com/mediaconnect/latest/ug/encryption-static-key-set-up.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow) \(when you set up MediaConnect as a trusted entity\)
+ The ARN that was assigned to the secret that you created in Secrets Manager to store the encryption key

## Learn more<a name="hp-flow-decryption-learn"></a>
+ [Data protection](https://docs.aws.amazon.com/mediaconnect/latest/ug/data-protection.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Setting up static key encryption](https://docs.aws.amazon.com/mediaconnect/latest/ug/encryption-static-key-set-up.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)