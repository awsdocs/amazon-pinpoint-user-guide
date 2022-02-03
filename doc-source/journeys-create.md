# Create a journey<a name="journeys-create"></a>

The Amazon Pinpoint console lets you create powerful journeys through an easy\-to\-use graphical editor\. The first step in building your journey is to create and configure it\. You can configure the journey to begin immediately, or at a certain date and time\. You can also configure it to end at a specific date and time\.

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

   1. Choose **Save**\. At this point, you can [set up the journey entry activity](journeys-entry-activity.md)\. The journey entry activity determines the conditions that cause participants to enter your journey\.

**Next**: [Set up the journey entry activity](journeys-entry-activity.md)