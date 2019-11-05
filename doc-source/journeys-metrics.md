# View Journey Metrics<a name="journeys-metrics"></a>

After you publish a journey, the **Journey metrics** pane appears on the left side of the journey workspace, and Amazon Pinpoint begins to capture metrics related to the journey\. At the top of the **Journey metrics** pane, you can choose from the following metrics categories:
+ [Execution metrics](#journeys-metrics-execution) – These metrics provide information about how many endpoints were added to your journey, as well as the reasons that qualified endpoints were excluded from the journey\.
+ [Engagement metrics](#journeys-metrics-engagement) – These metrics provide information about how journey participants interacted with the messages that were sent from your journeys\.
**Note**  
Engagement metrics depend on email 

## Execution Metrics<a name="journeys-metrics-execution"></a>

Journey execution metrics include information about the endpoints that entered \(or were prevented from entering\) your journey\. To view engagement metrics, choose **Engagement metrics** in the **Journey metrics** pane\.

These metrics are divided into several sections, which are discussed in more detail in the folloing sections\.

### Entry Metrics<a name="journeys-metrics-execution-entries"></a>

The first section in the list of execution metrics shows you how many participants entered your journey\. An example of this section is shown in the following image\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-metrics-execution-entries.png)

This section contains the following information: 
+ **Currently in journey** – The number of participants that are actively proceeding through the activities in the journey\.
+ **Completed journey** – The number of participants who have reached an End activity in the journey\. 
+ **Lifetime journey entries** – The number of participants that have entered into the journey since the start date of the journey\.

This section also contains a chart that compares the percentage of participants who completed the journey \(shown in blue\) versus the percentage of participants who are still in the journey \(shown in orange\)\.

### Journey Settings<a name="journeys-metrics-execution-settings"></a>

The next section in the list of execution metrics includes information about some important settings for the journey\. An example of this section is shown in the following image\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-metrics-execution-settings.png)

This section contains the following information: 
+ **Max\. daily messages per endpoint** – The maximum number of messages that you can send to a single endpoint from the journey in a 24\-hour period\.
+ **Max\. journey entries per endpoint** – The maximum number of times a single endpoint can participate in a journey\.
+ **Max\. messages per second** – The maximum number of email messages that the journey can send per second\.

### Unsent Message Metrics<a name="journeys-metrics-execution-unsent-messages"></a>

The next section in the list of execution metrics includes information about the reasons that messages weren't sent to journey participants\. An example of this section is shown in the following image\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-metrics-execution-unsent-messages.png)

This section contains the following information: 
+ **Exceeded max entries per endpoint** – The number of participants who were prevented from participating the journey because they would have exceeded the maximum number of times a single endpoint can participate in a journey\.
+ **Exceeded endpoint message limit** – The number of messages that weren't sent because they would have exceeded the maximum number of messages that a single participant can receive in a 24\-hour period\.
+ **Sent during quiet time** – The number of messages that weren't sent because they would have been delivered during the quiet hours in the recipient's time zone\.
+ **Held out** – The number of participants that were removed from the journey on a **Holdout** step\.

### Message Failure Metrics<a name="journeys-metrics-execution-message-failures"></a>

The final section in the list of execution metrics includes information about the number of messages that couldn't be delivered because of system issues or issues related to your Amazon Pinpoint account\. An example of this section is shown in the following image\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-metrics-execution-message-failures.png)

This section contains the following information: 
+ **Permanent failure** – The number of messages that weren't sent because of a permanent failure\.
+ **Transient failure** – The number of messages that weren't sent because of a temporary failure\.
+ **Service failure** – The number of messages that weren't sent because of an issue with the Amazon Pinpoint service\.
+ **Unknown failure** – The number of messages that weren't sent because of an unknown reason\.
+ **Throttled** – The number of messages that weren't sent because they would have exceeded the sending limits for your Amazon Pinpoint account\.

## Engagement Metrics<a name="journeys-metrics-engagement"></a>

Journey engagement metrics include information about the ways in which the participants in your journey interacted with the messages that were sent from the journey\.

**Important**  
Several of the engagement metrics are based on information that we receive from recipients' email providers\. Different email providers have different practices for providing us with this data\. Some providers send us this information immediately, while others send it infrequently\. After we receive this data, there is a delay of up to two hours while we process the incoming metrics\.

### Email Response Metrics<a name="journeys-metrics-engagement-response"></a>

The first section in the list of engagement metrics provides email response metrics\. An example of this section is shown in the following image\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-metrics-engagement-response.png)

