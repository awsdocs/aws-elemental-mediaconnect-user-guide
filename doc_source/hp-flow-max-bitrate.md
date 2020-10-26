# Maximum bitrate<a name="hp-flow-max-bitrate"></a>

We recommend that you specify a maximum expected bitrate \(in bits per second\) that is twice the actual bitrate\.

For contribution, MediaConnect is designed to work with mezzanine\-quality live video with a bitrate of up to 80 megabits per second \(Mb/s\)\.

For distribution, MediaConnect is designed to work with an aggregate output bandwidth of 400 Mb/s\. The aggregate output bandwidth is calculated by multiplying the bitrate of the source by the number of outputs\. For example, if your flow has a source with a bitrate of 80 Mb/s and 5 outputs, the aggregate output bandwidth is 400 Mb/s\. A flow that has a source with a bitrate of 20 Mb/s and sends content to 20 outputs also has an aggregate output bandwidth of 400 Mb/s\.

## Learn more<a name="hp-flow-max-bitrate-learn"></a>
+ [Creating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-create.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Updating a flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/flows-update.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Best practices](https://docs.aws.amazon.com/mediaconnect/latest/ug/best-practices.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)