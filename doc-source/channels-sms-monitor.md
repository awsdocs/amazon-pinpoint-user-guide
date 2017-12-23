# Monitoring SMS Activity with Amazon Pinpoint<a name="channels-sms-monitor"></a>

Amazon Pinpoint provides the following options for monitoring your SMS activity\.

## Streaming SMS Event Data<a name="w3ab1c14c18c18c13"></a>

To monitor your SMS activity, such as successful and failed message deliveries, you can configure Amazon Pinpoint to stream SMS event data to Amazon Kinesis Data Streams or Amazon Kinesis Data Firehose\. Then, you can use the Kinesis platform to analyze your SMS data\. For more information, see [Streaming Amazon Pinpoint Events to Kinesis](analytics-streaming.md#analytics-streaming-kinesis)\.

For examples of the event data that Amazon Pinpoint streams to Kinesis, see [Event Data](http://docs.aws.amazon.com/pinpoint/latest/developerguide/analytics-streaming.html#analytics-streaming-data) in the *Amazon Pinpoint Developer Guide*\.

## Amazon Pinpoint Analytics<a name="w3ab1c14c18c18c15"></a>

On the **Analytics** page in the Amazon Pinpoint console, you can view metrics for the number of active targetable users that you can engage with the SMS channel\. 