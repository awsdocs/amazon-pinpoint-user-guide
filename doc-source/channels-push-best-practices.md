# Best practices<a name="channels-push-best-practices"></a>

Even when you have your customers' best interests in mind, you may still encounter situations that impact the deliverability of your messages\. The following sections contain recommendations to help ensure that your push communications reach your intended audience\.

## Sending a high volume of push notifications<a name="channels-push-best-practices-highvolume"></a>

Before you send a high volume of push notifications, make sure that your Amazon Pinpoint account is configured to support your throughput requirements\. By default, all Amazon Pinpoint accounts are configured to send 25,000 messages per second\. If you need to be able to send more than 25,000 messages in one second, you can request a quota increase\. For more information, see [Requesting a quota increase](https://docs.aws.amazon.com/pinpoint/latest/developerguide/quotas.html#quotas-increase) in the *Amazon Pinpoint Developer Guide*

Make sure that your Amazon Pinpoint account is correctly configured with the credentials for each of the push notification providers that you plan to use, such as FCM or APNs\.

Finally, devise a way to handle exceptions\. Each push notification service provides different exception messages\. For transactional sends, you receive a main status code of 200 for the API call, with a per endpoint status code of 400 permanent failure if the corresponding platform token \(for example, FCM\) or certificate \(for example, APN\) is determined to be invalid during message sends\. For campaigns, you will see fewer than expected deliveries corresponding to the campaign activities\. See [Streaming Amazon Pinpoint events to Kinesis](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams.html) in the *Amazon Pinpoint Developer Guide* for more information on setting up streaming events\.