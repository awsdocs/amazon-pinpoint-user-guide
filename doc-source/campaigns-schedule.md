# Step 4: Choose when to send the campaign<a name="campaigns-schedule"></a>

After you write your message, you can specify when the campaign should be sent\. You can choose to send the campaign immediately, at a scheduled date and time, on a recurring basis, or when certain events occur\.

When you create a campaign, you choose a *segment* to send that campaign to\. A segment is a group of your customers that share certain attributes\. For example, a segment might contain all of your customers who use version 2\.0 of your app on an Android device, or all customers who live in the city of Los Angeles\. 

**Topics**
+ [Scheduling an email, SMS, voice message, push, or custom campaign](#campaigns-schedule-no-inapp)
+ [Scheduling an in\-app campaign](#campaigns-schedule-inapp)

**Prerequisite**  
Before you begin, complete [Step 3: Configure the message](campaigns-message.md)\.

## Scheduling an email, SMS, voice message, push, or custom campaign<a name="campaigns-schedule-no-inapp"></a>

**Topics**
+ [Sending the campaign immediately](#campaigns-schedule-immediate)
+ [Sending the campaign at a specific date and time](#campaigns-schedule-once)
+ [Sending the campaign on a recurring basis](#campaigns-schedule-recurring)
+ [Sending the campaign when events occur](#campaigns-event-triggered)
+ [Best practices for using event\-based campaigns](#campaigns-event-triggered-best-practices)

If you want to send the campaign as soon as you finish creating it, you can choose to send the campaign immediately\.

### Sending the campaign immediately<a name="campaigns-schedule-immediate"></a>

If you want to send the campaign as soon as you finish creating it, you can choose to send the campaign immediately\.

**To send the campaign immediately**

1. Under **When should the campaign be sent**, choose **At a specific time**\.

1. Under **How often should the campaign be sent**, choose **Immediately**\.

1. Choose **Next** to continue to the final step\.

### Sending the campaign at a specific date and time<a name="campaigns-schedule-once"></a>

If you want to send a campaign only once, you can schedule it to be sent at a specific date and time\.

**To send the campaign at a specific date and time**

1. Under **When should the campaign be sent**, choose **At a specific time**\.

1. Under **How often should the campaign be sent**, choose **Once**\. 

1. For **Start date and time**, choose the date and time when Amazon Pinpoint should send the message\.

1. Under **Time zone**, choose the time zone that you want to use to schedule the campaign\. Optionally, choose **Use recipient's local time** to base the delivery time on each recipient's local time zone\.

1. Choose **Next** to continue to the final step\.

### Sending the campaign on a recurring basis<a name="campaigns-schedule-recurring"></a>

You can also schedule the campaign to be sent on a recurring basis\. You can specify the frequency and the start and end dates for the campaign\.

**To send the campaign on a recurring basis**

1. Under **When should the campaign be sent**, choose **At a specific time**\.

1. Under **How often should the campaign be sent**, choose how often Amazon Pinpoint should send the recurring campaign\. For example, to send the campaign once per week, choose **Weekly**\.

1. For **Start date and time**, choose the date and time when Amazon Pinpoint should send the first message in the recurring series\.

1. For **End date and time**, choose the date and time when Amazon Pinpoint should stop sending recurring messages\.

1. Under **Time zone**, choose a time zone to base the start and end times on\. Optionally, choose **Use recipient's local time** to base the delivery time on each recipient's local time zone\.

1. Choose **Next** to continue to the final step\.

### Sending the campaign when events occur<a name="campaigns-event-triggered"></a>

If you want to send the campaign when customers take certain actions, you can configure the campaign to be sent when a specific event occurs\. For example, campaigns can be sent when a customer registers a new account, or when a customer adds an item to their shopping cart but doesn't purchase it\. To learn more about sending events from your apps to Amazon Pinpoint, see [Reporting events in your application](https://docs.aws.amazon.com/pinpoint/latest/developerguide/integrate-events.html) in the *Amazon Pinpoint Developer Guide*\.

**Note**  
You can send event\-based messages only if your campaign uses dynamic segments \(as opposed to imported segments\)\. In addition, if you integrate your app with Amazon Pinpoint by using an AWS Mobile SDK, messages from event\-based campaigns are sent only to customers whose apps are running AWS Mobile SDK for Android version 2\.7\.2 or later, or AWS Mobile SDK for iOS version 2\.6\.30 or later\.

**To configure a campaign to be sent when an event occurs**

1. Under **When should the campaign be sent**, choose **When an event occurs**\.

1. For **Events**, choose the name of the event that initiates the campaign\.

1. \(Optional\) For **Attributes** and **Metrics**, choose the specific characteristics that initiate the campaign\.
**Tip**  
The more event data you capture from your users, the more options you have when you set up event triggers\. Event attributes and metrics are available only if you've provided those values to Amazon Pinpoint\. To learn more about capturing event data, see [Reporting events in your application](https://docs.aws.amazon.com/pinpoint/latest/developerguide/integrate-events.html) in the *Amazon Pinpoint Developer Guide*\.

1. Under **Campaign Dates**, for **Start date and time**, choose a start date\. Amazon Pinpoint sends the campaign only if the event that you specified earlier occurs after the start date\.
**Note**  
The **Start date and time** that you choose must be at least 15 minutes in the future\.

1. For **End date and time**, choose an end date\. Amazon Pinpoint sends the campaign only if the event that you specified earlier occurs before the end date\.

1. Under **Time zone**, choose a time zone to base the start and end dates on\.

1. Choose **Next** to continue to the final step\.

### Best practices for using event\-based campaigns<a name="campaigns-event-triggered-best-practices"></a>

There are a few restrictions and best practices that you should consider when you create event\-based campaigns:
+ You can create an event\-based campaign only if you chose a dynamic segment \(as opposed to an imported segment\) in [Step 2](campaigns-segment.md)\.
+ If you integrate your app with Amazon Pinpoint by using an AWS Mobile SDK, your app should use the following versions of the SDK in order to work properly with event\-based campaigns: 
  + AWS Mobile SDK for Android version 2\.7\.2 or later
  + AWS Mobile SDK for iOS version 2\.6\.30 or later

  Because of this restriction, we recommend that you set up your segments to include only customers who use a version of your app that runs a compatible version of the SDK\.
+ Choose your events carefully\. For example, if you send an event\-based campaign every time a `session.start` event occurs, you might quickly overwhelm your users with messages\. You can limit the number of messages that Amazon Pinpoint sends to a single endpoint in a 24\-hour period\. For more information, see [General settings](settings-general.md)\.

 

## Scheduling an in\-app campaign<a name="campaigns-schedule-inapp"></a>

This section contains information about setting up the parameters of your in\-app message using the Amazon Pinpoint console\. These parameters include setting up the following:
+ **Trigger event** – A trigger event is an action a customer performs that makes your in\-app message display\. Trigger events might include opening an app, making a purchase, or opening a menu\. With trigger events, you can see what users are doing within apps, and use that information to improve the apps\.
+ **Conversion event** – Conversion events help you get your website visitors to become customers, and can help you keep current customers\. Use conversion events alone, or use them with trigger events\. After you add conversion events, you can view their performance on the [campaign analytics](analytics-campaigns.md) page of the Amazon Pinpoint console\. A conversion is recorded for analytics when a user views your in\-app message and performs the action set by the conversion event\.

**Topics**
+ [Define triggers and set campaign start and end dates](#campaigns-inapp-trigger)
+ [\(Optional\) Change campaign global settings](#campaigns-inapp-settings)

### Define triggers and set campaign start and end dates<a name="campaigns-inapp-trigger"></a>

**To set a trigger event**

1. Add the **Trigger event ** that initiates the campaign\. You can manually enter a trigger event name, or choose an existing trigger from the dropdown list\. For example, to show a message to a user who purchases something from your online store, enter *Purchase*\.

   At this point, you don't need to enter any additional information, such as attributes or conversions\. The *Purchase* trigger event displays your in\-app campaign message to anyone who makes an online purchase\.

1. \(Optional\) Add event attributes\. An event attribute is used to refine a trigger\. It consists of an attribute name and a value\. For example, to narrow down the *Purchase* trigger event, you can add an attribute that displays the in\-app message to customers who purchase a specific item\. Imagine that the item is a pair of gardening gloves that cost $10 USD or more\. For **Attribute**, choose *item*, and then for **Value**, choose *gardening gloves*\. \(You set the event **Metric** for the cost in Step 3\.\)

   To further narrow down who gets your in\-app message, choose **Add new attribute** and add additional attributes and values\. If an attribute has multiple possible values, you must add each attribute and value pair separately\. 

   When you use the same attribute multiple times with different values, Amazon Pinpoint processes the campaign attributes using "or" between the values\. 

1. \(Optional\) Choose an event **Metric**\. This event typically uses a range of numbers, such as a duration or a cost\. After entering the event, choose one of the following **Operator** options:
   + **is equal to**
   + **is greater than**
   + **is less than**
   + **is greater than or equal to**
   + **is less than or equal to**

   Enter the **Value** for the operator\. Only numeric values are supported\. For example, enter the following values for the *Purchase* trigger\. For **Metric**, choose *Price*, and for the **Operator**, choose **is greater than or equal to**\. For the value, choose *10*\. The in\-app message now displays to any user that purchases gardening gloves at $10 USD or more\. 
**Note**  
You can use only a single metric in an in\-app message\.

1. Under **Campaign Dates**, for **Start date and time**, choose a start date\. Amazon Pinpoint sends the campaign only if the event that you previously specified occurs after the start date\.
**Note**  
The **Start date and time** that you choose must be set 15 minutes or more in the future\.

1. For **End date and time**, choose an end date\. Amazon Pinpoint sends the campaign only if the event that you previously specified occurs before the end date\.

1. Under **Time zone**, choose a time zone to base the start and end dates on\.

### \(Optional\) Change campaign global settings<a name="campaigns-inapp-settings"></a>

Campaign global settings determine how often a message is displayed to a user\. Customers might not want to see the same in\-app message every time they initiate a trigger event\. Alternatively, you might want to set the number of times that a customer sees your in\-app message\.

**To change global settings for the campaign**

1. For **Maximum number of session messages viewed per endpoint**, specify the number of times a customer should see your in\-app message during a session\. A session is defined as the period of time when a customer interacts with your application\. Set a level from *0* to *10*, with *0* displaying the message during an unlimited number of sessions\. For example, if you enter a value of *2*, then your customer sees your in\-app message during two separate sessions only\. If your customer interacts with your app for a third session, the in\-app message is not displayed\. 

1. For **Maximum number of daily messages viewed per endpoint**, choose **Override default setting**\. Then, set the number of times during a day that a customer sees your message\. Set a level from *0* to *10*, with *0* displaying the message an unlimited number of times during the day\. For example, if you enter a value of *2*, then your customer sees your in\-app message only twice during a 24\-hour period\.

1. For **Maximum number of session messages viewed per endpoint**, choose **Override default setting**\. Then, set the number of in\-app messages a customer can see\. If you send out multiple in\-app messages, you might want to restrict the number of messages that an endpoint displays\. Set a level from *0* to *10*, with *0* displaying an unlimited number of messages\. For example, if you enter a value of *2*, then your customers only see two in\-app messages, regardless of how many you send out\. 

**Next**  
[Step 5: Review and launch the campaign](campaigns-review.md)