# Use Case: Selective Sharing<a name="use-cases-entitlements"></a>

Selective sharing, implemented as entitlements, allow an AWS account holder to share content with selected AWS account holders\. 

Take the example of a network that wants to share content \(Baseball\-Game\) with a local TV station\. A broadcaster \(the originator\) creates an entitlement on the Baseball\-Game, which allows access from the local TV station \(the subscriber\)\. 

With the entitlement in hand, the local TV station creates an AWS Elemental MediaConnect flow, using content from the Baseball\-Game\. That MediaConnect instance must be in the same AWS region used by the broadcaster\.

The following screen illustrates how you might share content with an AWS subscriber\. 

![\[Illustration of how content may be shared with another AWS subscriber.\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/)
