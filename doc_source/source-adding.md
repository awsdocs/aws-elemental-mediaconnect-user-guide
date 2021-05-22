# Adding a source to an existing flow<a name="source-adding"></a>

For transport stream flows, you can add a second source for failover\. Both sources on the flow must  use the same protocol\. \(However, you can have one source that uses RTP and the other that uses RTP\-FEC\.\) For more information about source failover, see [Source failover](source-failover.md)\.

The method you use to add a second source to a flow is dependent on the type of source that you want to use:
+ [Standard source](source-adding-standard.md) – Uses content from any source that is not a VPC source or an entitled source\.
+ [VPC source](source-adding-vpc.md) – Uses content that comes from a VPC that you configure\.

MediaConnect doesn't support two sources on entitled flows or on CDI flows\. For redundancy with ST 2110 JPEG XS sources, you can specify two inbound VPC interfaces on an individual media stream\. For redundancy with CDI sources, create a second flow\.

From the MediaConnect console, you can view Amazon CloudWatch metrics to [monitor the source health](monitor-source-health.md) of an active flow\.