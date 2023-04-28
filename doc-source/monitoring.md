# Monitoring Amazon Pinpoint with Amazon CloudWatch<a name="monitoring"></a>

You can use Amazon CloudWatch to collect, view, and analyze several important metrics related to your Amazon Pinpoint account and projects\. When you configure CloudWatch for Amazon Pinpoint, you gain insight into the delivery of your Amazon Pinpoint campaigns, as well as the status of your endpoint registrations and import jobs\. You can also use CloudWatch to create alarms that notify you when certain metrics exceed values that you define\. For example, you can create an alarm that automatically sends you an email if a certain number of campaign messages fail within a specific time period\.

For directions on how to stream events and logs see [Streaming Amazon Pinpoint events to Kinesis](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams.html) in the [Amazon Pinpoint Developer Guide](https://docs.aws.amazon.com/pinpoint/latest/developerguide/)\.

**Topics**
+ [Amazon Pinpoint metrics that are exported to CloudWatch](monitoring-metrics.md)
+ [View Amazon Pinpoint metrics in CloudWatch](monitoring-view-metrics.md)
+ [Create CloudWatch alarms for Amazon Pinpoint metrics](monitoring-create-alarms.md)