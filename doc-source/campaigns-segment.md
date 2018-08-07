# Step 2: Specify the Audience Segment for the Campaign<a name="campaigns-segment"></a>

When creating a campaign, you can specify which audience segment to reach with your campaign by creating a new segment or choosing one that was previously created\.

**Prerequisite**  
Before you begin, complete [Step 1: Begin a New Campaign](campaigns-begin.md)\.

**To specify a segment**
+ For the **Segment** step in **Create a campaign**, specify a segment in one of the following ways:
  + Choose **Create a new segment** and follow the steps under *To build a segment*\.
  + Choose **Use a previously defined segment** and select the segment that you want to target\. Then, choose **Next step**\.

**To build a segment**

To build your segment, define the segmentation criteria\. As you choose criteria, the **Segment estimate** shows how many users the segment includes\.  
![\[The segment estimate shows how many users belong to the segment with the selected criteria.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_estimate.png)![\[The segment estimate shows how many users belong to the segment with the selected criteria.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The segment estimate shows how many users belong to the segment with the selected criteria.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. For **Name your segment to reuse it later**, type a name to make your segment easy to recognize\.

1. If you selected **Mobile push** as the channel type, define the **App usage criteria**\. Select which users belong to the segment based on whether they have \(or haven't\) used your app within the specified number of days\.  
![\[The app usage criteria options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_usage.png)![\[The app usage criteria options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The app usage criteria options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. \(Optional\) For **Filter by standard attributes**, define which users belong to the segment based on the characteristics that are standard to Amazon Pinpoint\.  
![\[The device attributes options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_standard_attributes.png)![\[The device attributes options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The device attributes options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. \(Optional\) For **Filter by custom attributes** and **Filter by user attributes**, define which users belong to the segment based on custom attributes that you add to your Amazon Pinpoint endpoint resources\.

1. If you chose to create a standard campaign, you can use this page to allocate the **holdout**, which is the percentage of users in the segment who will not receive messages from the campaign\.  
![\[The holdout slider.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/campaigns_holdout.png)![\[The holdout slider.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The holdout slider.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

   If you're creating an A/B test, you allocate the holdout when you define the message or schedule\.

1. When you finish defining the segment, choose **Next step**\.

**Next**  
[Step 3: Write the Message](campaigns-message.md)