# Create a journey<a name="journeys-create"></a>

The Amazon Pinpoint console lets you create powerful journeys through an easy\-to\-use graphical editor\. This section contains information about planning your journey, as well as information about creating your journey by using the Amazon Pinpoint console\.

## Step 1: Configure the journey<a name="journeys-create-step-1-configure"></a>

The first step in building your journey is to create and configure it\. You can configure the journey to begin immediately, or at a certain date and time\. You can also configure it to end at a specific date and time\.

**To configure a journey**

1. On the **All projects** page, choose the Amazon Pinpoint project that you want to create a journey in\.
**Note**  
In Amazon Pinpoint, segments and endpoints are unique to each project\. The project that you choose should contain the segments and endpoints that you want to engage with this journey\.

1. In the navigation pane, choose **Journeys**\.

1. Choose **Create journey**\. The journey workspace appears\.

1. On the **Actions** menu, choose **Settings**\. The **Journey settings** dialog box appears\. An example of this dialog box is shown in the following image\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-settings.png)

1. In the **Journey settings** dialog box, do the following:

   1. For **Journey title**, enter a name that describes the journey\.

   1. \(Optional\) For **Start date and time** and **End date and time**, enter the dates and times when the journey should start and end, respectively\. If you don't enter a start date, customers enter the journey 5 minutes after you launch it\. If you don't enter an end date, the journey runs continuously for up to 540 days \(approximately 18 months\)\.

   1. \(Optional\) For **Time zone**, choose the time zone that the start date and end date should be based on\. By default, Amazon Pinpoint chooses a time zone from this list based on your location\. You need to complete this step only if you set a start date or end date\.

      Optionally, choose **Use recipient's local time zone** to use the time zone value in the endpoint record for each participant\. Note, however, that a participant won't be included in the journey if you choose this option and the participant's endpoint record doesn't specify a time zone\.

      If you choose this option, you must specific a time zone for the participant's endpoint record in order for the participant to be included in the journey\.
**Note**  
**Use recipient's local time zone** is not supported for event\-triggered journeys\.

   1. Under **Advanced settings \- optional**, further refine your scheduling and message parameters, such as including a start and end date for the journey or setting quiet hours in which no messages are sent:
      + **Quiet time settings** – Choose **Enable quiet time** to enable quiet time for message delivery for this journey\. During quiet time, Amazon Pinpoint does not send messages to participants during the specified **Start time** and **End time** based on the end user's local timezone\. Choose the **Resume sending after quiet times** option to send any messages that were held from being sent during quiet time along with new messages\. If you do not choose **Resume sending after quiet time ends**, any messages held during quiet time are dropped and not sent\. Only new messages are sent after quiet time ends\.
**Note**  
SMS messages might take up to 5 minutes to process\. When configuring your quiet time hours, it's recommended to factor in a 5\-minute buffer to the **Start time**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-start-quiet-time.png)

   1. Under **Journey limits**, set options for message processing\. For example, this might be changing the number of journey messages per second or changing the number of entries per endpoint\. Endpoints will only re\-enter a journey if allowed by limits\. 
      + **Maximum daily messages per endpoint** – Choose **Override default setting** to override the maximum daily message setting for the project that contains this journey\. If you specify a value in this section, Amazon Pinpoint limits the number of messages that are sent to each individual endpoint\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-max-daily-endpoint.png)
      + **Maximum number of journey messages per second** – Choose **Override default setting** to override the maximum messages per second setting for the project that contains this journey\. If you specify a value in this section, Amazon Pinpoint limits the number of messages that the journey can send each second\. The value that you specify should be less than or equal to the maximum sending rate for your account\. You can find the maximum sending rate for your account on the [Email settings](settings-email.md) page on the Amazon Pinpoint console\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-max-journey-second.png)
      + **Maximum entries per endpoint** – Choose this setting to override the maximum entry setting for the project that contains this journey\. If you specify a value in this section, Amazon Pinpoint limits the number of times that a participant can enter the journey\. For example, if you specify a value greater than 1, a participant could enter a journey, complete several activities in the journey, arrive at an **End** activity, and start the journey again\. If a participant is eligible for a journey, but they've already entered the journey the maximum number of times, they are prevented from entering the journey again\. For example, if you have a maximum entry endpoint limit of **2**, and a participant has already entered and exited the journey two times, they will not re\-enter that journey again\.

        If you choose a value greater than **1** for the default, you can then choose and **Endpoint re\-entry interval**, setting how long to wait before an endpoint re\-enters a journey\. For example, you might set a re\-entry interval if you want to space out messages sent to your users, thus preventing your users from being spammed\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-max-entries-endpoint.png)

   1. Choose **Save**\. You're next prompted to set up the journey entry activity\.

