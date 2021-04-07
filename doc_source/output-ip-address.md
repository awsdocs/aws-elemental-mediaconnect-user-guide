# Determining an output's IP address<a name="output-ip-address"></a>

For flows that use listener protocols \(such as Zixi pull or SRT listener\), the receiver requires the IP address of the output to establish a connection with the flow\.

**To determine an output's IP address**

1. On the **Flows** page, choose the name of the flow that you want to view\.

1. For specific instructions based on how content is sent to your output, choose one of the following tabs:

------
#### [ Public internet ]

   1. In the **Details** section, review the **Public outbound IP address**\. This is the IP address that the receiver needs\.

------
#### [ Private internet ]

   1. Choose the **Outputs** tab, and then choose the output that you want to view\.

   1. Choose **Details**, and then locate the **Output to VPC** value\. 

   1. Choose **Cancel**\.

   1. Choose the **VPC interfaces** tab\.

   1. In the VPC interface section, locate the **Network interface** value\.

   1. Open the Amazon EC2 console at [https://console\.aws\.amazon\.com/ec2/](https://console.aws.amazon.com/ec2/)\.

   1. In the navigation pane, choose **Network Interfaces**\.

   1. Select the network interface, and then choose **Details**\.

   1. Locate the IP address that the receiver needs\.

------