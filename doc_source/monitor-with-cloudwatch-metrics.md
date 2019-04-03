# AWS Elemental MediaConnect Metrics<a name="monitor-with-cloudwatch-metrics"></a>

AWS Elemental MediaConnect sends metrics to CloudWatch\. For details about each metric, see the tables in this section\.

**Note**  
Metrics tracked by AWS Elemental MediaConnect adhere to the standard as defined by the TR 101 290 spec\.

**Topics**
+ [Network Metrics](#monitor-with-cloudwatch-metrics-network)
+ [TR 101 290 Priority 1 Metrics](#monitor-with-cloudwatch-metrics-p1)
+ [TR 101 290 Priority 2 Metrics](#monitor-with-cloudwatch-metrics-p2)
+ [Source Metrics](#monitor-with-cloudwatch-metrics-source)

## Network Metrics<a name="monitor-with-cloudwatch-metrics-network"></a>

The following table lists network metrics that AWS Elemental MediaConnect sends to CloudWatch\.


| Metric | Description | 
| --- | --- | 
| ARQRecovered |  The number of dropped packets that were recovered by automatic repeat request \(ARQ\)\. This metric applies only to sources that use Zixi protocol\. Units: Count Valid dimensions:  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| ARQRequests |  The number of retransmitted packets that were requested through automatic repeat request \(ARQ\) and received\. This metric applies only to sources that use the Zixi protocol\. Units: Count Valid dimensions:  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| ConnectedOutputs |  The number of outputs that are currently connected\. This metric applies only to outputs that use Zixi protocol\.  Units: Count Valid dimensions:  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| FECPackets |  The number of packets that were transmitted using forward error correction \(FEC\) and received\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| FECRecovered |  The number of packets that were transmitted using forward error correction \(FEC\), lost during transit, and recovered\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| NotRecoveredPackets |  The number of packets that were lost during transit and never recovered\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| OverflowPackets |  The number of packets that were lost in transit because the video required more buffer than was available\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| PacketLossPercent |  The percentage of packets that were lost during transit, even if they were recovered\. Units: Percent Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| RecoveredPackets |  The number of packets that were lost during transit, but recovered\. Units: Counter Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| RoundTripTime |  The amount of time it takes for the source to send a signal and receive an acknowledgement from AWS Elemental MediaConnect\. This metric applies only to sources that use Zixi protocol\. Units: Milliseconds Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 

## TR 101 290 Priority 1 Metrics<a name="monitor-with-cloudwatch-metrics-p1"></a>

The following table lists TR 101 290 Priority 1 metrics that AWS Elemental MediaConnect sends to CloudWatch\.


| Metric | Description | 
| --- | --- | 
| ContinuityCounter |  The number of times that a continuity error occurred\. This error indicates an incorrect packet order or lost packets\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| PATError |  The number of times that a program association table \(PAT\) error occurred\. This error indicates that the PAT is missing\. The PAT lists the programs that are available in a transport stream and points to the program map tables \(PMTs\)\. The decoder needs the PAT to do its job\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| PIDError |  The number of times that a packet identifier \(PID\) error occurred\. This error indicates that a PID is missing its associated data stream\. The PIDs are identifiers that provide the location of the video, audio, and data streams\. This error can occur after the transport stream \(TS\) has been multiplexed and then remultiplexed\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| PMTError |  The number of times that a program map table \(PMT\) error occurred\. This error happens when the PMT is not received at least every 500 milliseconds \(ms\)\. Each PMT contains a list of PIDs, which help decoders reassemble data\. The decoder needs the PMTs to do its job\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| TSByteError |  The number of times that a transport stream \(TS\) byte error occurred\. This error indicates that the sync byte did not appear after the prescribed number of bytes\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| TSSyncLoss |  The number of times that a TS sync loss error occurred\. This error happens after two or more consecutive TS byte errors\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 

## TR 101 290 Priority 2 Metrics<a name="monitor-with-cloudwatch-metrics-p2"></a>

The following table lists TR 101 290 Priority 2 metrics that AWS Elemental MediaConnect sends to CloudWatch\.


| Metric | Description | 
| --- | --- | 
| CATError |  The number of times that a conditional access table \(CAT\) error occurred\. This error indicates that the CAT is not present\. The CAT tells the integrated receiver decoder \(IRD\) where to find management messages for the conditional access \(CA\) systems that are in use\. Units: Count Valid dimensions:  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| CRCError |  The number of times that a cyclic redundancy check \(CRC\) error occurred\. This error happens when a CRC determines that data is corrupted\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| PCRAccuracyError |  The number of times that a program clock register \(PCR\) accuracy error occurred\. This error happens when the value of the transmitted PCR differs from what is expected by more than 500 nanoseconds \(ns\)\. When a stream is encoded, the encoder assigns periodic PCR values of the encoder's program clock\. The decoder relies on these values to ensure that the stream is kept in sync\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| PCRError |  The number of times that a PCR error occurred\. This error happens when PCR values are not sent frequently enough\. The service relies on consistent, frequent PCRs to reset the local 27 MHz system clock\. Although the error occurs when the interval exceeds 100 milliseconds \(ms\), best practices dictate that PCRs should be received at least every 40 ms\.  Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| PTSError |  The number of times that a presentation timestamp \(PTS\) error occurred\. This error happens when a presentation timestamp \(PTS\) is not received at least every 700 ms\. This can occur if the PTS is sent less frequently or not at all\. The most common cause of this error is when the transport stream is scrambled\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 
| TransportError |  The number of times that a primary transport error occurred\. This error indicates that the TS packet is unusable\. When this error occurs, ignore all other TR 101 290 errors for this packet\. Units: Count Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 

## Source Metrics<a name="monitor-with-cloudwatch-metrics-source"></a>

The following table lists source metrics that AWS Elemental MediaConnect sends to CloudWatch\.


| Metric | Description | 
| --- | --- | 
| SourceBitRate |  The bitrate of the incoming \(source\) video\. Units: bits per second \(b/s\) Valid dimensions: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/monitor-with-cloudwatch-metrics.html)  | 