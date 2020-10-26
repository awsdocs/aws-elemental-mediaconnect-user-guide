# Ingest port<a name="hp-flow-ingest-port"></a>

The ingest port is the port that the flow will be listening on for incoming content\. The port that you use depends on the source protocol\.
+ **For flows that use the RIST protocol** – Use any port from 1024 to 65535, except 2088\. The RIST protocol requires one additional port for error correction\. To accommodate this requirement, MediaConnect reserves the port that is \+1 from the port that you specify\. For example, if you specify port 4000 for the output, the service assigns ports 4000 and 4001\.
+ **For flows that use the RTP or RTP\-FEC protocol** – Use any port from 1024 to 65535, except 2088\. The RTP\-FEC protocol requires two additional ports for error correction\. To accommodate this requirement, MediaConnect reserves the ports that are \+2 and \+4 from the port that you specify\. For example, if you specify port 4000 for the output, the service assigns ports 4000, 4002, and 4004\.
+ **For flows that use the Zixi pull protocol** – MediaConnect automatically assigns port 2088\.

## Learn more<a name="hp-flow-ingest-port-learn"></a>
+ [Creating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Updating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-update.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Protocols in MediaConnect](https://docs.aws.amazon.com/mediaconnect/latest/ug/protocols.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)