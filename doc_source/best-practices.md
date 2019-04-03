# Best Practices for AWS Elemental MediaConnect<a name="best-practices"></a>

Follow these best practices for optimizing performance when working with AWS Elemental MediaConnect\.

For contribution, AWS Elemental MediaConnect is designed to work with mezzanine quality live video with a bitrate of up to 80 megabits per second \(Mb/s\)\. 

For distribution, AWS Elemental MediaConnect is designed to work with an aggregate output bandwidth of 400 Mb/s\. The *aggregate output bandwidth* is calculated by multiplying the bitrate of the source by the number of outputs\. For example, if your flow has a source with a bitrate of 80 Mb/s and 5 outputs, the aggregate output bandwidth is 400 Mb/s\. A flow that has a source with a bitrate of 20 Mb/s and sends content to 20 outputs also has an aggregate output bandwidth of 400 Mb/s\.