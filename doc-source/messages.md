# Send Test Messages with Amazon Pinpoint<a name="messages"></a>

With Amazon Pinpoint, you can send *test messages*, which are one\-time messages that you send to a specific set of recipients without creating a campaign\. Sending a test message is useful if you want to test the deliverability of your messages, or to see how your message appears to recipients\. We charge you for each test message that you send, just as if it were a normal campaign message\. However, unlike campaign messages, we don't bill you based on your monthly targeted audience \(MTA\) when you send test messages\.

When you use the Amazon Pinpoint console to send test messages, you can send your messages to up to 15 recipients\. You can't send test messages to segments—you have to send them to individual users\. Amazon Pinpoint delivers test messages immediately—you can't schedule the delivery of test messages\. Finally, test messages don't generate messaging metrics, such as open, click, or bounce rates\. If you want to send a message to a segment, schedule the delivery of a message, or obtain metrics for your messages, you should [create a campaign](campaigns.md) instead of sending a test message\.

You can send test messages using any channel that is supported by Amazon Pinpoint: push notifications, email, or SMS\.

Send test messages by using the **Test messaging** page in the Amazon Pinpoint console\.

**To access the Test messaging page**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project for which you want to send a message\.

1. In the navigation menu, choose **Test messaging**\.