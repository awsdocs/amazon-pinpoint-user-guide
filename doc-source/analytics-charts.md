# Chart Reference for Amazon Pinpoint Analytics<a name="analytics-charts"></a>

On the **Analytics** page, Amazon Pinpoint provides an **overview** of key metrics, and it provides details for **campaigns**, **demographics**, **funnels**, **usage**, **revenue**, and **users**\. For further analysis, you can choose any **event** that is reported by your app to see related trends\.

**Note**  
Some charts on the **Analytics** page provide data about *endpoints*, and other charts provide data about *users*\.  
An endpoint represents a destination to which you can send messages, such as a user's mobile device, email address, or phone number\. Before you can see data about endpoints, your application must register endpoints with Amazon Pinpoint, or you must import your endpoint definitions\.  
A user represents an individual who is assigned a unique user ID, and this ID is assigned to one or more endpoints\. For example, if an individual uses your app on multiple devices, your app could assign that person's user ID to the endpoint for each device\. Before you can see data about users, your application must assign user IDs to endpoints, or you must import endpoint definitions that include user IDs\.  
For information about registering endpoints and assigning user IDs within your mobile app, see [Registering Endpoints \(iOS\)](http://docs.aws.amazon.com/pinpoint/latest/developerguide/mobile-sdk-ios-register.html) or [Registering Endpoints \(Android\) ](http://docs.aws.amazon.com/pinpoint/latest/developerguide/mobile-sdk-android-register.html)in the *Amazon Pinpoint Developer Guide*\.  
For information about registering endpoints and assigning user IDs using the AWS SDK for Java, see [Adding Endpoints](http://docs.aws.amazon.com/pinpoint/latest/developerguide/endpoints.html) in the *Amazon Pinpoint Developer Guide*\.  
For information about importing endpoint definitions, see [Importing Segments](segments-importing.md)\.


+ [Overview Charts](#analytics-overview)
+ [Campaigns Charts](#analytics-campaigns)
+ [Demographics Charts](#analytics-demographics)
+ [Events Charts](#analytics-events)
+ [Usage Charts](#analytics-engagement)
+ [Revenue Charts](#analytics-revenue)
+ [Users Charts](#analytics-users)

## Overview Charts<a name="analytics-overview"></a>

The charts on the **Overview** tab summarize metrics related to user engagement and campaigns\.

**Active targetable endpoints**  
User endpoints that were active in the previous 30 days, where users have not opted out of notifications\.

**Campaigns**  
Open rate – Percentage of recipients who opened your app after receiving a push notification from a campaign\.  
Delivered – Messages that were successfully sent to the push notification services for iOS and Android\.  
Active campaigns – Campaigns that are scheduled to start, pending their next run, or currently running\. Does not include campaigns that are complete, paused, or deleted\.

**Daily active endpoints**  
User endpoints that are active on a specific day\.

**Monthly active endpoints**  
Users endpoints that were active in the previous 30 days\.

**Revenue**  
Revenue that is reported by your app\.

**New endpoints**  
User endpoints that were registered with Amazon Pinpoint for the first time\.

**Sessions**  
Number of times your app was opened\.

**7\-day retention rate**  
Out of the users who opened your app 8 days ago, the percentage who opened it again in the following 7 days\.

## Campaigns Charts<a name="analytics-campaigns"></a>

The charts on the **Campaigns** tab provide the following aggregate information from all of the campaigns for the app\.

**Active users**  
Users who opened your app in the previous 30 days\.

**Delivered**  
Messages that were successfully sent to the push notification services for iOS and Android\.

**Open rate**  
Percentage of recipients who opened your app after receiving a push notification from a campaign\.

**Opt out rate**  
Percentage of users who chose not to receive push notifications for your app\.

Each campaign for the app is summarized with the following metrics\.

**Type**  
Standard – Sends a customized push notification to a specified segment\.  
A/B test – Includes 2 or more treatments for the message or schedule\.

**Schedule**  
The frequency with which the campaign sends push notifications\.

**User devices messaged**  
User devices to which the campaign sent push notifications\.

**Delivered**  
Messages that were successfully sent to the push notification services for iOS and Android\.

**Open rate**  
Percentage of recipients who opened your app after receiving a push notification from a campaign\.

### Individual Campaign Charts – Standard<a name="analytics-campaign"></a>

In addition to the aggregate analytics for all campaigns on the **Campaigns** tab, you can view the analytics for an individual campaign\. The **Analytics** page provides the following information for a standard campaign\.

**Delivery metrics**  
Open rate – Percentage of recipients who opened your app after receiving a push notification from a campaign\.  
Delivery rate – Percentage of the campaign’s delivery attempts that were successfully sent to the push notification services for iOS and Android\.  
User devices messaged – User devices to which the campaign sent push notifications\.

**Campaign session heat map**  
The days and times at which users opened your app from a push notification sent by the campaign\. Darker colors represent greater numbers of users\. Times are based on each user’s local time\.

**Campaign metrics**  
Sent – Attempted push notification deliveries\.  
Delivered – Messages that were successfully sent to the push notification services for iOS and Android\.  
Direct opened – The number of times users opened your app from a push notification sent by the campaign\.

**Sessions per endpoint**  
Average number of app sessions started by each user since the start of the campaign\.  
Average number of times a user endpoint was active since the start of the campaign\.

**Purchases per endpoint**  
Average number of in\-app purchases made per user endpoint since the start of the campaign\.

For a campaign that has delivered messages at least once, the run history is summarized with the following metrics\.

**Targeted**  
User devices to which Amazon Pinpoint attempted to deliver messages\.

**Delivered**  
The number of successful message deliveries\.

**Delivery rate**  
The percentage of all delivery attempts that were successful\.

**Total opened**  
The number of app openings resulting from users tapping the notifications sent by the campaign\.

**Open rate**  
The percentage of app openings resulting from users tapping the notifications sent by the campaign\.

### Individual Campaign Charts – A/B Test<a name="analytics-abcampaign"></a>

For a campaign that includes an A/B test, you can use the campaign's **Analytics** page to compare the effectiveness of the campaign treatments\.

**Treatment comparisons**  
Name – Custom name assigned to the treatment\.  
Allocation – Percentage of users in the campaign's segment who are engaged by the treatment\.  
Sessions per user – Average number of app sessions started by each user engaged by the treatment since the start of the campaign\.  
Purchases per user – Average number of purchases from each user engaged by the treatment since the start of the campaign\.  
vs Holdout – Difference between the *per user* metric and the same metric for users who belong to the campaign's holdout\. For example, if, on average, the users engaged by the treatment start 10 app sessions, and the users who belong to the holdout start 5 app sessions, the vs holdout value is `+5`\.

**Campaign session heat map**  
The days and times at which users opened your app from a push notification sent by the campaign\. Darker colors represent greater numbers of users\. Times are based on each user’s local time\.

## Demographics Charts<a name="analytics-demographics"></a>

The charts on the **Demographics** tab provide the characteristics of the devices on which your app is installed\. If your app reports custom metrics, those are also displayed\.

**Platforms**  
Device platforms on which your app is installed\.

**App versions**  
Versions of your app installed on your users’ devices\.

**Models**  
Device models on which your app is installed\.

**Makes**  
Device makes on which your app is installed\.

**Countries**  
Countries or regions where your users are located\.

**Custom charts**  
Custom attributes reported by your app\.

## Events Charts<a name="analytics-events"></a>

On the **Events** tab, you can choose any event that is reported by your app to see related trends\.

**Event count**  
Events reported by your app that match the selected event type and attributes\.

**Events per session**  
Average number of matching events that occur in each app session\.

**Endpoint count**  
User endpoints that are reporting the selected event\.

## Usage Charts<a name="analytics-engagement"></a>

The charts on the **Usage** tab indicate how frequently your app is being used and how successfully it retains user interest over time\.

**Purchases**  
Number of times purchases were made from your app\.

**Sessions**  
Number of times your app was opened\.

**Sessions per endpoint**  
Average number of times each user endpoint was active\.

**Sticky factor**  
Fraction of monthly active endpoints that were active on a specific day\. For example, a sticky factor of \.25 means that on a specific day, 25% of active user endpoints from the previous 30 days were active that day\.

**Session heat map**  
The days and times at which user endpoints were active based on each user's local time\. Darker colors represent greater numbers of active endpoints\.

## Revenue Charts<a name="analytics-revenue"></a>

The charts on the **Revenue** tab provide details about user purchase activity and the revenue that is generated by your app\.

**Revenue**  
Total spent within your app by all users\.

**Revenue per user**  
The average revenue from each app user\.

**Paying users**  
Users who made one or more purchases by using your app\.

**Revenue per paying user**  
The average revenue from each paying user\.

**Units sold**  
Total items purchased within your app by all users\.

**Revenue per unit sold**  
The average revenue from each unit sold\.

**Purchases**  
Number of times users made a purchase by using your app\.

**Units per purchase**  
The average number of units sold with each purchase\.

## Users Charts<a name="analytics-users"></a>

The charts on the **Users** tab provide app usage metrics for endpoints and users, and they provide metrics about user authentication\. For example, a user who uses your app on multiple devices counts as one user in the **Daily Active Users** chart, but each of the user's devices counts as one endpoint in the **Daily Active Endpoints** chart\.

You can enable several of the metrics on this tab by using Amazon Cognito user pools to manage user authentication\. User pools provide user directories that make it easier to add sign\-up and sign\-in to your app\. As users authenticate with your app, Amazon Cognito reports data to Amazon Pinpoint, including sign\-ups, sign\-ins, failed authentications, daily active users, and monthly active users\. For more information, see [Using Amazon Pinpoint Analytics with Amazon Cognito User Pools](http://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-pinpoint-integration.html) in the *Amazon Cognito Developer Guide*\.

If you don't want to use Amazon Cognito user pools, to view analytics about users, you must assign user IDs to your endpoint definitions\. To view analytics about user authentication, your app must report the supported authentication event types to Amazon Pinpoint\.

**Daily active users**  
Users who opened your app on a specific day\.

**Daily active endpoints**  
User endpoints active on a specific day\.

**Monthly active users**  
Users who opened your app in the previous 30 days\.

**Monthly active endpoints**  
User endpoints active in the previous 30 days\.

**Active users month\-to\-date**  
Users who opened your app after the start of the current calendar month\.

**Sign\-ins**  
Number of times users signed in to your app\.

**Sign\-ups**  
Number of times users signed up for your app\.

**Authentication failures**  
Number of failed authentication calls\.