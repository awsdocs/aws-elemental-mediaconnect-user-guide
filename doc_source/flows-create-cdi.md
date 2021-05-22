# Creating a CDI flow<a name="flows-create-cdi"></a>

A CDI flow transports high\-quality uncompressed or lightly compressed content into and out of the AWS Cloud\. You can configure a CDI flow to use JPEG XS to transport lightly compressed content\. The content is demuxed into separate media streams for audio, video, or ancillary data\. Each CDI flow can use multiple media streams for the source and multiple media streams for each output\. MediaConnect uses AWS Cloud Digital Interface \(AWS CDI\) network technology to transport content that adheres to the SMPTE 2110, part 22 transport standard\. 

CDI flows only support sources from a virtual private cloud \(VPC\) that you set up using Amazon VPC\. You set up your VPC and then create a flow that has an interface to that VPC\. 

MediaConnect doesn't support two sources on CDI flows\. For redundancy with ST 2110 JPEG XS sources, you can specify two inbound VPC interfaces on an individual media stream\. For redundancy with CDI sources, create a second flow\. 

**Important**  
Before you begin this procedure, make sure that the following steps have been completed:  
Review the suggested workflow shown in [Contribution for CDI flows](use-cases-cdi.md)\.
In Amazon VPC, set up your VPC and associated security groups\. For more information about VPCs, see the [Amazon VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/)\. For information about configuring security groups to work with your VPC interface, see [Security group considerations](vpc-interface-security-groups.md)\.
In IAM, [set up MediaConnect as a trusted service](security-iam-trusted-entity.md)\.

**To create a CDI flow \(console\)**

1. Open the MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. On the **Flows** page, choose **Create flow**\.

1. In the **Details** section, for **Name**, specify a name for your flow\. This name will become part of the ARN for this flow\.
**Note**  
MediaConnect allows you to create multiple flows with the same name\. However, we encourage you to use unique flow names within an AWS Region to help with organization\. After you create a flow, you can't change the name\.

1. For **Availability Zone**, choose the Availability Zone where your VPC subnet resides\. 

1. In the **Source** section, for **Source type**, choose **VPC source**\.

1. For **Name**, specify a name for your source\. This value is an identifier that is visible only on the MediaConnect console\. 

1. Skip to the **VPC interface** section\.

1. For each VPC that you want to connect to the flow, do the following:

   1. Choose **Add VPC interface**\.

   1. For **Name**, specify a name for your VPC interface\. The name of the VPC interface must be unique within the flow\.

   1. For **Type**, choose the type of network adapter that you want MediaConnect to use on this interface\. If you want to use this interface for a CDI source or output, you must choose **EFA** as the type\.

   1. For **Role ARN**, specify the Amazon Resource Name \(ARN\) of the role that you created when you set up MediaConnect as a trusted service\.

   1. For **VPC**, choose the ID of the VPC that you want to use\.
**Note**  
If you don't see the VPC that you want in the list, verify that the VPC has been set up in Amazon Virtual Private Cloud and that you have IAM permissions to view the VPC\.

   1. For **Subnet**, choose the VPC subnet that you want MediaConnect to use to set up your VPC configuration\. You must choose at least one and can choose as many as you want\.

   1. For **Security groups**, specify the VPC security groups that you want MediaConnect to use to set up your VPC configuration\. You must choose at least one security group\.

1. For each media stream that you want to add to the flow, do the following:

   1. In the **Media streams** section, choose **Add media stream**\.

   1. In the **Name** field, specify a descriptive name that will help you distinguish this media stream from others in the flow\.

   1. For **Description**, specify a descripton that will help you remember the use of this media stream\. 

   1. For **Stream ID**, specify a unique identifier for the media stream\. 

      If the source or any of the outputs uses the CDI protocol, specify the value that is expected by the production and playout systems\.

      If the source and all outputs use the ST 2110 JPEG XS protocol, specify a value that is unique to that of other media streams within the flow\.

   1. Choose **Advanced options** to display the additional options based on your stream type\.

   1. For specific instructions on the advanced options based on your stream type, choose one of the following tabs:

