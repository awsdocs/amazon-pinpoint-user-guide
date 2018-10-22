# Send Test Messages with Amazon Pinpoint<a name="messages"></a>

With Amazon Pinpoint, you can send *test messages*, which are one\-time messages that you send to a specific set of recipients without creating a campaign\. Sending a test message is useful if you want to test the deliverability of your messages, or to see how your message appears to recipients\. We charge you for each test message you send, just as if it were a normal campaign message\. However, unlike campaign messages, we don't bill you based on your monthly targeted audience \(MTA\) when you send test messages\.

You can send test messages to up to 15 recipients\. You can't use the message to engage a segment\. When you send the message, Amazon Pinpoint delivers it immediately, and you can't schedule the delivery\. Additionally, test messages don't generate messaging metrics, such as open and bounce rates\. If you want to engage a user segment, schedule the message delivery, and observe message engagement rates, you should [create a campaign](campaigns.md) instead of sending a test message\. 

You can send test messages using any channel that is supported by Amazon Pinpoint: push notifications, email, or SMS\.

Send test messages by using the **Test messaging** page in the Amazon Pinpoint console\.

**To access the Test messaging page**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project for which you want to send a message\.

1. In the navigation menu, choose **Test messaging**\.