## Step 2: Set up the journey entry activity<a name="journeys-create-step-2-set-entry-activity"></a>

Now you can choose the type of journey you're going to create\. You'll have one of two options for choosing the journey start:

### Add participants when they perform an activity<a name="journeys-create-add-from-activity"></a>

This event\-triggered journey type adds participants based on a chosen event\. You choose an event, such as music downloads, and then choose the event attributes to further define the journey event\. This might be downloading music from a specific artist\. When a user performs any of the activities described by the event, they become participants in the journey\.

**To add participants when they perform an activity**

1. Choose **Add participants when they perform an activity** if it is not already chosen\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-entry-activity-event.png)

1. For **Events**, choose an event from a list of events or type a new event to add it\. For example, you might want to trigger a journey when a user downloads a particular artist from your music service\. Let's call this event *artist\.download*\. A journey can include only one event\.

   Events can be submitted by using any of the following:
   + The PutEvents API\. See [Events ](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-events.html) in the Amazon Pinpoint API Reference
   + AWS Mobile SDK for Android: version 2\.7\.2 or later
   + AWS Mobile SDK for iOS: version 2\.6\.30 or later
**Note**  
If you're using either of the AWS Mobile SDKs you'll be limited to a set of events\. For the list of supported events, see [App events ](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams-data-app.html) in the Amazon Pinpoint Developer Guide\.

1. \(Optional\) An event attribute is a specific piece of information used to refine an event\. It's composed of an attribute name and a value\. We'll narrow down the *artist\.download* by adding an *artistName* attribute For **Attribute**, choose the attribute from the list\. Since you want to add participants based on specific a specific artist, you'd choose *artistName* as the **Attribute**, and then choose a specific artist for the **Value** – for example, *Bruce Springsteen*\. Your journey event now adds any participants from the *artist\.download* event and the *artistName* is *Bruce Springsteen*\.

   If you want to refine the journey even further, add additional attributes and values by choosing **Add new attribute** for each attribute you want to add\. If an attribute has multiple possible values, you must add each attribute and value pair separately\. For *artist\.download* event you now add in an additional *artistName* attribute, *Alicia Keys*\. Choose **Add new attribute**, again choose *artistName* as the attribute, and then choose *Alicia Keys* for the **Value**\. When you use the same attribute multiple times with different values, Amazon Pinpoint processes the journey attributes using "or" between the values\. Your journey event now adds any participants from the *artist\.download* event, and the *artistName* is either *Bruce Springsteen* or *Alicia Keys*\.

   You can add a combination of attributes with multiple values in addition to attributes with only a single value\. 

1. \(Optional\) Choose an event **Metric**\. This is an event that typically uses a range of numbers, such as a duration or a cost\. After entering the event, choose an **Operator**:
   + **is equal to**
   + **is greater than**
   + **is less than**
   + **is greater than or equal to**
   + **is less than or equal to**

   Enter the **Value** for the operator\. Only numeric values are supported\. Participants are added based on the metric, operator, and value\. For the *artist\.download* event you might add a *songLength* metric where you add participants when they download any song by either *Bruce Springsteen* or *Alicia Keys* and where the *songLength* is greater than or equal to *500 seconds*\.
**Note**  
You can't use the same metric with multiple values\.

