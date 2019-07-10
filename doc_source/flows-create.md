# Creating a Flow<a name="flows-create"></a>

A flow consists of one source, a name, and an Availability Zone\. The ability to choose an Availability Zone allows you to create multiple flows within an AWS Region for redundancy\. After you create a flow, you can add up to 20 outputs and up to 50 entitlements\.

**Important**  
If the source of your flow requires encryption, [set up encryption](encryption-static-key-set-up.md) before you begin this procedure\. 

**To create a flow \(console\)**

1. Open the MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. On the **Flows** page, choose **Create flow**\.

1. In the **Details** section, for **Name**, specify a name for your flow\. This name will become part of the ARN for this flow\.
**Note**  
AWS Elemental MediaConnect allows you to create multiple flows with the same name\. However, we encourage you to use unique flow names within an AWS Region to help with organization\. After you create a flow, you can't change the name\.

1. For **Availability Zone**, choose an Availability Zone for your flow\. Use this option when you are setting up redundant flows\. Otherwise, you can leave this as **Any** and the service will randomly assign an Availability Zone within the current AWS Region\.

1. Determine which type of source you are using:
   + A standard source with RTP or RTP\-FEC protocol
   + A standard source with Zixi push protocol
   + An entitled source \(a flow that is owned by another AWS account and has granted an entitlement to your account\)

1. For specific instructions based on your source type and protocol, choose one of the following tabs:

------
#### [ Standard source with RTP or RTP\-FEC ]

   1. In the **Source** section, for **Source type**, choose **Standard source**\.

   1. For **Name**, specify a name for your source\. This value is an identifier that is visible only on the AWS Elemental MediaConnect console\. It is not visible to anyone outside of the current AWS account\.

   1. For **Protocol**, choose RTP or RTP\-FEC\. 

   1. For **Ingest port**, specify the port that the flow will listen on for incoming content\.

   1. For **Whitelist CIDR**, specify a range of IP addresses that are allowed to contribute content to your source\. Format the IP addresses as a Classless Inter\-Domain Routing \(CIDR\) block, for example, 10\.24\.34\.0/23\. For more information about CIDR notation, see [RFC 4632](https://tools.ietf.org/html/rfc4632)\.

   1. For **Maximum bitrate**, specify the maximum expected bitrate \(in bits per second\) for the flow\. We recommend that you specify a value that is twice the actual bitrate\.

------
#### [ Standard source with Zixi push ]

   1. In the **Source** section, for **Source type**, choose **Standard source**\.

   1. For **Name**, specify a name for your source\. This value is an identifier that is visible only on the AWS Elemental MediaConnect console\. It is not visible to anyone outside of the current AWS account\.

   1. For **Protocol**, choose **Zixi push**\. 

      AWS Elemental MediaConnect populates the value of the ingest port\.

   1. For **Whitelist CIDR**, specify a range of IP addresses that are allowed to contribute content to your source\. Format the IP addresses as a Classless Inter\-Domain Routing \(CIDR\) block, for example, 10\.24\.34\.0/23\. For more information about CIDR notation, see [RFC 4632](https://tools.ietf.org/html/rfc4632)\.

   1. For **Stream ID**, specify the stream ID set in the Zixi feeder\.
**Important**  
If you leave this field blank, the service uses the source name as the stream ID\. Because the stream ID must match the value set in the Zixi feeder, you need to specify the stream ID if it is not exactly the same as the source name\.

   1. For **Maximum latency**, specify the size of the buffer \(delay\) that you want the service to maintain\. A higher latency value means a longer delay in transmitting the stream, but more room for error correction\. A lower latency value means a shorter delay, but less room for error correction\. You can choose a value between 0 and 60,000 ms\. If you keep this field blank, the service uses the default value of 6,000 ms\. 

   1. If the source is encrypted, choose **Enable** in the **Decryption** section and do the following:

      1. For **Decryption type**, choose **Static key**\.

      1. For **Role ARN**, specify the ARN of the role that you created when you [set up encryption](encryption-static-key-set-up.md#encryption-static-key-set-up-create-iam-role)\.

      1. For **Secret ARN**, specify the ARN that AWS Secrets Manager assigned when you [created the secret to store the encryption key](encryption-static-key-set-up.md#encryption-static-key-set-up-store-key)\.

      1. For **Decryption algorithm**, choose the type of encryption that was used to encrypt the source\.

------
#### [ Entitled source ]

   1. In the **Source** section, for **Source type** choose **Entitled source**\.

   1. For **Entitlement ARN**, choose the appropriate entitlement\. This list includes all entitlements that have been granted to you\.
**Tip**  
You can click in this field and start entering the entitlement name\. AWS Elemental MediaConnect will filter the list to include only entitlements with a name that matches what you enter\.

------

1. At the bottom of the page, choose **Create flow**\.
**Note**  
The flow doesn't start automatically\. You must [start the flow](flows-start.md) manually\.

1. [Add outputs](outputs-add.md) to specify where you want AWS Elemental MediaConnect to send the content, or [grant entitlements](entitlements-grant.md) to allow users of other AWS accounts to subscribe to your content\.

**To create a flow \(AWS CLI\)**

1. Create a JSON file that contains the details of the flow that you want to create\.

   The following example shows the structure for the contents of the file:

   ```
   {
     "Name": "AwardsShow",
     "Outputs": [
       {
         "Destination": "198.51.100.5",
         "Description": "RTP output",
         "Name": "RTPOutput",
         "Protocol": "rtp",
         "Port": 5020
       }
     ],
     "Source": {
       "Name": "AwardsShowSource",
       "Protocol": "rtp-fec",
       "WhitelistCidr": "10.24.34.0/23"
     }
   }
   ```

1. In the AWS CLI, use the `create-flow` command:

   ```
   aws mediaconnect create-flow --cli-input-json file://rtp.json --region us-east-1 --profile PMprofile
   ```

   The following example shows the return value:

   ```
   {
     "Flow": {
       "EgressIp": "203.0.113.0",
       "AvailabilityZone": "us-east-1d",
       "Name": "AwardsShow",
       "Status": "STANDBY",
       "FlowArn": "arn:aws:mediaconnect:us-east-1:111122223333:flow:1-23aBC45dEF67hiJ8-12AbC34DE5fG:AwardsShow",
       "Source": {
               "SourceArn": "arn:aws:mediaconnect:us-east-1:111122223333:source:3-4aBC56dEF78hiJ90-4de5fG6Hi78Jk:AwardsShowSource",                                       
               "Name": "AwardsShowSource",
               "IngestPort": 5000,
               "WhitelistCidr": "10.24.34.0/23",
               "IngestIp": "198.51.100.15",
               "Transport": {
                   "Protocol": "rtp-fec",
                   "MaxBitrate": 80000000
               }
           },
           "Entitlements": [],
           "Outputs": [
               {
                   "Port": 5020,
                   "Name": "AwardsShowOutput",
                   "OutputArn": "arn:aws:mediaconnect:us-east-1:111122223333:output:2-3aBC45dEF67hiJ89-c34de5fG678h:AwardsShowOutput",                                          
                   "Description": "RTP-FEC Output",
                   "Destination": "198.51.100.5",
                   "Transport": {
                       "Protocol": "rtp",
                       "SmoothingLatency": 0
                   }
               }
           ]
       }
   }
   ```