# Adding a media stream to a flow<a name="media-stream-add"></a>

Before you can associate a media stream with a source or an output, you need to add it to the flow\. After you add a media stream to a flow, you can associate it with a source and then with outputs\.

**Note**  
You can only associate a media stream with an output if it has already been associated with a source on the flow\.

**To add a media stream to a flow**

1. Open the MediaConnect console at [https://console\.aws\.amazon\.com/mediaconnect/](https://console.aws.amazon.com/mediaconnect/)\.

1. On the **Flows** page, choose the name of the flow that you want to add the media stream to\.

1. Choose the **Media streams** tab\.

1. Choose **Add media stream**\.

1. In the **Name** field, specify a descriptive name that will help you distinguish this media stream from others in the flow\.

1. For **Description**, specify a description that will help you remember the use of this media stream\. 

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