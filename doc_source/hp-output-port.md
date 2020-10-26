# Port<a name="hp-output-port"></a>

The port that you specify defines where you want MediaConnect to distribute the content\. Because MediaConnect requires a unique destination for each output in your flow, you must specify a unique port for each output\. 

**Note**  
Some protocols require additional ports for error correction\. For outputs that use these protocols, MediaConnect automatically reserves the additional ports\. The protocol defines specifically which ports must be reserved\. For example, some protocols require port\+2 and port\+4 for error correction\. If you specify port 5000 for the output, the service assigns ports 5000, 5002, and 5004\.
+ **For outputs that use the RIST protocol** – Use any port from 1024 to 65535, except 2077\. The RIST protocol requires one additional port for error correction\. To accommodate this requirement, MediaConnect reserves the port that is \+1 from the port that you specify\. For example, if you specify port 4000 for the output, the service assigns ports 4000 and 4001\.
+ **For outputs that use the RTP protocol** – Use any port from 1024 to 65535, except 2077\. The port that you specify is the only port needed for the output\.
+ **For outputs that use the RTP\-FEC protocol** – Use any port from 1024 to 65535, except 2077\. The RTP\-FEC protocol requires two additional ports for error correction\. To accommodate this requirement, MediaConnect reserves the ports that are \+2 and \+4 from the port that you specify\. For example, if you specify port 4000 for the output, the service assigns ports 4000, 4002, and 4004\.
+ **For outputs that use the Zixi pull protocol** – MediaConnect automatically assigns port 2077\.
+ **For outputs that use the Zixi push protocol** – Use any port from 1024 to 65535, except 2077\. The port that you specify is the only port needed for the output\.

## Learn more<a name="hp-output-port-learn"></a>

[Adding outputs to a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/outputs-add.html?icmpid=docs_mediaconnect_help_panel)

[Viewing a list of outputs of a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/outputs-view-list.html?icmpid=docs_mediaconnect_help_panel)

[Output destinations](https://docs.aws.amazon.com/mediaconnect/latest/ug/destinations.html?icmpid=docs_mediaconnect_help_panel)