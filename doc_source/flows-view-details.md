# Viewing the Details of a Flow<a name="flows-view-details"></a>

You can view a flow's details, such as ARN, Availability Zone, status, source, entitlements, and outputs\.

**To view the details of a flow \(console\)**

1. Open the AWS Elemental MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. On the **Flows** page, choose the name of the flow that you want to view\.

   The details page for that flow appears\. This page is divided into three tabs:
   + The **Source** tab shows details about the source for this flow, including an indication of whether the flow is connected to the source\. 
   + The **Source** tab shows details about the source for this flow, including an indication of whether the flow is connected to the source\. 
   + The **Entitlements** tab shows any entitlements that you have granted on this flow\.
   + The **Outputs** tab shows details for each output that you created for this flow\.

**To view the details of a flow \(AWS CLI\)**
+ In the AWS CLI, use the `describe-flow` command:

  ```
  aws mediaconnect describe-flow --flow-arn "arn:aws:mediaconnect:us-east-1:111122223333:flow:1-23aBC45dEF67hiJ8-12AbC34DE5fG:BasketballGame" --region us-east-1 --profile PMprofile
  ```

  The following example shows the return value:

  ```
  {
    "Flow": {
      "AvailabilityZone": "us-east-1d",
      "Entitlements": [],
      "FlowArn": "arn:aws:mediaconnect:us-east-1:111122223333:flow:1-23aBC45dEF67hiJ8-12AbC34DE5fG:BasketballGame",
      "Name": "BasketballGame",
      "Outputs": [
        {
          "Address": "192.0.2.12",
          "Description": "RTP-FEC Output",
          "Name": "RTPOutput",
          "OutputArn": "arn:aws:mediaconnect:us-east-1:111122223333:output:2-3aBC45dEF67hiJ89-c34de5fG678h:RTPOutput",
          "Port": 5020,
          "Protocol": "rtp-fec"
        }
      ],
      "Source": {
        "IngestIp": "195.51.100.21",
        "IngestPort": 5010,
        "Name": "BasketballGameSource",
        "Protocol": "rtp-fec",
        "SourceArn": "arn:aws:mediaconnect:us-east-1:111122223333:source:3-4aBC56dEF78hiJ90-4de5fG6Hi78Jk:BasketballGameSource",
        "WhitelistCidr": "10.24.34.0/23"
      },
      "Status": "STANDBY"
    }
  }
  ```