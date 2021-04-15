# Source failover<a name="source-failover"></a>

Source failover is a setup that involves two redundant sources for a flow\. Additionally, MediaConnect must receive content from each source at the same time\. 

When you enable source failover and specify two sources for a flow, MediaConnect treats both sources as the primary\. Neither source is considered a backup of the other\. Sources used this way need to be *binary identical*, which means that they need to have originated from the same encoder\. Additionally, if the sources use RTP protocol, they must have RTP headers with aligned sequence numbers and they must also comply with the SMPTE\-2022\-7 standard\. 

**Note**  
SMPTE 2022\-7 is a standard developed by the Society of Motion Picture and Television Engineers \(SMPTE\) group\. The SMPTE 2022\-7 standard defines a method that replaces missing packets with packets in an identical, redundant stream\. This type of failover requires a small latency buffer in your workflow to allow time for MediaConnect to recover packets from the two streams\.

MediaConnect uses two types of failover method behind the scenes:
+ If the two sources are binary identical/SMPTE 2022\-7 compliant, MediaConnect uses content from both sources\. The service randomly selects one of the sources to start with\. If that source is missing a packet, the service pulls the missing packet from the other source\. For example, if the flow is using source A and packet 123 is missing, MediaConnect pulls in packet 123 from source B and continues using source A\. 
+ If the sources are **not** binary identical/SMPTE 2022\-7 compliant, MediaConnect randomly uses one of the sources to provide content for the flow\. If that source fails, the service switches to the other source\. The service continues switching back and forth between sources as needed\. This setup is sometimes referred to as *hot/hot*\.