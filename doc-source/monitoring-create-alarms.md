# Create CloudWatch Alarms for Amazon Pinpoint Metrics<a name="monitoring-create-alarms"></a>

In Amazon CloudWatch, you can create alarms that send notifications when specific metrics exceed a particular value\. For example, you could set an alarm that sends you an email when the **ImportedEndpointFailure** metric exceeds a certain value\. In this example, if the number of endpoint import failures exceeds the threshold that you specified, you receive an email alerting you of the issue\. This section contains procedures for setting up an alarm for Amazon Pinpoint metrics in the CloudWatch console\.

**Important**  
Before you can complete the procedures in this section, you have to create an Amazon SNS topic and subscribe an endpoint to it\. For more information, see [Create a Topic](https://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html) and [Subscribe to a Topic](https://docs.aws.amazon.com/sns/latest/dg/SubscribeTopic.html) in the *Amazon Simple Notification Service Developer Guide*\.

**To create an alarm for Amazon Pinpoint metrics in the CloudWatch console**

1. Open the CloudWatch console at [https://console\.aws\.amazon\.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/)\.

1. Choose **Alarms**, and then choose the **Create Alarm** button\. The **Create Alarm** wizard appears\. 

1. In the **Pinpoint Metrics** section, choose the metric you want to create an alarm for\. Choose **Next**\. 

1. In the **Alarm Threshold** section, do the following:
   + Type a **Name** and a **Description** for the alarm\.
   + Specify the value that causes CloudWatch to raise an alarm, as shown in the following image\.  
![\[The Alarm Threshold section of the CloudWatch alarm creation wizard. The alarm is set to trigger whenever the ImportedEndpointFailure metric is greater than or equal to 10 for 1 out of 1 consecutive datapoints.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/monitoring-cw-alarm-trigger.png)![\[The Alarm Threshold section of the CloudWatch alarm creation wizard. The alarm is set to trigger whenever the ImportedEndpointFailure metric is greater than or equal to 10 for 1 out of 1 consecutive datapoints.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Alarm Threshold section of the CloudWatch alarm creation wizard. The alarm is set to trigger whenever the ImportedEndpointFailure metric is greater than or equal to 10 for 1 out of 1 consecutive datapoints.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. In the **Actions** section, do the following:
   + For **Whenever this alarm**, choose **State is ALARM**\. This setting tells CloudWatch to send a notification when the state of the alarm is `ALARM` \(as opposed to `OK` or `INSUFFICIENT`\)\.
   + For **Send notification to**, choose the Amazon SNS topic that should be notified when the alarm is triggered, as shown in the following image\.  
![\[The Actions section of the CloudWatch alarm creation wizard. In this example, whenever the state of the alarm is ALARM, CloudWatch sends a notification to an Amazon SNS topic called "ops-team".\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/monitoring-send-notification.png)![\[The Actions section of the CloudWatch alarm creation wizard. In this example, whenever the state of the alarm is ALARM, CloudWatch sends a notification to an Amazon SNS topic called "ops-team".\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Actions section of the CloudWatch alarm creation wizard. In this example, whenever the state of the alarm is ALARM, CloudWatch sends a notification to an Amazon SNS topic called "ops-team".\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. Choose **Create Alarm**\.
**Note**  
There are additional settings that you can configure when you create a CloudWatch alarm\. For additional information about configuring CloudWatch alarms, see [Create or Edit a CloudWatch Alarm](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ConsoleAlarms.html) in the *Amazon CloudWatch User Guide*\.

For more information about using CloudWatch and alarms, see the [CloudWatch Documentation](https://aws.amazon.com/documentation/cloudwatch)\.