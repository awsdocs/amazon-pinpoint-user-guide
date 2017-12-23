# Monitoring Mobile Push Activity with Amazon Pinpoint<a name="channels-mobile-monitor"></a>

For push notifications that you send as part of a campaign, Amazon Pinpoint provides options for monitoring your mobile push activity\. 

**Note**  
To monitor push notification activity, you must use a campaign\. You cannot monitor push notification activity outside of a campaign\.

## Streaming Mobile Push Event Data<a name="w3ab1c14c13c16b9"></a>

To monitor data, such as successful and failed mobile push deliveries, configure Amazon Pinpoint to stream mobile push event data to Amazon Kinesis Data Streams or Amazon Kinesis Data Firehose\. Then, you can use the Kinesis platform to analyze this push data\. For more information, see [Streaming Amazon Pinpoint Events to Kinesis](analytics-streaming.md#analytics-streaming-kinesis)\.

For examples of the event data that Amazon Pinpoint streams to Kinesis, see [Event Data](http://docs.aws.amazon.com/pinpoint/latest/developerguide/analytics-streaming.html#analytics-streaming-data) in the *Amazon Pinpoint Developer Guide*\.

## Amazon Pinpoint Analytics<a name="w3ab1c14c13c16c11"></a>

The **Analytics** page in the Amazon Pinpoint console shows trends related to user engagement, campaign outreach, revenue, and more\. To monitor your mobile push activity, you can view metrics such as:

**Targeted**  
User devices to which Amazon Pinpoint attempted to deliver messages\.

**Delivered**  
The number of successful message deliveries\.

**Delivery rate**  
The percentage of all delivery attempts that were successful\.

**Total opened**  
The number of app openings resulting from users tapping notifications sent by the campaign\.

**Open rate**  
Percentage of recipients who opened your app after receiving a push notification from a campaign\.

**Opt out rate**  
Percentage of users who chose not to receive push notifications for your app\.

For more information, see [Amazon Pinpoint Analytics](analytics.md)\.