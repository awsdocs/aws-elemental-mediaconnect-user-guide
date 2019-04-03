# Sources in AWS Elemental MediaConnect<a name="sources"></a>

Each AWS Elemental MediaConnect flow can have one source\. When you create a flow, you specify the source name, protocol, whitelist, and ingest port\. A source can be anything that provides a live video feed, such as the following:
+ An on\-premises encoder
+ Another AWS Elemental MediaConnect flow
+ An AWS Elemental MediaLive output
+ A playout system \(cloud\-based or on\-premises\)

**Topics**
+ [Updating the Source of a Flow](source-update.md)
+ [Confirming the Connection of a Flow to Its Source](source-confirm-connection.md)