1. \(Optional\) Select the dynamic segment to use for the journey\. You can have only one previously defined segment per journey entry\. In addition, for any endpoint to enter into the journey, that endpoint must be part of the chosen segment\. If you want to build a new segment for this journey, you can build that segment through the Amazon Pinpoint console\. For more information about segments, see [Building segments ](https://docs.aws.amazon.com/pinpoint/latest/userguide/segments-building.html)\.
**Note**  
Imported segments and dynamic segments based on an imported segment aren't supported\. The dropdown list indicates the type of segment\. While a segment displayed in the dropdown list might indicate it's dynamic, if it's based on an imported segment, you'll get an error

1. \(Optional\) For **Description**, enter text that describes the activity\. When you save the activity, this text appears as its label\. 

1. Choose **Save**\.

### Add participants from a segment<a name="journeys-create-add-from-segment"></a>

For this journey type you'll choose the segment that participates in the journey\. You can optionally configure the Journey entry activity to add new journey participants by periodically searching for new segment participants\.

**To add participants from a segment**

1. Choose **Add participants from a segment**\.   
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-entry-activity.png)

1. For **Segments**, choose the segment that you want to add to a journey\. A segment can be dynamic or imported\.
**Tip**  
You can include only one segment in the** Journey entry** activity\. If you need to add more segments, you can create a new segment that includes all of the segments that you want to add to the journey\. Then, later in the journey, you can use a multivariate split activity to divide journey participants into separate groups based on their segment membership\.

1. \(Optional\) For **Specify how often to add new segment members**, choose how often the segment membership should be evaluated and refreshed\. You can choose **Never**, or you can choose to check on a schedule you set\. For example, if you choose **Once every 12 hours**, Amazon Pinpoint checks for new segment members every 12 hours\. If Amazon Pinpoint finds any new segment members during one of these checks, it adds them to the journey\. Existing endpoints will also be re\-evaluated\. If the **Maximum entries per interval** is greater than 1, then existing endpoints will also re\-enter the journey\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-entry-activity-add.png)

1. \(Optional\) Choose **Refresh on segment update** adds any new journey endpoint updates to the segment before the refresh interval set in the previous step\. Any endpoints removed from the segment will not be processed if they do not enter the journey within 15 minutes\. If this option is not chosen, then segments are refreshed based on the how often to add new segment members from the previous step\.

   The following describes the behavior of the refresh on segment update and refresh interval\.
**Note**  
A refresh interval and refresh on segment update applies to both dynamic and imported segments\. For more information about these types of segments, see [Amazon Pinpoint segments](segments.md)\.
   +   
**Refresh on segment update is not chosen, and the refresh interval is set to Never**  
Only endpoints present in the original segment are processed\. Any endpoints added before the journey starts will be included\. Any dynamic segment endpoints added or removed after the journey starts will not be processed\.
   +   
**Refresh on segment update is not chosen, and a refresh interval is set**  
Any dynamic segment endpoints added, or are common across segment updates, are processed as long as it's allowed by other journey limits\. Removed endpoints are not processed by the journey\.
   +   
**Refresh on segment update is chosen, and the refresh interval is set to Never**  
If the journey is current processing endpoints, any changes to the segment are evaluated\. However, if the journey has already finished processing, any endpoints that were added or removed after the journey started will not be included\.
   +   
**Refresh on segment update is chosen, and a refresh interval is set**  
Any changes to the both dynamic and imported segments are evaluated and updated based on the refresh interval in addition to when any segment update occurs\. Any segment endpoints added, or are common across segment updates, are processed as long it's allowed by other journey limits\. Removed endpoints are not processed by the journey\.

1. \(Optional\) For **Description**, enter text that describes the activity\. When you save the activity, this text appears as its label\.

1. Choose **Save**\.

## Step 3: Add activities to the journey<a name="journeys-create-step-3-add-activities"></a>

