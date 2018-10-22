# Overview Charts<a name="analytics-overview"></a>

The **Analytics** page contains several charts that give you an overview of the application usage and campaign responses for your project\.

## Viewing the Analytics Overview Charts<a name="analytics-overview-view"></a>

You can view the **Analytics** overview page in the Amazon Pinpoint console\. 

**To view and filter the Analytics overview charts**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Pinpoint Projects** page, choose the project that you want to view the Analytics charts for\.

1. In the navigation pane, choose **Analytics**\.

1. \(Optional\) Choose **Last 30 days** to choose a range of dates\. When you choose a new date range, the charts update to show data for the specified time period\.

## Chart Descriptions<a name="analytics-overview-description"></a>

The **Analytics Overview** page contains two sections: [App analytics](#analytics-overview-description-app-analytics) and [Campaign analytics](#analytics-overview-description-campaign-analytics)\.

### App analytics<a name="analytics-overview-description-app-analytics"></a>

The **App analytics** section contains some of the most commonly used metrics that are related to using your application\.

**Daily active endpoints**  
Shows the number of endpoints that opened your app at least once in a 24\-hour period for each day in the selected time period\. This chart also provides the average number of daily active endpoints for the entire time period, and the percentage change in the number of daily active endpoints from the beginning to the end of the time period\.

**Monthly active endpoints**  
Shows the number of endpoints that opened your app at least once in the previous 30 days for each day in the selected time period\. This chart also provides the average number of monthly active endpoints for the entire time period, and the percentage change in the number of monthly active endpoints from the beginning to the end of the time period\.

**New endpoints**  
Shows the number of endpoints that were registered with Amazon Pinpoint for the first time for on each day in the selected time period\. This chart also provides the average number of new endpoints for the entire time period, and the percentage change in the number of new endpoints from the beginning to the end of the time period\.

**7\-day retention rate**  
Shows the percentage of users who opened your app 8 days ago, and then opened it again at some point in the following 7 days\. This chart also provides the average 7\-day retention rate for the entire time period, and the percentage change in the 7\-day retention rate from the beginning to the end of the time period\.

**Sessions**  
The total number of times that your app was opened each day in the selected time period\. This chart also provides the average number of daily sessions for the entire time period, and the percentage change in the number of sessions from the beginning to the end of the time period\.

**Revenue**  
The revenue, in USD, that was reported by your app for each day in the selected time period\. This chart also provides the average daily revenue for the entire time period, and the percentage change in the amount of revenue from the beginning to the end of the time period\.

### Campaign analytics<a name="analytics-overview-description-campaign-analytics"></a>

The **Campaign analytics** section contains several important metrics that help you understand the success of your campaigns\. The metrics in this section provide aggregated metrics for all the campaigns in the current application or project\.

**Active targetable endpoints**  
Shows the number of endpoints that are opted in to receive messages from you, and that have opened your app in the past 30 days\. This section displays the number of active targetable endpoints by channel \(push notification, email, and SMS\), as well as the total number of active targetable endpoints\.

**Campaigns**  
Shows information about the campaigns that were active during the time period you selected\. This section includes the following information:    
**Active campaigns**  
The number of campaigns that were active during the selected time period\.  
**Endpoints messaged**  
The number of endpoints that received a message during the selected time period\.  
**Delivery rate**  
The percentage of targeted endpoints that received messages from you\. Amazon Pinpoint calculates this rate by dividing the number of messages that were delivered to their intended recipients by the total number of messages that you sent\.  
**Email open rate**  
The number of email messages sent from this project that were opened by their recipients, divided by the number of messages that were received by their recipients\.  
**Push open rate**  
The number of recipients who opened your app as a result of receiving a push notification from this project, divided by the number of recipients who received the message\.  
**Opt out rate**  
The percentage of customers who opted out after receiving the message\. Amazon Pinpoint calculates this rate by dividing the number of recipients who received your message and opted out by the number of messages that were received by their intended recipients\. \(The recipients could have opted out by clicking an unsubscribe link in an email, or by replying to an SMS message with the keyword `STOP`\)\. 