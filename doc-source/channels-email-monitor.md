# Monitoring Email Activity with Amazon Pinpoint<a name="channels-email-monitor"></a>

For email that you send as part of a campaign, Amazon Pinpoint provides options for monitoring your email activity\.

**Note**  
To monitor email activity, you must use a campaign\. You can't monitor email activity outside a campaign\.

## Amazon Pinpoint Analytics<a name="channels-email-monitor-analytics"></a>

The console provides several campaign\-related metrics\. For example, you can view the number of email endpoints that you can target and the number of endpoints that you've already sent messages to\. Also, you can view the open, click, and opt\-out rates for campaigns that you've already sent\. You can view these metrics across all your campaigns or for individual campaigns\.

**To view campaign analytics in the Amazon Pinpoint console**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that you want to view metrics for\.

1. In the navigation pane, under **Analytics**, choose **Campaigns**\.

1. \(Optional\) Choose a campaign from the **Campaigns** table to view metrics specific to that campaign\.

## Streaming Email Event Data<a name="channels-email-monitor-stream"></a>

To monitor data, such as successful and failed email deliveries, configure Amazon Pinpoint to stream email event data to Amazon Kinesis Data Streams or Amazon Kinesis Data Firehose\. Then, you can use the Kinesis platform to analyze this email data\. For more information, see [Streaming Amazon Pinpoint Events to Kinesis](analytics-streaming.md#analytics-streaming-kinesis)\.

For examples of the event data that Amazon Pinpoint streams to Kinesis, see [Event Data](http://docs.aws.amazon.com/pinpoint/latest/developerguide/analytics-streaming.html#analytics-streaming-data) in the *Amazon Pinpoint Developer Guide*\.