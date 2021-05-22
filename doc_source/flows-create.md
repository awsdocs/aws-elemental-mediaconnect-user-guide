# Creating a flow<a name="flows-create"></a>

A flow is a connection between one or more sources and one or more outputs or entitlements\.

The method that you use to create a flow is dependent on the type of flow that you want to create and the type of content in the source:
+ [Transport stream flow with a standard source](flows-create-standard-source.md) – Uses content from any source that is not a VPC source or an entitled source\.
+ [Transport stream flow with an entitled source](flows-create-entitled-source.md) – Uses content that is owned by another AWS account that has granted an entitlement to your account\. 
+ [Transport stream flow with a VPC source](flows-create-vpc-source.md) – Uses compressed content that comes from a VPC that you configure\.
+ [CDI flow ](flows-create-cdi.md) – Uses uncompressed content that comes from a VPC that you configure\.

**Note**  
If you want to create a transport stream flow that uses redundant sources for failover, create the flow with one of the sources\. After the flow is created, [add the other source](source-adding.md)\. Because MediaConnect treats both sources as the primary source, it doesn't matter which one you specify when you first create the flow\. If your flow uses an entitled source, you can't add a second source\. For redundancy with CDI workflows, create two separate flows\. 