This section contains the following information: 
+ **Total messages sent** – The number of messages that Amazon Pinpoint attempted to send\.
+ **Total deliveries** – The number of messages that were delivered to their recipients\.
+ **Total opens** – The number of messages that were opened in the recipient's email client\.
**Note**  
In order for Amazon Pinpoint to count an email open event, the recipient has to load the images in your messages\. Several email clients, such as some versions of Microsoft Outlook, prevent images from being loaded by default\.  
Each time the recipient opens the email, it's counted as a distinct event\. For example, if a recipient opens a message five times, then Amazon Pinpoint counts five distinct open events\. For this reason, it's possible \(but unlikely\) for the number of opens to exceed the number of sends or deliveries\.
+ **Total clicks** – The number of messages in which the recipient clicked a link\.
**Note**  
Amazon Pinpoint counts each click as a separate event\. For example, if a recipient clicks three links in an email, then Amazon Pinpoint counts three distinct click events\. For this reason, it's possible for the number of clicks to exceed the number of opens or deliveries\.

### Message Engagement Metrics<a name="journeys-metrics-engagement-message"></a>

The final section in the list of engagement metrics provides additional email response metrics\. An example of this section is shown in the following image\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-metrics-engagement-message.png)

This section contains the following information: 
+ **Emails soft bounced** – The number of messages that resulted in a soft bounce\. A soft bounce occurs when a message can't be delivered because of a temporary issue \(for example, when the recipient's inbox is full\)\.
**Note**  
Amazon Pinpoint attempts to re\-deliver messages that result in a soft bounce for a certain period of time\. If the message is delivered during one of these redelivery attempts, then the message is counted in the **Total deliveries** metric and removed from the **Soft bounces** metric\.
+ **Emails hard bounced** – The number of messages that resulted in a hard bounce\. A hard bounce occurs when a message can't be delivered because of a permanent issue \(for example, when the destination email address no longer exists\)\.
**Note**  
Soft bounces that can't be delivered after a certain period of time are converted to hard bounces\. For this reason, you might see the number of soft bounces decrease and the number of hard bounces increase\.
+ **Emails unsubscribed** – The number of messages that prompted the recipient to unsubscribe\.
**Note**  
In order for Amazon Pinpoint to count an unsubscribe event, the unsubscribe link in the email has to contain a special link tag \(a tag called `unsubscribeLinkTag`, as in the following example: `<a ses:tags="unsubscribeLinkTag:click;" href="http://www.example.com/unsubscribe">`\)\. Only links that contain this tag are counted as Unsubscribes\.
+ **Emails complained** – The number of messages that were reported by the recipient as unsolicited mail\.
**Note**  
This metric is based on complaint report data that we receive from recipients' email providers\. Some email providers send us complaint data immediately, while others send a weekly or monthly digest\.

### Activity Metrics<a name="journeys-metrics-activity"></a>

While viewing the metrics for a journey, you can choose individual activities in the journey to see metrics that apply only to that activity\. Different activities offer different metrics\.

#### Email Activity Metrics<a name="journeys-metrics-activity-email"></a>

Journey metrics for **Email** activities include the following information:
+ **Execution metrics** – The number of participants who were sent a message after visiting the Email activity\. Also includes the number of participants who weren't sent messages, and the reasons why the messages weren't sent\. For details of each of these metrics, see [Execution Metrics](#journeys-metrics-execution)\.
+ **Engagement metrics** – Information about participants' interactions with the messages that were sent from the Email activity, including the number of messages that were delivered, opened, clicked, that resulted in bounces, and more\. For details of each of these metrics, see [Engagement Metrics](#journeys-metrics-engagement)\.

#### Wait Activity Metrics<a name="journeys-metrics-activity-wait"></a>

Journey metrics for **Wait** activities include the following information:
+ **Wait completed** – The number of journey participants who have completed the **Wait** activity\.
+ **Wait date passed** – The number of journey participants who arrived on the **Wait** activity and immediately moved to the next activity because the wait date occurred in the past\.
+ **Currently waiting** – The number of participants who are currently waiting on the **Wait** activity\.

#### Yes/no Split Activity Metrics<a name="journeys-metrics-activity-yes-no-split"></a>

Journey metrics for **Yes/no split** activities include the following information:
+ **Total participants** – The number of journey participants who have passed through Multivariate split activity\.
+ Branch details – Shows the number of journey participants who were sent down each branch of the Multivariate split activity\.

#### Multivariate Split Activity Metrics<a name="journeys-metrics-activity-multivariate-split"></a>

Journey metrics for **Multivariate split** activities include the following information:
+ **Total participants** – The number of journey participants who have passed through Multivariate split activity\.
+ Branch details – Shows the number of journey participants who were sent down each branch of the Multivariate split activity\.

#### Holdout Activity Metrics<a name="journeys-metrics-activity-holdout"></a>

Journey metrics for **Holdout** activities include the following information:
+ **Total entered** – The number of journey participants who have passed through Holdout activity\.
+ **Participants held out** – The number of participants who exited the journey as a result of being held out by the Holdout activity\.

#### Random Split Activity Metrics<a name="journeys-metrics-activity-random-split"></a>

Journey metrics for **Random split** activities include the following information:
+ **Total participants** – The number of journey participants who have passed through **Random split** activity\.
+ Branch details – Shows the number of journey participants who were sent down each branch of the **Random split** activity\.