# Media streams in AWS Elemental MediaConnect<a name="media-streams"></a>

A media stream is an essential component in a CDI flow, which you can use to ingest content into and transport content within the AWS Cloud via the SMPTE 2110, part 22 transport standard\. Each media stream represents a single track or stream of media that contains video, audio, or ancillary data\. 

You define a media stream as part of the flow\. Then, you can associate it with a source and multiple outputs on that flow\. The source and outputs must use the CDI protocol or the ST 2110 JPEG XS protocol, and can consist of one or many media streams\. 

The type of media stream that you create is based on the output that you are receiving from or sending to an on\-premises device, such as AWS Elemental Live\. 

**Note**  
You use media streams only for CDI flows that have ST 2110 with JPEG XS as their input and output protocol\. If you have configured your flows to use CDI as the input and output protocol, you don’t need media streams\.


****  

| AWS Elemental Live output | MediaConnect media stream type | 
| --- | --- | 
| SMPTE 2110\-20: Uncompressed video | \(Not supported\) | 
| SMPTE 2110\-22: Compressed video with JPEG XS | Video | 
| SMPTE 2110\-30: PCM audio | Audio | 
| SMPTE 2110\-31: Dolby audio \(AC3, EAC3\) | \(Not supported\) | 
| SMPTE 2110\-40: Ancillary data | Ancillary data | 

For illustrations of CDI workflows, see [Contribution for CDI flows](use-cases-cdi.md) and [CDI replication and monitoring](use-cases-cdi-replication-monitoring.md)\.

**Topics**
+ [Adding a media stream to a flow](media-stream-add.md)
+ [Updating a media stream](media-stream-update.md)
+ [Removing a media stream](media-stream-remove.md)