------
#### [ Audio ]

      1. For **Stream type**, choose **Audio**\. 

      1. For **Media clock rate**, specify the sample rate for the stream\. This value is measured in Hz\.

      1. For **Language**, specify the language of the audio\. This value should be in a format that the receiver recognizes\. 

      1. For **Channel order**, specify the format of the audio channel\. 

      1. Choose **Add media stream**\. 

------
#### [ Video ]

      1. For **Stream type**, choose **Video**\. 

         For many fields, MediaConnect provides a default value that represents the recommended setting\. Change the default value if needed\. 

      1. **Media clock rate** is the sample rate for the stream, and is set to 90000\. This value is measured in Hz\.

      1. For **Video format**, specify the resolution of the video\. 

      1. For **Exact framerate**, specify the frame rate of the video\. This value should be represented in frames per second\.

      1. For **Colorimetry**, specify the format that was used for the representation of color in the video\. 

      1. For **Scan mode**, specify the method that was used to scan the incoming video\. 
         + Choose **Interlace** if the incoming video is interlaced \(for example, 480i or 1080i\)\.
         + Choose **Progressive** if the incoming video is progressive \(for example, 720p or 1080p\)\.
         + Choose **Progressive segmented frame** if the incoming video is PSF \(for example, 1080psf\)\.

      1. For **TCS**, specify the transfer characteristic system \(TCS\) that was used in the video\. 

      1. For **Range**, specify the encoding range of the video\. 

      1. For **PAR**, specify the pixel access ratio \(PAR\) of the video\. 

      1. Choose **Add media stream**\. 

------
#### [ Ancillary data ]

      1. For **Stream type**, choose **Ancillary data**\. 

      1. **Media clock rate** is the sample rate for the stream, and is set to 90000\. This value is measured in Hz\.

      1. Choose **Add media stream**\. 

------

1. Scroll back up to the **Sources** section\.

1. Determine which protocol your source uses\.

1. For specific instructions based on your protocol, choose one of the following tabs:

------
#### [ CDI ]

   1. For **Protocol**, choose **CDI**\. 

   1. For **Description**, enter a description that will remind you later where this source is from\. This might be the company name or notes about the setup\.

   1. For **Inbound port**, specify the port that the flow will listen on for incoming content\. This value can be anything from 1024 to 65535, with the exception of 2077 and 2088 \(those ports are reserved for other protocols\)\.

   1. For **VPC interface**, choose the name of the VPC interface that you want to use as the source\.

   1. For each media stream that you want to use as part of the source, do the following\.

      1. For **Media stream name**, choose the name of the media stream\.

      1. For **Encoding name**, accept the default value\.
         + For ancillary data streams, the encoding name is **smpte291**\.
         + For audio streams, the encoding name is **pcm**\.
         + For video, the encoding name is **raw**\.

------
#### [ ST 2110 JPEG XS ]

   1. For **Protocol**, choose **ST 2110 JPEG XS**\. 

   1. For **Description**, enter a description that will remind you later where this source is from\. This might be the company name or notes about the setup\.

   1. For **Max sync buffer**, specify the size of the buffer that you want MediaConnect to use to sync incoming source data\. This value is measured in milliseconds \(ms\)\.

   1. For **VPC interface name 1**, choose one of the VPC interfaces that you want to use as a source\.

   1. For **VPC interface name 2**, choose a second VPC interface that you want to use as a source\. There is no priority between VPC interfaces 1 and 2\.

   1. For each media stream that you want to use as part of the source, do the following\.

      1. For **Media stream name**, choose the name of the media stream\.

      1. For **Encoding name**, accept the default value\.
         + For ancillary data streams, the encoding name is **smpte291**\.
         + For audio streams, the encoding name is **pcm**\.
         + For video, the encoding name is **jxsv**\.

      1. For **Inbound port**, specify the port that the flow will listen on for incoming content\. This value can be anything from 1024 to 65535, with the exception of 2077 and 2088 \(those ports are reserved for other protocols\)\.

------

1. At the bottom of the page, choose **Create flow**\.
**Note**  
The flow doesn't start automatically\. You must [start the flow](flows-start.md) manually\.

1. [Add outputs](outputs-add-vpc.md) to specify where you want MediaConnect to send the content\.