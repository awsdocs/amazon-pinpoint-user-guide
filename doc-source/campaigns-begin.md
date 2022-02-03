# Step 1: Create a campaign<a name="campaigns-begin"></a>

The first step in setting up a campaign is to create a new campaign\. When you create a new campaign, you give the campaign a name, specify whether the campaign should be a standard campaign or an A/B test campaign, and choose the channel that you want to use to send the campaign\.

**To begin creating a campaign**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that you want to create the campaign in\.

1. In the navigation pane, choose **Campaigns**\.

1. Choose **Create a campaign**\.

1. For **Campaign name**, enter a descriptive name for the campaign\. Using a descriptive name makes it easier to find or search for the campaign later\.

1. For **Campaign type**, choose one of the following options:
   + **Standard campaign** – Sends a message to a segment on a schedule that you define\.
   + **A/B test campaign** – Behaves like a standard campaign, but enables you to define different treatments for the campaign's message or schedule\. In an A/B test campaign, you create several versions of a message or schedule to compare their performance\.

1. Under **Choose a channel for this campaign**, choose the channel that you want to use to send the campaign\.
**Note**  
You can only choose a single channel\. You can only choose the channels that are enabled for the current project\. The **Custom** channel is enabled for all projects by default\.

1. If you chose **In\-app messaging** in the preceding step, choose a **Prioritization** for the in\-app message\. The value that you choose determines which message is shown in response to a trigger event\.

   If you chose a different message type, proceed to the next step\.

1. Choose **Next**\.

**Next**  
[Step 2: Specify the audience for the campaign](campaigns-segment.md)