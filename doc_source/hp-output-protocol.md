# Protocol<a name="hp-output-protocol"></a>

The protocol that you choose for the output represents the protocol used in the stream that is distributed from your flow\. If your output is sent to an on\-premises encoder, use a protocol that matches what the encoder can receive\. If you set up multiple flows for distribution, we recommend that you use Zixi as the protocol to send content between flows\. 

## RIST<a name="hp-output-protocol-rist"></a>

Reliable Internet Stream Transport \(RIST\) is a highly available, low\-latency protocol that is suitable for long\-distance applications\. MediaConnect doesn't support encryption for sources or outputs that use the RIST protocol\.

## RTP or RTP\-FEC<a name="hp-output-protocol-rtp"></a>

Real\-Time Transport Protocol with Forward Error Correction \(RTP\-FEC\) has wide applicability and forward error correction \(FEC\) to self\-heal any corruption and packet loss\. Using this protocol takes more bandwidth than RTP without FEC\. MediaConnect doesn't support encryption for sources or outputs that use the RTP\-FEC protocol\.

Real\-Time Transport Protocol \(RTP\) has wide applicability and takes less bandwidth than RTP\-FEC\. MediaConnect doesn't support encryption for sources or outputs that use the RTP protocol\.

## Zixi pull or push<a name="hp-output-protocol-zixi"></a>

Zixi is a highly available protocol suitable for most applications, especially use cases that involve longer distances\. MediaConnect supports two Zixi protocol options:
+ **Zixi pull** uses the Zixi protocol to send content to a receiver or an integrated receiver decoder \(IRD\) that is behind a firewall\. Additionally, you can use this option when you need network address translation \(NAT\) to route the traffic from MediaConnect to the receiver\.
+ **Zixi push** uses the Zixi protocol to send content to a receiver that has a static, publicly addressable IP address\. Use this option when the receiver is not behind a firewall or NAT\-based router\.

## Learn more<a name="hp-output-protocol-learn"></a>

[Adding outputs to a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/outputs-add.html?icmpid=docs_mediaconnect_help_panel)

[Viewing a list of outputs of a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/outputs-view-list.html?icmpid=docs_mediaconnect_help_panel)

[Protocols](https://docs.aws.amazon.com/mediaconnect/latest/ug/protocols.html?icmpid=docs_mediaconnect_help_panel)