Activities are the most important parts of any journey\. Activities represent the steps that are applied to journey participants\. You can use activities to send messages to journey participants across a variety of channels, or to split them into smaller groups, or to wait for a period of time\. There are several different types of activities that you can add to a journey\. This section provides basic information about adding activities to a journey\. For detailed information about setting up each type of activity, see [Setting up journey activities](#journeys-create-step-3-add-activities-procedures)\.

**Note**  
An exit journey element is added to the journey flow after reviewing and publishing your journey\.

**To add activities to a journey**

1. Choose **Add activity**\.

1. For **Add an activity**, choose one of the following types of journey activities:
   + **Send an email** – When a participant arrives on this type of activity, Amazon Pinpoint sends them an email\. When you create a **Send an email** activity, you specify an [ email template](message-templates-creating-email.md)\.
   + **Send a push notification** – When a participant arrives on this type of activity, Amazon Pinpoint sends them a push notification\. When you create a **Send a push notification** activity, you specify a [ push notification template](message-templates-creating-push.md)\. Push notification templates can include standard or raw messages\.
   + **Send an SMS message** – When a participant arrives on this type of activity, Amazon Pinpoint sends them an SMS message\. When you create a **Send an SMS message** activity, you specify an [ SMS message template](message-templates-creating-sms.md)\.
   + **Send through a custom channel** – When a participant arrives on this type of activity, Amazon Pinpoint sends them a message through any service that has an API, including third\-party services\. When you create a **Send through a custom channel** activity, you specify a Lambda function or a webhook URL to send your message\. Custom messages allow you to specify the endpoint types that will receive the message\. For more information about custom channels, see [ Creating Custom Channels](channels-custom.md) in the Amazon Pinpoint Developer Guide\.
   + **Wait** – When a participant arrives on this type of activity, they remain on the activity until a certain date or for a specific amount of time\.
   + **Yes/No split** – Sends customers down one of two paths based on certain criteria\. For example, you can send all customers who opened an email down one path, and all other customers down the other path\.
   + **Multivariate split** – Sends customers down one of up to four paths, based on certain criteria\. Customers who don't meet any of the criteria that you define go down an "Else" path\. Participants who meet the criteria in more than one branch will travel down the first branch that they qualify for\.
   + **Holdout** – Ends the journey for a specified percentage of users\.
   + **Random split** – Randomly sends customers down one of up to five paths\.
**Tip**  
Amazon Pinpoint automatically saves your journey every few minutes, and every time you configure an activity\. The text in the upper right corner of the screen tells you when your journey was last saved\. You can close the journey workspace at any time and return to it later\.

   For procedures for setting up each of these types of activities, see [Setting up journey activities](#journeys-create-step-3-add-activities-procedures)\.

### Setting up journey activities<a name="journeys-create-step-3-add-activities-procedures"></a>

Each type of journey activity has separate components that you have to configure\. The following sections provide additional information about setting up each type of activity\.

#### Set up an email activity<a name="journeys-create-step-3-add-activities-procedures-email"></a>

When a journey participant arrives on a **Send email** activity, Amazon Pinpoint sends them an email immediately\. Before you can configure an email activity, you have to create an email template\. For more information about creating email templates, see [Creating email templates](message-templates-creating-email.md)\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-email-activity.png)

**To set up an email activity**

1. Choose the **Send email** activity that you want to configure\.

1. For **Choose an email template**, choose the email template for the message that you want participants to receive\. Then, under **Template version behavior**, specify whether you want Amazon Pinpoint to automatically update the message to include any changes that you might make to the template before the message is sent\. To learn more about these options, see [Managing versions of message templates](message-templates-versioning.md)\.
**Tip**  
You can send yourself a preview of the message, even if your Amazon Pinpoint account doesn't contain an endpoint record for your email address\. To send a preview, choose **Send a test message**\.

1. For **Sender email address**, choose the email address that you want to send the message from\. This list contains all the verified email addresses for your Amazon Pinpoint account in the current AWS Region\. For information about verifying additional email addresses or domains, see [Verifying email identities](channels-email-manage-verify.md)\.
**Tip**  
To display a friendly sender name for the message, choose the default email address for the project\. A *friendly sender name* is the name that appears in participants' email clients when they receive the message\. To change the default email address for the project or the friendly sender name for that address, update the project's settings for the email channel\. To do this, choose **Settings** in the left navigation pane, and then choose **Email**\. Then, enter the settings that you want\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up a push notification activity<a name="journeys-create-step-3-add-activities-procedures-push"></a>

When a journey participant arrives on a **Send a push notification** activity, Amazon Pinpoint sends them a push notification immediately\. Before you can configure a push notification activity, you have to create a push notification template\. For more information about creating push notification templates, see [Creating push notification templates](message-templates-creating-push.md)\.

**Note**  
To send push notifications to journey participants, your app has to be integrated with an AWS SDK\. For more information, see [Handling Push Notifications](https://docs.aws.amazon.com/pinpoint/latest/developerguide/integrate-push.html) in the *Amazon Pinpoint Developer Guide*\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-create-step-3-add-activities-procedures-push.png)

**To set up a push notification activity**

1. Choose the **Send a push notification** activity that you want to configure\.

1. For **Choose an push notification template**, choose the push notification template for the message that you want participants to receive\. Then, under **Template version behavior**, specify whether you want Amazon Pinpoint to use the template version that is currently designated as active or the template version that was active when the journey was created\. To learn more about these options, see [Managing versions of message templates](message-templates-versioning.md)\.
**Tip**  
You can send yourself a preview of the message, even if your Amazon Pinpoint account doesn't contain an endpoint ID or device token that you specify\. To send a preview, choose **Send a test message**\.

1. \(Optional\) For **Time to live**, specify whether you want Amazon Pinpoint to use the default time to live \(TTL\) value or a custom value for each push notification service\. By default, Amazon Pinpoint uses the maximum TTL value of each respective push notification service\. You can also specify a custom TTL value for all push notification services\. If the message delivery fails, the push notification service attempts to deliver the message for the amount of time that you specify in this setting\. For information about specific time to live values, see [Messages](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-messages.html) in the *Amazon Pinpoint API Reference*\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up an SMS message activity<a name="journeys-create-step-3-add-activities-procedures-sms"></a>

When a journey participant arrives on a **Send an SMS message** activity, Amazon Pinpoint sends them an SMS message immediately\. Before you can configure an SMS activity, you have to create an SMS template\. For more information about creating SMS templates, see [Creating SMS templates](message-templates-creating-sms.md)\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-create-step-3-add-activities-procedures-sms.png)

**To set up an SMS message activity**

1. Choose the **Send an SMS message** activity that you want to configure\.

1. For **Choose an SMS message template**, choose the SMS message template for the message that you want participants to receive\. Then, under **Template version behavior**, specify whether you want Amazon Pinpoint to use the template version that is currently designated as active or the template version that was active when the journey was created\. To learn more about these options, see [Managing versions of message templates](message-templates-versioning.md)\.
**Tip**  
You can send yourself a preview of the message, even if your Amazon Pinpoint account doesn't contain an endpoint record for your phone number\. To send a preview, choose **Send a test message**\.

1. Choose **Send a test message** if you want to first test this activity\. Test messages don't count against your daily sending limits, but you are charged for each message\. When sending a test message you're prompted to optionally choose the origination number but required to choose a destination number\.
**Note**  
If your account is in the SMS sandbox, you can only send a test message to one of your verified destination numbers\. If the destination number doesn't appear in the list, choose **Manage numbers** to add that new number\. See [Amazon Pinpoint SMS sandbox](channels-sms-sandbox.md) for the steps to add and verify a destination number\.

1. For **Message type**, choose the type of message that you want to send\. You can choose transactional or promotional messages\.

1.  \(Optional\) For the **Origination phone number**, choose the number to use as the originator\. The originator can be any of your numbers: short code, 10DLC, or long code/toll\-free\. If you have multiple numbers associated with your account, and you do not choose an originator, Amazon Pinpoint will choose an originator for you based on the following order: short code, 10DLC, long code/toll\-free\. 

1. \(Optional\) For **Sender ID**, enter the alphanumeric ID that identifies the sender of the SMS message\. The sender ID will appear on your recipients’ devices only if the recipient is in an area where sender IDs are supported\. It is important to note that if you specify a sender ID in your journey activity, it will override the default value on the **SMS and voice settings** page\. To learn more about support for sender IDs, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up a custom message channel activity<a name="journeys-create-step-3-add-activities-procedures-custom"></a>

When a journey participant arrives on a **Send through a custom channel** activity, Amazon Pinpoint sends information about the participant to an AWS Lambda function or webhook\. A custom channel allows you to send messages to your customers through any service that has an API, including non\-AWS services\.

Before you can configure a custom channel activity, you you need to decide whether to use a Lambda function or a webhook URL to send your message\. For more information about creating custom message channels, see [Creating custom channels in Amazon Pinpoint](https://docs.aws.amazon.com/pinpoint/latest/developerguide/channels-custom.html) in the *Amazon Pinpoint Developer Guide*\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-create-step-3-add-activities-procedures-custom-lambda.png)

**To set up a custom message channel activity that calls a Lambda function**

1. Choose the **Send through a custom channel** activity that you want to configure\.

1. For **Choose the method that you want to use to send messages**, select **Execute a Lambda function**\.

1. For **Lambda function**, choose the function that you want to execute\.

1. For **Specify the endpoint types that will receive this message**, select the endpoint types that the custom channel applies to\. By default, only the **Custom** endpoint type is selected\. To add additional endpoint types, select **Choose endpoint types**\.
**Note**  
Other endpoint types that arrive at this activity are sent through it, but only the endpoint types that you specify are sent to the Lambda function or webhook\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-create-step-3-add-activities-procedures-custom-webhook.png)

**To set up a custom message channel activity that uses a webhook URL**

1. Choose the **Send through a custom channel** activity that you want to configure\.

1. For **Choose the method that you want to use to send messages**, select **Specify a webhook URL**\.

1. For **Webhook URL**, enter the address of the webhook that you want to execute\. For more information about configuring webhooks, see [Creating custom channels in Amazon Pinpoint](https://docs.aws.amazon.com/pinpoint/latest/developerguide/channels-custom.html) in the *Amazon Pinpoint Developer Guide*\.

1. For **Specify the endpoint types that will receive this message**, select the endpoint types that the custom channel applies to\. By default, only the **Custom** endpoint type is selected\. To add additional endpoint types, select **Choose endpoint types**\.
**Note**  
Other endpoint types that arrive at this activity are sent through it, but only the endpoint types that you specify are sent to the Lambda function or webhook\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up a wait activity<a name="journeys-create-step-3-add-activities-procedures-wait"></a>

When a journey participant arrives on a **Wait** activity, they remain on that activity for a certain period of time or until a specific date and time\. This type of activity is a useful way to schedule the sending of time\-sensitive communications, or to give customers time to interact with messages that you sent earlier in the journey\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-wait-activity.png)

**To set up a wait activity**

1. Choose the **Wait** activity that you want to configure\.

1. Choose one of the following options:
   + **For a period of time** – Choose this option if you want journey participants to remain on this activity for a certain amount of time\. Then, enter the amount of time that you want journey participants to wait on this activity before they proceed to the next activity\. You can specify a value that's as short as 1 hour or as long as 365 days\.
   + **Until a specific date** – Choose this option if you want journey participants to remain on this activity until a specific date and time\. Then, enter the date and time when journey participants should move to the next activity\. You can choose any date and time that precedes the end date of the journey\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up a Yes/No split activity<a name="journeys-create-step-3-add-activities-procedures-yes-no-split"></a>

When journey participants arrive on a **Yes/No split** activity, they're sent down one of two paths based on their attributes or behaviors\. You can use this type of split activity to send journey participants down separate paths based on their membership in a segment\. You can also send participants down separate paths based on their interactions with other journey activities\. For example, you can divide journey participants based on whether they opened an email that was sent earlier in the journey\.

**Note**  
To create split activities that send participants down different paths based on push notification events \(such as Open or Received events\), your mobile app has to specify the User ID and Endpoint ID values\. For more information, see [Integrating Amazon Pinpoint with your application](https://docs.aws.amazon.com/pinpoint/latest/developerguide/integrate.html) in the *Amazon Pinpoint Developer Guide*\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-yes-no-split-activity.png)

**To set up a yes/no split activity**

1. Choose the **Yes/No split** activity that you want to configure\.

1. For **Select a condition type**, choose one of the following options:
   + **Segment** – Choose this option to send all members of the chosen segment down the "Yes" path\. Then, for **Segments**, choose a segment\.
   + **Event** – Choose this option to send users down the "Yes" path based on their interactions with a previous step in this journey\. Then, complete the following steps:

     1. For **Events**, choose one of the following options:
        + **Email send** – Amazon Pinpoint accepted the message and will attempt to deliver it\.
        + **Email delivered** – The message was successfully delivered to the recipient\.
        + **Email rejected** – Amazon Pinpoint rejected the message because it contained a virus or malware\.
        + **Email hard bounce** – The email wasn't delivered to the recipient because of a permanent issue\. For example, the recipient's email address might not exist anymore\. When a message generates a hard bounce, Amazon Pinpoint doesn't attempt to re\-deliver it\.
        + **Email soft bounce** – The email wasn't delivered to the recipient because of a temporary issue\. For example, the recipient's inbox could be full, or their email provider might be experiencing a temporary issue\. When a soft bounce occurs, Amazon Pinpoint attempts to re\-deliver the message for a certain period of time\. If the message still can't be delivered, the message becomes a hard bounce\.
        + **Email complaint** – The recipient received the email, but used the "Report spam" or similar button in their email client to report the message as unwanted\.
**Note**  
Amazon Pinpoint relies on complaint reports from email providers to generate complaint events\. Some email providers give us these reports on a regular basis, while others send them infrequently\.
        + **Email open** – The recipient received the email and opened it\.
**Note**  
For Amazon Pinpoint to capture an **Email open** event, the recipient's email client has to download the images contained in the message\. Many common email clients, such as Microsoft Outlook, don't download email images by default\.
        + **Email click** – The recipient received the email and followed one of the links contained in the body of the message\.
        + **Email unsubscribe** – The recipient received the email and used the "Unsubscribe" link to opt out of future messages\.

     1. For **Choose an activity**, choose the activity that the split should be applied to\.

1. For **Condition evaluation**, choose when Amazon Pinpoint should evaluate the condition\. You can choose from the following options:
   + **Evaluate immediately** – If you choose this option, Amazon Pinpoint checks to see if the event condition that you specified has been met the moment when the journey participant arrives on the activity\.
   + **Evaluate after** – If you choose this option, Amazon Pinpoint waits for a specified period of time\. After the specified period of time has elapsed, Amazon Pinpoint checks to see if the event condition that you specified has been met\.
   + **Evaluate on** – If you choose this option, Amazon Pinpoint waits until a specific date and time\. When that date and time arrives, Amazon Pinpoint checks to see if the event condition that you specified has been met\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up a multivariate split activity<a name="journeys-create-step-3-add-activities-procedures-multivariate-split"></a>

When journey participants arrive on a **Multivariate split** activity, they're sent down one of several paths based on their attributes or behaviors\. This type of split is similar to a yes/no split\. The advantage of using a multivariate split activity is that it can evaluate more than one condition\. Additionally, every multivariate split activity contains an "Else" path\. Journey participants who don't meet any of the conditions that you specified in other paths are automatically sent down the "Else" path\.

You can use this type of split to send journey participants down separate paths based on their membership in a segment\. You can also send participants down separate paths based on their interactions with other journey activities\. For example, you can divide journey participants based on whether they opened an email that was sent earlier in the journey\.

**Note**  
If a journey participant meets more than one condition in a conditional split, they are sent down the first condition that they meet, in alphabetical order\. For example, if a participant meets the conditions in Branch A and Branch D, they're sent down the path that corresponds with Branch A\.  
To create split activities that send participants down different paths based on push notification events \(such as Open or Received events\), your mobile app has to specify the User ID and Endpoint ID values\. For more information, see [Integrating Amazon Pinpoint with your application](https://docs.aws.amazon.com/pinpoint/latest/developerguide/integrate.html) in the *Amazon Pinpoint Developer Guide*\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-multivariate-split-activity.png)

**To set up a multivariate split activity**

1. Choose the **Multivariate split** activity that you want to configure\.

1. Determine how many different paths \(branches\) you want to create\. Choose **Add another branch** to create additional paths\.

1. On each branch, for **Select a condition type**, choose one of the following options:
   + **Segment** – Choose this option to send all members of the chosen segment down the path\. Then, for **Segments**, choose a segment\.
   + **Event** – Choose this option to send users down the path based on their interactions with a previous step in this journey\. Then, complete the following steps:

     1. For **Events**, choose one of the following options:
        + **Email send** – Amazon Pinpoint accepted the message and will attempt to deliver it\.
        + **Email delivered** – The message was successfully delivered to the recipient\.
        + **Email rejected** – Amazon Pinpoint rejected the message because it contained a virus or malware\.
        + **Email hard bounce** – The email wasn't delivered to the recipient because of a permanent issue\. For example, the recipient's email address might not exist anymore\. When a message generates a hard bounce, Amazon Pinpoint doesn't attempt to re\-deliver it\.
        + **Email soft bounce** – The email wasn't delivered to the recipient because of a temporary issue\. For example, the recipient's inbox could be full, or their email provider might be experiencing a temporary issue\. When a soft bounce occurs, Amazon Pinpoint attempts to re\-deliver the message for a certain period of time\. If the message still can't be delivered, the message becomes a hard bounce\.
        + **Email complaint** – The recipient received the email, but used the "Report spam" or similar button in their email client to report the message as unwanted\.
**Note**  
Amazon Pinpoint relies on complaint reports from email providers to generate complaint events\. Some email providers give us these reports on a regular basis, while others send them infrequently\.
        + **Email open** – The recipient received the email and opened it\.
**Note**  
For Amazon Pinpoint to capture an **Email open** event, the recipient's email client has to download the images contained in the message\. Many common email clients, such as Microsoft Outlook, don't download email images by default\.
        + **Email click** – The recipient received the email and followed one of the links contained in the body of the message\.
        + **Email unsubscribe** – The recipient received the email and used the "Unsubscribe" link to opt out of future messages\.

     1. For **Choose an activity**, choose the activity that the split should be applied to\.

   Repeat this step for each path in the activity\.

1. For **Condition evaluation**, choose when Amazon Pinpoint should evaluate the condition\. You can choose from the following options:
   + **Evaluate immediately** – If you choose this option, Amazon Pinpoint checks to see if the event condition that you specified has been met at the moment the journey participant arrives on the activity\.
   + **Evaluate after** – If you choose this option, Amazon Pinpoint waits for a specified period of time\. After the specified period of time has elapsed, Amazon Pinpoint checks to see if the event condition that you specified has been met\.
   + **Evaluate on** – If you choose this option, Amazon Pinpoint waits until a specific date and time\. When that date and time arrives, Amazon Pinpoint checks to see if the event condition that you specified has been met\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up a holdout activity<a name="journeys-create-step-3-add-activities-procedures-holdout"></a>

When journey participants arrive on a **Holdout** activity, the journey ends for a random selection of participants\. You can specify the percentage of total journey participants who are held out\. Holdout activities can help you measure the impact of a journey by creating a control group that doesn't receive your messages\. When a journey finishes running, you can compare the behaviors of the users who participated in the journey against those who were part of the control group\.

**Note**  
Amazon Pinpoint uses a probability\-based algorithm to determine which journey participants are held out\. The percentage of journey participants who are held out will be very close to the percentage that you specify, but it might not be perfectly equal\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-holdout-activity.png)

**To set up a holdout activity**

1. Choose the **Holdout** activity that you want to configure\.

1. For **Holdout percentage**, enter the percentage of journey participants who should be prevented from proceeding to the next activity in the journey\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set up a random split activity<a name="journeys-create-step-3-add-activities-procedures-random-split"></a>

When journey participants arrive on a **Random split** activity, they're randomly sent down one of up to five paths\. You can create two to five separate paths for this type of activity\. This type of activity is useful when you want to measure the effectiveness of different message variants\.

**Note**  
Amazon Pinpoint uses a probability\-based algorithm to determine which journey participants are sent down each path in a random split activity\. The percentages of journey participants who are sent down each path will be very close to the percentages that you specify, but they might not be perfectly equal\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-random-split-activity.png)

**To set up a random split activity**

1. Choose the **Random split** activity that you want to configure\.

1. Determine how many different paths \(branches\) you want to create\. Choose **Add another branch** to create each additional path\.

1. In the field next to each branch, enter the percentage of journey participants who should be sent down that branch\. The values that you specify have to be positive numbers, and they can't contain decimals\. The sum of the values that you enter across all branches has to equal exactly 100%\.

1. \(Optional\) For **Description**, enter text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

**Next**: [Review and test a journey](journeys-review-test.md)