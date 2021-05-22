# Entitlements in AWS Elemental MediaConnect<a name="entitlements"></a>

Content originators can grant entitlements to share their content with other AWS accounts \(subscriber accounts\)\. Subscribers can then set up their own AWS Elemental MediaConnect flows using the originator's flow as their source\. The following illustration shows this process\.

**Note**  
You can only grant entitlements on transport stream flows\. MediaConnect doesn't support entitlements on CDI flows\.

![\[This illustration shows how content originators can grant entitlements to share their content with other AWS accounts (subscriber accounts). Subscribers can then set up their own MediaConnect flows using the originator's flow as their source.\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/)

**Topics**
+ [Sharing content with other AWS accounts](entitlements-originator.md)
+ [Subscribing to content provided by another AWS account](entitlements-subscriber.md)