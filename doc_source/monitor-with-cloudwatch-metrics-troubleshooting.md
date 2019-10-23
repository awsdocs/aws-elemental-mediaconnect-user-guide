# Using Metrics to Troubleshoot<a name="monitor-with-cloudwatch-metrics-troubleshooting"></a>

You can monitor the health of your stream by reviewing the metrics that AWS Elemental MediaConnect sends to CloudWatch\. In particular, if you encounter a problem on your MediaConnect flow, these metrics can help you isolate the problem\. The specific metrics to watch depend on the protocol that your source uses\. Review the lists below, which are sorted by source protocol\.

**Topics**
+ [Metrics to Watch if Your Source Uses the RTP Protocol](#monitor-with-cloudwatch-metrics-troubleshooting-rtp)
+ [Metrics to Watch if Your Source Uses the RTP\-FEC Protocol](#monitor-with-cloudwatch-metrics-troubleshooting-rtp-fec)
+ [Metrics to Watch if Your Source Uses the RIST Protocol](#monitor-with-cloudwatch-metrics-troubleshooting-rist)
+ [Metrics to Watch if Your Source Uses the Zixi Push Protocol](#monitor-with-cloudwatch-metrics-troubleshooting-zixi-push)
+ [Metrics to Watch if Your Source Comes From an Entitlement](#monitor-with-cloudwatch-metrics-troubleshooting-entitlement)

## Metrics to Watch if Your Source Uses the RTP Protocol<a name="monitor-with-cloudwatch-metrics-troubleshooting-rtp"></a>

If the protocol of your source is RTP, watch the metrics below to evaluate the health of your source\.
+ `DroppedPackets`
+ `OverflowPackets`
+ `PacketLossPercent`
+ `RoundTripTime`
+ `TotalPackets`

## Metrics to Watch if Your Source Uses the RTP\-FEC Protocol<a name="monitor-with-cloudwatch-metrics-troubleshooting-rtp-fec"></a>

If the protocol of your source is RTP\-FEC, watch the metrics below to evaluate the health of your source\.
+ `DroppedPackets`
+ `FECPackets`
+ `FECRecovered`
+ `NotRecoveredPackets`
+ `OverflowPackets`
+ `PacketLossPercent`
+ `RecoveredPackets`
+ `RoundTripTime`
+ `TotalPackets`

## Metrics to Watch if Your Source Uses the RIST Protocol<a name="monitor-with-cloudwatch-metrics-troubleshooting-rist"></a>

If the protocol of your source is RIST, watch the metrics below to evaluate the health of your source\.
+ `ARQRecovered`
+ `ARQRequests`
+ `DroppedPackets`
+ `NotRecoveredPackets`
+ `OverflowPackets`
+ `PacketLossPercent`
+ `RecoveredPackets`
+ `RoundTripTime`
+ `TotalPackets`

## Metrics to Watch if Your Source Uses the Zixi Push Protocol<a name="monitor-with-cloudwatch-metrics-troubleshooting-zixi-push"></a>

If the protocol of your source is Zixi push, watch the metrics below to evaluate the health of your source\.
+ `ARQRecovered`
+ `ARQRequests`
+ `DroppedPackets`
+ `FECPackets`
+ `FECRecovered`
+ `NotRecoveredPackets`
+ `OverflowPackets`
+ `PacketLossPercent`
+ `RecoveredPackets`
+ `RoundTripTime`
+ `TotalPackets`

## Metrics to Watch if Your Source Comes From an Entitlement<a name="monitor-with-cloudwatch-metrics-troubleshooting-entitlement"></a>

If your source comes from an entitlement that was granted to your account by another AWS account, watch the metrics below to evaluate the health of your source\.
+ `ARQRecovered`
+ `ARQRequests`
+ `DroppedPackets`
+ `FECPackets`
+ `FECRecovered`
+ `NotRecoveredPackets`
+ `OverflowPackets`
+ `PacketLossPercent`
+ `RecoveredPackets`
+ `RoundTripTime`
+ `TotalPackets`