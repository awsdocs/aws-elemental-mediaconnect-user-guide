# Data Protection in AWS Elemental MediaConnect<a name="data-protection"></a>

You can protect your data using tools that are provided by AWS\. AWS Elemental MediaConnect can decrypt your incoming video \(source\) and encrypt your outgoing video \(outputs\)\. You can store encryption information securely in AWS Secrets Manager, and then set up an IAM policy to allow AWS Elemental MediaConnect to communicate with Secrets Manager to obtain the encryption credentials as needed\.

**Note**  
Encryption is supported only for sources and outputs that use Zixi protocol\.

**Topics**
+ [Encryption in Transit](encryption-in-transit.md)
+ [Key Management in AWS Elemental MediaConnect](key-management.md)