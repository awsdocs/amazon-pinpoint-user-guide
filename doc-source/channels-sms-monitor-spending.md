# Monitoring SMS Spending Activity with Amazon Pinpoint<a name="channels-sms-monitor-spending"></a>

This topic contains information about viewing SMS spending metrics in CloudWatch\. It also contains procedures for using CloudWatch to set up an alarm that sends you a notification when your monthly SMS spending goes over a certain amount\.

## View Your Monthly SMS Spending by Using CloudWatch<a name="channels-sms-monitor-spending-metrics"></a>

You can quickly determine how much money you've spent sending SMS messages in the current month by using the Metrics section of the CloudWatch console\. CloudWatch retains metrics for 15 months, so you can view real\-time data and analyze historical trends\.

For more information about viewing metrics in CloudWatch, see [Using Amazon CloudWatch Metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html) in the *Amazon CloudWatch User Guide*\.

**To view SMS spending metrics in CloudWatch**

1. Open the CloudWatch console at [https://console\.aws\.amazon\.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/)\.

1. In the navigation pane, choose **Metrics**\.

1. On the **All Metrics** tab, choose **SNS**\.

1. Choose **Metrics with no dimensions**\.

1. Select **SMSMonthToDateSpendUSD**\. The chart updates to display the amount of money that you've spent sending SMS messages in the current month using both Amazon Pinpoint and Amazon SNS\.
**Note**  
The **SMSMonthToDateSpendUSD** metric doesn't appear until you send at least one SMS message through Amazon Pinpoint or Amazon SNS\.

## Create an SMS Spending Alarm<a name="channels-sms-monitor-spending-alarms"></a>

In addition to viewing your monthly SMS spending metrics, you can also create alarms in CloudWatch that send you notifications when your SMS spending exceeds a certain amount\. You can set up CloudWatch to deliver these notifications to you by sending them to an Amazon SNS topic\.

For more information about creating alarms in CloudWatch, see [Creating Amazon CloudWatch Alarms](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) in the *Amazon CloudWatch User Guide*\.

**To create an SMS spending alarm in CloudWatch**

1. If you haven't already done so, create an Amazon SNS topic and subscribe an endpoint to it\. The endpoint that you subscribe to the topic should be the location where you want to receive spending notifications\. For example, if you want to receive spending notifications by email, subscribe your email address to the Amazon SNS topic\. If you want to receive spending notifications by text message, subscribe an SMS endpoint to the topic\.

   For more information about creating and subscribing to topics, see [Getting Started with Amazon Simple Notification Service](https://docs.aws.amazon.com/sns/latest/dg/GettingStarted.html) in the *Amazon Simple Notification Service Developer Guide*\.

1. Open the CloudWatch console at [https://console\.aws\.amazon\.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/)\.

1. In the navigation pane, under **Alarms**, choose **Billing**\.

1. Choose **Create Alarm**\.

1. Under **SNS Metrics**, choose **Metrics with no dimensions**, and then select **SMSMonthToDateSpendUSD**\. Choose **Next**\.
**Note**  
The **SMSMonthToDateSpendUSD** metric doesn't appear until you send at least one SMS message through Amazon Pinpoint or Amazon SNS\.

1. Under **Alarm Threshold**, complete the following steps: 
   + For **Name**, type a name for the alarm\. 
   + For **Description**, type a description of the alarm\.
   +  For **Whenever**, specify the dollar amount \(in US Dollars\) that should trigger the alarm\. Also, specify the number of periods that the spending amount must exceed the threshold in order to trigger the alarm\. 

1. Under **Additional settings**, for **Treat missing data as**, choose **ignore**\.

1. Under **Actions**, make the following selections:
   + For **Whenever this alarm**, choose **State is ALARM**\. 
   + For **Send notification to**, choose the Amazon SNS topic that the notification should be sent to\.

1. Choose **Create Alarm**\.