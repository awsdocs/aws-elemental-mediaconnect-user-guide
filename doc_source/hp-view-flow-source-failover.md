# Source failover<a name="hp-view-flow-source-failover"></a>

Source failover is a configuration that involves two redundant sources for a flow\. You specify two sources for the flow, both of which come from the same encoder\. MediaConnect treats both sources as the primary, so you don't need to specify one as primary and the other as backup\. MediaConnect must receive content from the two sources at the same time\.

After you enable source failover, you set the recovery window, which is the size of the buffer \(delay\) that you want MediaConnect to maintain\. A larger recovery window means a longer delay in transmitting the stream, but more room for error correction\. A smaller recovery window means a shorter delay, but less room for error correction\. You can choose a value from 100–15000 ms\. If you keep this field blank, the service uses the default value of 200 ms\.

## Learn more<a name="hp-view-flow-source-failover-learn"></a>
+ [Source failover](https://docs.aws.amazon.com/mediaconnect/latest/ug/source-failover.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)
+ [Adding a second source to an existing flow](https://docs.aws.amazon.com/mediaconnect/latest/ug/source-adding-second.html?icmpid=docs_mediaconnect_help_panel_hp-create-flow)