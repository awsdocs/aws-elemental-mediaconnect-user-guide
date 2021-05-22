# Use case: Contribution for CDI flows<a name="use-cases-cdi"></a>

With AWS Elemental MediaConnect and AWS Direct Connect, you can bridge your on\-premises live video network \(SDI, 2022\-6, or 2110\) to your  VPC live video network \(CDI\)\. MediaConnect uses the JPEG XS codec to reduce your AWS Direct Connect network bandwidth significantly\. MediaConnect supports SMPTE 2110 standard \(parts 22, 30, and 40\) for video, audio, and metadata transfer\. MediaConnect converts the content to CDI streams that are ready to be consumed by other services in the cloud, such as AWS Elemental MediaLive\. When your cloud VPC content is ready to be distributed back to on\-premises networks, you can use MediaConnect to convert the CDI streams back to the SMPTE 2110 standard \(parts 22, 30, and 40\) for transport\. 

For redundancy, when you transport content between your on\-premises configuration and the AWS Cloud, set up two connections in AWS Direct Connect\. Be sure to configure the AWS Elemental Live appliance with settings to match the MediaConnect flows\. For more information about configuring the appliance, see SMPTE 2110 [inputs](https://docs.aws.amazon.com/elemental-live/latest/ug/input-2110.html) and [outputs](https://docs.aws.amazon.com/elemental-live/latest/ug/output-2110.html) in the *AWS Elemental Live User Guide*\.

**Note**  
Because CDI outputs don't support inter\-Availability Zone transfers, use ST 2110 JPEG XS outputs if you want to send content to a different Availability Zone\. 

The following illustration shows a workflow that creates a bridge between your on\-premises live video infrastructure and the AWS Cloud\.

![\[This illustration shows an on-premises contribution encoder that uploads content to MediaConnect via AWS Direct Connect in the AWS Cloud. MediaConnect converts the content to CDI so that it can be consumed by other services for production and playout. The content is then sent back to MediaConnect where it is converted to JPEG XS and sent to an on-premises receiver via AWS Direct Connect.\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/)