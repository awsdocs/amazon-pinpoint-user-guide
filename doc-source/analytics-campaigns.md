# Campaign Charts<a name="analytics-campaigns"></a>

The charts on the **Campaigns** page provide information about all of the campaigns for the chosen app or project\. You can also choose a specific campaign to view additional delivery and engagement metrics for that campaign\.

## Viewing the Campaign Charts<a name="analytics-campaigns-view"></a>

You can view the **Campaigns** charts in the Amazon Pinpoint console\. 

**To view and filter the Campaigns charts**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Pinpoint Projects** page, choose the project that you want to view campaign metrics for\.

1. In the navigation pane, under **Analytics**, choose **Campaigns**\.

1. \(Optional\) Choose **Last 30 days** to choose a range of dates\. When you choose a new date range, the charts update to show data for the specified time period\.

## Chart Descriptions<a name="analytics-campaigns-description"></a>

The **Campaigns** page includes a section that provides aggregated metrics for all campaigns that were active during the selected time period\. When you choose a specific campaign, you see a new set of charts that contain metrics specific to that campaign\.

### Aggregated Campaign Metrics<a name="analytics-campaigns-description-aggregated"></a>

The **Campaigns** page includes the following metrics, which are aggregated across all campaigns that were active during the selected time period\.

**Active targetable endpoints**  
Shows the total number of *targetable endpoints*\. Targetable endpoints are endpoints that have opened your app at least once in the past 30 days, and that haven't opted out of receiving messages from you\. This section includes the total number of active targetable endpoints, as well as the number of active targetable endpoints for each channel \(push notification, email, and SMS\)\.

**Campaigns**  
Shows the total number of campaigns that were active in the time period you selected\. Also shows the number of endpoints that you sent messages to in the selected time period, and the delivery, open, and opt\-out rates for campaigns sent in the selected time period\.

### Metrics for Individual Campaigns<a name="analytics-campaigns-description-individual"></a>

When you choose a campaign from the list of campaigns, you see metrics that are specific to that campaign\. The metrics that you see depend on the channel of the campaign\.

**Note**  
When you select an A/B test campaign, you see the metrics listed in the following sections for each treatment\. This report makes it easy to compare the effectiveness of various treatments for your campaign\.

#### Email Campaigns<a name="analytics-campaigns-description-individual-email"></a>

When you select a standard campaign that uses the email channel, you see the following charts:

**Delivery count metrics**  
Provides the following metrics that relate to the delivery of messages from this campaign:    
**Endpoints messaged**  
The number of unique email endpoints that received email from this campaign\.  
**Messages sent**  
The number of messages sent from the campaign\.  
**Messages delivered**  
The number of messages that were delivered to their intended recipients\. Amazon Pinpoint calculates this number by subtracting the number of messages that hard bounced from the total number of messages you sent\.  
**Links clicked**  
The number of times that recipients of the campaign clicked a link in the email\. If a single recipient clicks multiple links in an email, or clicks the same link more than once, each click is counted as a separate event\.

**Delivery rate metrics**  
Provides the following metrics that relate to the delivery of messages from this campaign:    
**Delivery rate**  
The percentage of emails that were delivered to their intended recipients\. Amazon Pinpoint calculates this rate by dividing the number of messages that were delivered by the number of messages sent\.  
**Open rate**  
The percentage of emails that were opened by their recipients\. Amazon Pinpoint calculates this rate by dividing the number of messages that were opened by the number of messages that were delivered\.  
**Bounce rate**  
The percentage of emails that couldn't be delivered to their intended recipients\. This metric only measures *hard bounces*—that is, messages in which the recipient's email address had a permanent issue that prevented the message from being delivered\. Amazon Pinpoint calculates this rate by dividing the number of bounced emails by the number of messages sent\.

**Campaign runs**  
Provides the following metrics that relate to the timing and delivery of your messages each time this campaign ran\.    
**Run date**  
The date and time when the campaign was sent\.  
**Endpoints targeted**  
The number of unique endpoints that you attempted to send this message to\.  
**Messages sent**  
The number of messages that were sent during this campaign run\. This number might differ from the number of endpoints targeted, if the targeted segment includes email addresses that are incorrectly formatted or are known to produce hard bounces\. This number also omits endpoints that have opted out\.  
**Messages delivered**  
The number of messages sent from this campaign run that were delivered to their intended recipients\.  
**Delivery rate**  
The percentage of messages sent from this campaign run that were delivered\. Amazon Pinpoint calculates this rate by dividing **Messages delivered** by **Messages sent**\.  
**Total email opened**  
The number of messages that were opened by their recipients\. Because of technical limitations, this value only includes recipients who opened the message in an email client that supports images\.  
**Email open rate**  
The percentage of messages that were opened by their recipients\. Amazon Pinpoint calculates this rate by dividing **Total opened** by **Messages delivered**\.  
**Bounce rate**  
The percentage of messages that couldn't be delivered to their recipients\. This metric only measures hard bounces\. Amazon Pinpoint calculates this rate by dividing the number of emails that bounced during the campaign run by **Messages delivered**\.

