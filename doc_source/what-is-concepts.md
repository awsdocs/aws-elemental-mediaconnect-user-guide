# MediaConnect concepts and terminology<a name="what-is-concepts"></a>

ARN  
An [Amazon Resource Name](https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html), which is a unique identifier for any AWS resource\.

Availability Zone  
A specific location where AWS Cloud computing resources are hosted\. Availability Zones within an AWS Region are connected to each other with low latency, high throughput, and highly redundant networking\. In addition, they are physically separated and isolated from each other\. You can choose to create MediaConnect flows in different Availability Zones for redundancy\.

AWS Region  
A geographic area where one or more Availability Zones are located\. Each AWS Region is independent from the other Regions\. You can create MediaConnect flows in different Regions to distribute content to receivers in different locations around the world\. For more information about AWS Regions and their Availability Zones, see [AWS Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/)\.

CDI flow  
A MediaConnect flow that transports high\-quality content that has been lightly compressed using JPEG XS\. The content is demuxed into separate media streams for audio, video, or ancillary data\. Each CDI flow can use multiple media streams for the source and multiple media streams for each output\. MediaConnect uses AWS Cloud Digital Interface \(AWS CDI\) network technology to ingest content that adheres to the SMPTE 2110, part 22 transport standard\.

Contribution encoder  
An encoder that receives a live video feed and encodes the stream into a single, high\-quality mezzanine stream for transportation or further processing into an adaptive bitrate \(ABR\) stream\.

Distribution  
The result of creating outputs that point to MediaConnect flows in other AWS Regions, for the purpose of delivering content to different geographical locations\.

Entitlement  
A permission that is granted to allow an AWS account to access the content in a specific MediaConnect flow\. The content originator grants an entitlement to a specific AWS account \(the subscriber\)\. Once an entitlement is granted, the subscriber can create a flow using the originator's flow as the source\. You can only grant entitltements to transport stream flows\.

Flow  
A connection between one or more video sources and one or more outputs\. For each flow, you specify the transport protocol to use, encryption information, and details about the source\. MediaConnect returns an ingest endpoint where you can send your live video as a single unicast stream\. The service replicates and distributes the video to every output that you specify, whether inside or outside the AWS Cloud\. There are two types of flows: transport stream and JPEG XS\.

Media stream  
A single track or stream of media that contains video, audio, or ancillary data\. After you add a media stream to a flow, you can associate it with sources and outputs on that flow, as long as they use the CDI protocol or the ST 2110 JPEG XS protocol\. Each source or output can consist of one or many media streams\. 

Mezzanine stream  
A lightly compressed video stream that takes up less space than a full resolution uncompressed stream\. The quality of a mezzanine stream is high enough to use as a source for creating final encodes that are delivered to consumer devices\. 

Offering  
A discount that MediaConnect offers in exchange for a commitment to use a certain amount of outbound bandwidth each month\. When you purchase an offering, it becomes a reservation\. 

Originator account  
An AWS account that was used to create a flow with at least one entitlement\.

Output  
The destination where you want MediaConnect to send ingested video\. An output can have the same protocol or a different protocol from the source\.

Policy  
An [IAM policy](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html), which is used to manage access in AWS\. 

Protocol  
A set of rules used for file transmission\. MediaConnect provides protocol options \(such as Zixi, RTP, and RTP\-FEC\) that implement a quality of service \(QoS\) layer to enable the service to work with mezzanine\-quality live video\.

Receiver  
The recipient of a stream from MediaConnect\. A receiver is any entity, inside or outside of the AWS Cloud, that can receive RTP or Zixi streams\. This might be an affiliate, a cloud encoder, or another MediaConnect flow\.

Reservation  
A commitment to use a specific amount of outbound bandwidth each month over the course of a specified duration\. In return, you pay a discounted hourly rate for that bandwidth\. When you purchase an offering, it becomes a reservation\.

Replication  
The result of creating a flow with more than one output\. The source is replicated to produce multiple outputs\. Replication is useful when you want to distribute your video streams to multiple workflows within your own account or share your content with other AWS accounts\. 

Resource  
An entity in AWS that you can work with\. Each AWS resource is assigned an Amazon Resource Name \(ARN\) that acts as a unique identifier\. In MediaConnect, these are the resources and their ARN formats:   
+ Entitlement: `aws:mediaconnect:region:account-id:entitlement:resourceID:resourceName`
+ Flow: `aws:mediaconnect:region:account-id:flow:resourceID:resourceName`
+ Output: `aws:mediaconnect:region:account-id:output:resourceID:resourceName`
+ Source: `aws:mediaconnect:region:account-id:source:resourceID:resourceName`

Sharing  
Allowing another AWS account to access the content of your flow\. To share your content, you \(the originator\) grant an entitlement to another AWS account \(the subscriber\)\.

Source  
External video content that includes configuration information \(encryption and source type\) and a network address\. Each flow has at least one source\. A standard source comes from a source other than another MediaConnect flow, such as an on\-premises encoder\. An entitled source comes from an MediaConnect flow that is owned by another AWS account and has granted an entitlement to your account\.

Subscriber account  
An AWS account that been granted access to content from an AWS Elemental MediaConnect flow that is owned by another AWS account \(the originator account\)\. This permission is granted when the originator sets up an entitlement for the subscriber\. The entitlement permits the subscriber to create a flow that uses the originator's content as the source\.

Transport stream flow  
A MediaConnect flow that transports compressed content\. Audio, video, and ancillary data must be combined, or *muxed*, into a single stream\. The quality is high enough to use as a source for creating final encodes that are delivered to consumer devices\. You can add outputs to indicate where you want the content to be sent and how you want it transported\. You can also grant entitlements to allow another AWS account to access the content\.

VPC interface  
A connection between a flow and a virtual private cloud \(VPC\) that was created using the Amazon Virtual Private Cloud \(Amazon VPC\) service\.

Whitelisting  
Allowing a block of Classless Inter\-Domain Routing \(CIDR\) IP addresses to serve as a source to your MediaConnect flow\.