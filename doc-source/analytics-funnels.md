# Funnel Analytics<a name="analytics-funnels"></a>

You can use Amazon Pinpoint to analyze *funnels*, which visualize how many users complete each of a series of steps in your app\. For example, the series of steps in a funnel can be a conversion process that results in a purchase \(as in a shopping cart\), or some other intended user behavior\.

By monitoring funnels, you can assess whether conversion rates have improved because of changes made to your app or because of an Amazon Pinpoint campaign\.

After you specify which steps belong in your funnel, the **Create funnel** page displays a chart like the following example:

![\[A bar chart depicting each step in a funnel.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/funnel.png)![\[A bar chart depicting each step in a funnel.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[A bar chart depicting each step in a funnel.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

This example chart shows the percentage of users who complete each step in the process of updating an app\. By comparing the values between columns, you can determine the drop off rates between steps\. In this example, there is a 35% drop off between users who receive a notification and those who start an app session\. Then there is a 19% drop off between users who start a session and those who open the app settings page\.

To create a funnel, you specify each event that is part of the conversion process you want to analyze\. Your app reports these events to Amazon Pinpoint as long as it integrates Amazon Mobile Analytics through one of the supported AWS SDKs\. If your app is a project in AWS Mobile Hub, you integrate Amazon Mobile Analytics by enabling the [App Analytics](http://docs.aws.amazon.com/mobile-hub/latest/developerguide/app-analytics.html) feature in the AWS Mobile Hub console\.

When you add events to your funnel, you can choose any event that is reported by your app\. Your app can report the following types of events: 
+ Standard events – Includes events that automatically report when an app session starts or stops\. The event type names for standard events are denoted with an underscore prefix, as in `_session.start`\. Standard events also include monetization events that report in\-app purchases\.
+ Custom events – Defined by you to monitor activities specific to your app, such as completing a level in a game, posting to social media, or setting particular app preferences\.

For information about creating events using the AWS Mobile SDK for Android or the AWS Mobile SDK for iOS, see [Generating Mobile Analytics Events](http://docs.aws.amazon.com/mobileanalytics/latest/ug/generating-analytics-events-sdk.html) in the *Amazon Mobile Analytics User Guide*\.

**To create a funnel**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the Amazon Pinpoint homepage, choose the app that you want to create a funnel for\.

1. In the navigation panel, under **Analytics**, choose **Funnels**\.

1. Choose **Create funnel**\.

1. For **Funnel name**, type a name for the funnel\.

1. Choose the events that you want to add to the funnel chart\. For each event, specify the following:
   + **Name** – A name for the funnel chart\.
   + **Event** – The event type reported by your app to Amazon Pinpoint\.
   + **Attributes** – The attribute\-value pairs that are assigned to the events you want to add to the chart\.  
![\[The tabs on the Analytics page.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/funnel_eventbox.png)![\[The tabs on the Analytics page.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The tabs on the Analytics page.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. To add more events, choose the **add** \(\+\) button\. You can also copy an event by choosing the **copy** \(![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/analytics_funnel_event_copy_button.png)\) icon\.