#### Push Notification Campaigns<a name="analytics-campaigns-description-individual-push"></a>

When you select a standard campaign that sends push notifications, you see the following charts:

**Campaign delivery counts**  
Provides the following metrics that relate to the delivery of messages from this campaign:    
**Endpoints messaged**  
The number of unique push notification endpoints that received a notification from this campaign\.  
**Messages sent**  
The number of messages sent from the campaign\.  
**Messages delivered**  
The number of messages that were delivered to their intended recipients\. Amazon Pinpoint calculates this number by subtracting the number of messages that couldn't be delivered from the total number of messages you sent\.

**Campaign engagement rates**  
Provides the following metrics that relate to the delivery of messages from this campaign:    
**Delivery rate**  
The percentage of push notifications that were delivered to their intended recipients\. Amazon Pinpoint calculates this rate by dividing **Messages delivered** by **Messages sent**\.  
**Push open rate**  
The percentage of notifications that led to the recipient opening your app\. Amazon Pinpoint calculates this rate by dividing the number of recipients who received a message from you and later opened your app by **Messages delivered**\.

**Sessions per endpoint**  
Shows the average number of times an endpoint opened your app during the selected time period\. Amazon Pinpoint calculates this number by finding the number of times endpoints targeted by this campaign opened your app, and dividing that by the number of unique endpoints targeted by the campaign\.

**Purchases per endpoint**  
Shows the average number of purchases per endpoint during the selected time period\. Amazon Pinpoint calculates this number by finding the number of purchases made by endpoints targeted by this campaign, and dividing that by the number of unique endpoints targeted by the campaign\.

**Campaign session heat map**  
The days and times when users opened your app after receiving a push notification notification that was sent by this campaign\. Darker rectangles represent greater numbers of users\. Times are based on each user's local time zone\.

**Campaign runs**  
Provides the following metrics that relate to the timing and delivery of your messages each time this campaign ran\.    
**Run date**  
The date and time when the campaign was sent\.  
**Endpoints targeted**  
The number of unique endpoints that you attempted to send this message to\.  
**Messages sent**  
The number of messages that were sent during this campaign run\. This number might differ from the number of endpoints targeted if the targeted segment includes invalid tokens, or endpoints that have opted out\.  
**Messages delivered**  
The number of messages sent from this campaign run that were delivered to their intended recipients\.  
**Delivery rate**  
The percentage of messages sent from this campaign run that were delivered\. Amazon Pinpoint calculates this rate by dividing **Messages delivered** by **Messages sent**\.  
**Total push opened**  
The number of messages that led to their recipients opening your app\.  
**Push open rate**  
The percentage of messages that led to their recipients opening your app\. Amazon Pinpoint calculates this rate by dividing **Total opened** by **Messages delivered**\.

#### SMS Campaigns<a name="analytics-campaigns-description-individual-sms"></a>

When you select a standard campaign that uses the SMS channel, you see the following charts:

**Delivery metrics**  
Provides the following metrics that relate to the delivery of messages from this campaign:    
**Endpoints messaged**  
The number of unique SMS endpoints that received a notification from this campaign\.  
**Messages sent**  
The number of messages that were sent from the campaign\.  
**Messages delivered**  
The number of messages that were delivered to their intended recipients\. Amazon Pinpoint calculates this number by subtracting the number of messages that couldn't be delivered from the total number of messages you sent\.  
**Delivery rate**  
The percentage of messages that were delivered to their intended recipients\. Amazon Pinpoint calculates this rate by dividing **Messages sent** by **Messages delivered**\.

**Total SMS spend**  
Shows the total amount of money, in USD, that you spent sending SMS messages in the selected time period\.

**Campaign runs**  
Provides the following metrics that relate to the timing and delivery of your messages each time this campaign ran\.    
**Run date**  
The date and time when the campaign was sent\.  
**Endpoints targeted**  
The number of unique endpoints that you attempted to send this message to\.  
**Messages sent**  
The number of messages that were sent during this campaign run\. This number might differ from the number of endpoints targeted if the targeted segment includes invalid phone numbers, or endpoints that have opted out\.  
**Messages delivered**  
The number of messages sent from this campaign run that were delivered to their intended recipients\.  
**Delivery rate**  
The percentage of messages sent from this campaign run that were delivered\. Amazon Pinpoint calculates this rate by dividing **Messages delivered** by **Messages sent**\.