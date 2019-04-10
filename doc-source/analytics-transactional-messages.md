# Transactional Messaging Charts<a name="analytics-transactional-messages"></a>

The **Transactional Messaging** page contains charts that show you how many transactional emails you've sent\. It also includes charts that help you measure your recipients' responses to your transactional emails—that is, the number of messages that were delivered, opened, clicked, or that bounced or were reported as spam\.

## Viewing the Transactional Messaging Charts<a name="analytics-transactional-messages-view"></a>

You can view the **Transactional Messaging** charts in the Amazon Pinpoint console\. You can filter the charts on this page by date and by channel \(email or SMS\)\.

**To view and filter the Transactional Messaging charts**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All Projects** page, choose the project that you want to view transactional messaging metrics for\.

1. In the navigation pane, under **Analytics**, choose **Transactional messaging**\.

1. Use the menu at the top of the page to choose whether you want to view metrics for transactional **Email** or **SMS** messages, as shown in the following image\.  
![\[\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/analytics-transactional-messaging-channel-selector.png)

1. \(Optional\) To filter the charts by a specific date or range of dates, choose **Last 30 days**\. Then, use the date selector to specify a date range, as shown in the following image\.  
![\[\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/analytics-transactional-messaging-date-selector.png)

## Chart Descriptions<a name="analytics-transactional-messages-description"></a>

The Transactional Messaging page contains several charts that provide information about how your recipients have responded to the transactional emails and SMS messages that you've sent in the time period you selected\. These charts are discussed in detail below\.

**Note**  
These charts only include information about transactional messages\. They don't include information about messages that you sent by using campaigns\. For metrics related to messages that were sent from campaigns, see the [Campaigns charts](analytics-campaigns.md)\.

### Transactional SMS Charts<a name="analytics-transactional-messages-sms"></a>

When you use the channel selector to view **SMS** data, you see the following metrics:

**Sends**  
The total number of transactional SMS messages you sent in the time period that you selected\.

**Deliveries**  
The number of transactional SMS messages that were delivered to their recipients in the time period that you selected\. There are several factors that could cause this value to differ from the number of SMS messages that were sent\. For example, if you send an SMS message to a phone number that doesn't exist, it is counted as sent, but not delivered\.

**Delivery rate**  
The percentage of SMS messages that you sent that were delivered to their recipients\. We calculate this number by dividing the number of messages that were delivered each day by the number of messages that were sent each day\.

**Messages by country or region**  
Shows all of the countries that you sent SMS messages to\. For each country in the list, this table shows the number of messages that you sent to recipients in that country \(**Messages sent**\), the number of messages that were delivered to recipients in that country \(**Messages delivered**\), and the average price that you paid for each message that you sent to that country \(**Average price**\)\.

**Message delivery errors**  
Shows errors that occurred as a result of the transactional SMS messages that you sent\. Expand the **Show all SMS errors** section to view a list of all error types\. For each error, this section shows the total number of times that the error occurred in the selected period \(**Total over period**\), the average number of times the error occurred for each day \(**Average over period**\), and the percentage change in the number of errors that occurred between the first and last days of the time period \(**Change over period**\)\.

### Transactional Email Charts<a name="analytics-transactional-messages-email"></a>

When you use the channel selector to view **Email** data, you see the following metrics:

**Sends**  
The total number of transactional email messages you sent in the time period you selected\.

**Deliveries**  
The number of transactional email messages that were delivered to their recipients in the time period\. There are several factors that could cause this value to differ from the number of emails that were sent\. For example, if an email bounces, it is counted as sent, but not delivered\.

**Opens**  
The number of transactional messages that were received by their recipients and opened\. Amazon Pinpoint adds a very small, transparent image to the end of each transactional message you send\. When a recipient opens an email that contains one of these images, their email client downloads the image from our servers, and we count the message as opened\. If a recipient opens the same message more than once, we count each of those opens separately\.

**Clicks**  
The number of transactional messages that contained links that were clicked by their recipients\. When you send a transactional email that contains links, Amazon Pinpoint replaces those links with links that refer to our servers\. When a recipient clicks one of these links, we redirect the recipient to their intended location, and count the message as clicked\. If a recipient clicks a link in the same message more than once, or clicks multiple links in the same message, we count each of those clicks separately\.

**Complaints**  
The number of transactional messages that were reported by their recipients as spam\. When a recipient uses the **Mark as Spam** or similar function in their email client, the recipient's email provider notifies us that the message was reported\.

**Delivery rate**  
The average delivery rate for transactional emails that you sent in the time period that you selected\. We calculate this rate by dividing the number of emails that were delivered by the number of emails that you sent for each day in the time period that you selected\. We then calculate the average rate based on the number of days in the time period\.

**Bounce rate**  
The average bounce rate for transactional emails that you sent in the time period that you selected\. We calculate this rate by dividing the number of emails that hard bounced by the number of emails that you sent for each day in the time period that you selected\. We then calculate the average rate based on the number of days in the time period\.

**Complaint rate**  
The average complaint rate for transactional emails that you sent in the time period that you selected\. We calculate this rate by dividing the number of emails that were reported by their recipients as spam by the number of emails that you sent for each day in the time period that you selected\. We then calculate the average rate based on the number of days in the time period\.

**Unique user events**  
This chart shows the numbers of opens and clicks for the time period you selected\. Unlike the **Opens** and **Clicks** charts, these charts show the numbers of unique recipients who opened or clicked messages, as opposed to the total number of open and click events that occurred\. In other words, if a single user opens a message five times, the **Opens** chart would show five open events, but this chart would only show a single open\.

**Bounce and complaint events**  
This chart shows the numbers of soft bounces, hard bounces, and complaints that occurred on each day of the selected time period\. Soft bounces are usually temporary in nature—for example, if the recipient's inbox is full or their mail server is temporarily offline when we attempt to deliver the message, we count it as a soft bounce\. Hard bounces are permanent\. For example, if a recipient's email address doesn't exist or their mail server doesn't accept mail from your domain, we count it as a hard bounce\.