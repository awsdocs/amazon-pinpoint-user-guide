# Usage Charts<a name="analytics-usage"></a>

The **Usage** page includes charts that show you how often your app is being used and how successfully it retains user interest over time\.

**Note**  
Some of the charts on the **Usage** page refer to *endpoints*, while others refer to *users*\. For more information about the difference between users and endpoints, see [Endpoints and Users in Charts](analytics-charts.md#analytics-endpoints-users)\.

## Viewing the Usage Charts<a name="analytics-usage-view"></a>

You can view the **Usage** charts in the Amazon Pinpoint console\. You can filter the charts on this page by date\.

**To view and filter the Usage charts**

1. In the navigation pane, under **Analytics**, choose **Usage**\.

1. *\(Optional\)* Choose **Last 30 days** to filter the charts by a specific date or range of dates\.

## Chart Descriptions<a name="analytics-usage-description"></a>

The **Usage** page contains three sections: [Users Metrics](#analytics-usage-description-users), [Sessions Metrics](#analytics-usage-description-sessions), and [Authentication Metrics](#analytics-usage-description-authentication)\.

### Users Metrics<a name="analytics-usage-description-users"></a>

The **Users metrics** section contains information about how users and endpoints interacted with your app\. These charts help you better understand user retention—that is, the likelihood that a customer who used your app in the past will open it again at a later time\.

For more information about the difference between users and endpoints, see [Endpoints and Users in Charts](analytics-charts.md#analytics-endpoints-users)\.

**Daily active endpoints**  
Shows the number of endpoints that opened your application for each day in the selected time period\. This chart also provides the average number of daily active endpoints for the entire time period, and the percentage change in the number of daily active endpoints from the beginning to the end of the time period\. 

**Monthly active endpoints**  
Shows the number of endpoints that opened your app at some point in the preceding 30 days for each day in the selected time period\. This chart also provides the average number of monthly active endpoints for the entire time period, and the percentage change in the number of monthly active endpoints from the beginning to the end of the time period\.

**New endpoints**  
Shows the number of endpoints that were registered with Amazon Pinpoint for the first time for each day in the selected time period\. This chart also provides the average number of new endpoints for the entire time period, and the percentage change in the number of new endpoints from the beginning to the end of the time period\.

**Daily active users**  
Shows the number of users that opened your application for each day in the selected time period\. This chart also provides the average number of daily active users for the entire time period, and the percentage change in the number of daily active users from the beginning to the end of the time period\.

**Monthly active users**  
Shows the number of users that opened your app at some point in the preceding 30 days for each day in the selected time period\. This chart also provides the average number of monthly active users for the entire time period, and the percentage change in the number of monthly active users from the beginning to the end of the time period\.

**New users**  
Shows the number of new user IDs that were created in Amazon Pinpoint for each day in the selected time period\. This chart also provides the average number of new users for the entire time period, and the percentage change in the number of new users from the beginning to the end of the time period\.

**7\-day retention rate**  
Shows the percentage of users who opened your app 8 days prior, and then opened it again at some point in the following 7 days\. This chart also provides the average 7\-day retention rate for the entire time period, and the percentage change in the 7\-day retention rate from the beginning to the end of the time period\.

**Sticky factor**  
Shows the portion of monthly active endpoints that were active on each day of the selected time period\. For example, a sticky factor of 0\.25 indicates that 25% of active endpoints from the previous 30 days were active on the chosen day\.  
This chart also shows the average sticky factor for the entire time period, as well as the percentage change in the sticky factor rate from the beginning to the end of the time period\.

### Sessions Metrics<a name="analytics-usage-description-sessions"></a>

The **Sessions metrics** section contains information about how often your app was opened\. These metrics help you to better understand how often individual customers use your app, as well as the days and times that they're most likely to use your app\.

**Sessions**  
Shows the number of times your app was opened for each day in the selected time period\. This chart also provides the average number of sessions for the entire time period, and the percentage change in the number of sessions from the beginning to the end of the time period\.

**Sessions per endpoint**  
Shows the number of sessions for each endpoint\. Amazon Pinpoint calculates this number by dividing the number of sessions in the time period by the number of unique endpoints that opened your app in the time period\.   
This chart also provides the average number of sessions per endpoint for the entire time period, and the percentage change in the number of sessions per endpoint from the beginning to the end of the time period\.

**Sessions per user**  
Shows the number of sessions for each user\. Amazon Pinpoint calculates this number by dividing the number of sessions in the time period by the number of unique users who opened your app in the time period\.   
This chart also provides the average number of sessions per user for the entire time period, and the percentage change in the number of sessions per user from the beginning to the end of the time period\.

**Session heat map**  
Shows the days and times when endpoints opened your app\. The times in this chart reflect each endpoint's local time\. Darker rectangles in this chart indicate larger numbers of endpoints opening your app\.

### Authentication Metrics<a name="analytics-usage-description-authentication"></a>

The **Authentication metrics** section includes information about how often existing users sign in to your app, and how often new users sign up for your app\. These charts are useful for tracking the success of new user acquisition programs, or the success of campaigns that attempt to draw disengaged users back to your app, for example\.

**Sign\-ins**  
Shows the number of times that users signed in to your app for each day in the selected time period\. This chart also provides the average number of sign\-ins for the entire time period, and the percentage change in the number of sign\-ins from the beginning to the end of the time period\. 

**Sign\-ups**  
Shows the number of times that users created new accounts for your app for each day in the selected time period\. This chart also provides the average number of sign\-ups for the entire time period, and the percentage change in the number of sign\-ups from the beginning to the end of the time period\. 

**Authentication failures**  
Shows the number of times that users attempted to sign in but were unable to do so for each day in the selected time period\. This chart also provides the average number of authentication failures for the entire time period, and the percentage change in the number of authentication failures from the beginning to the end of the time period\.

**Active users month to date**  
Shows the number of users who opened your app at least once in the current calendar month\.