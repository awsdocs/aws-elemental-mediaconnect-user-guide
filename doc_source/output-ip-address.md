# Determining an output's IP address<a name="output-ip-address"></a>

For flows that use listener protocols \(such as Zixi pull or SRT listener\), the receiver requires the IP address of the output to establish a connection with the flow\.

**To determine an output's IP address**

1. On the **Flows** page, choose the name of the flow that you want to view\.

1. For specific instructions based on how content is sent to your output, choose one of the following tabs:

------
#### [ Public internet ]

   1. In the **Details** section, note the **Public outbound IP address**\. This is the IP address that the receiver needs\.

------
#### [ Private internet ]

   1. Choose the **Outputs** tab, and then locate the output that you want to view\.

   1. Under **Listener address** for that output, note the IP address\. This is the IP address that the receiver needs\.

------