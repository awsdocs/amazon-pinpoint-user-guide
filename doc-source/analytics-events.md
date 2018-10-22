# Events Charts<a name="analytics-events"></a>

The charts on the **Events** page help you see trends by displaying charts for a specified event type and its attributes\. You can filter the charts on the page to show any event that your application reports\.

## Viewing the Events Charts<a name="analytics-events-view"></a>

You can view the **Events** charts in the Amazon Pinpoint console\. You can filter the charts on this page by date, event type, and event attributes\.

**To view and filter the Events charts**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Pinpoint Projects** page, choose the project that you want to view revenue metrics for\.

1. In the navigation pane, under **Analytics**, choose **Events**\.

1. \(Optional\) To filter the charts by a specific date or range of dates, choose **Last 30 days**, and then specify a date range\.

1. For **Event**, choose an event type to filter the charts by\.

1. For **Attributes**, specify the event attributes to filter the charts by\.

## Chart Descriptions<a name="analytics-events-description"></a>

The **Events** page includes the following charts:

**Event count**  
This chart displays the number of events that are reported by your app for each day in the selected time period\. This chart also provides the average number of events per day, the total number of events in the time period, and the percentage change in the number of events from the beginning to the end of the time period\.

**Endpoint count**  
This chart displays the number of endpoints that reported the selected event for each day in the selected time period\. This chart also provides the average number of endpoints that reported the event each day, the total number of endpoints that reported the event each day, and the percentage change in the number of endpoints that reported the event from the beginning to the end of the time period\.

**Events per session**  
This chart displays the average number of events that occur in each app session for each day in the selected time period\. Amazon Pinpoint calculates this metric by dividing the number of times the selected event occurred each day by the number of sessions that occurred that day\.  
This chart also provides the average number of events per session for the entire time period, and the percentage change in the number of events per session from the beginning to the end of the time period\.