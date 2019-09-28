# Use Case: Uploads<a name="use-cases-uploads"></a>

You can upload content from your on-premises contribution encoder to the AWS cloud through AWS Elemental MediaConnect. 

The following diagram illustrates an on\-premises contribution encoder that uploads content to AWS Elemental MediaConnect in the AWS Cloud\. The output points to an AWS Elemental MediaLive channel\.

![\[This illustration shows the flow from an on-premises contribution encoder through AWS Elemental MediaConnect to an AWS Elemental MediaLive channel.\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/)

For redundancy, you have two options:

* Configure uploads from two on-premises encoders to a single AWS Elemental MediaLive system\. 
* Set up primary and backup on-premises contribution encoders\. Each encoder uploads content to different MediaConnect servers\. Each MediaConnect server redirects content to the same AWS MediaLive cloud encoder, as shown in the following diagram\. 

![\[This diagram shows two on-premises contribution encoders, a primary and a backup, that uploads content to AWS Elemental MediaConnect in the AWS Cloud. Both outputs are directed to a single AWS Elemental MediaLive encoder.\]](http://docs.aws.amazon.com/mediaconnect/latest/ug/)
