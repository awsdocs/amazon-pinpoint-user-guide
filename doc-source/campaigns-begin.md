# Step 1: Begin a New Campaign<a name="campaigns-begin"></a>

Use the Amazon Pinpoint console to create a campaign\. You will:

+ Choose the messaging channel \(mobile push, email, or SMS\)\.

+ Choose the user segment for the campaign\.

+ Write the message\.

+ Define the schedule on which the campaign runs\.

Optionally, you can set up your campaign as an A/B test to experiment with different treatments of the message or schedule\. As users respond to your campaign, you can view campaign analytics to compare the effectiveness of each treatment\.

**To begin creating a campaign**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project for which you want to create a campaign\.

1. In the navigation menu, choose **Campaigns**\. The **Campaigns** page opens, and it displays summary information for previously defined campaigns\.

1. Choose **New campaign**\. The **Create a campaign** page opens at the **Details** step\.  
![\[The Details page for creating a campaign.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Details page for creating a campaign.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Details page for creating a campaign.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. For **Campaign name**, type a name to make the campaign easy to recognize later\.

1. For **What messaging channel do you want to use?**, choose the channel you will use to deliver your message\. The channel must be enabled in your Amazon Pinpoint project\. For more information, see [Amazon Pinpoint Channels](channels.md)\.

1. For **Choose the campaign type**, choose one of the following:

   + **Standard campaign** – Sends a custom message to a specified segment according to a schedule that you define\.

   + **A/B Test** – Behaves like a standard campaign, but enables you to define different treatments for the campaign's message or schedule\.

1. If you choose to create an A/B test, for **Choose what you will test for**, choose whether you will test variations of the campaign's **Messages** or **Schedule**\.  
![\[Options to create A/B test for messages or schedule.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[Options to create A/B test for messages or schedule.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[Options to create A/B test for messages or schedule.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. Choose **Next step**\.

**Next**  
[Step 2: Specify the Audience Segment for the Campaign](campaigns-segment.md)