# Encryption in Transit<a name="encryption-in-transit"></a>

You can protect your content from unauthorized use through encryption\. If your source is encrypted, AWS Elemental MediaConnect can decrypt it\. In addition, the service can encrypt outputs\. You store your encryption keys in AWS Secrets Manager, and then give AWS Elemental MediaConnect permission to obtain the encryption keys from your Secrets Manager account\.

**Topics**
+ [Setting Up Encrypted Sources in AWS Elemental MediaConnect](encryption-in-transit-source.md)
+ [Setting Up Encrypted Outputs in AWS Elemental MediaConnect](encryption-in-transit-output.md)