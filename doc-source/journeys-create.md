# Create a Journey<a name="journeys-create"></a>

The Amazon Pinpoint console lets you create powerful journeys through an easy\-to\-use graphical editor\. This section contains information about planning your journey, as well as information about creating your journey by using the Amazon Pinpoint console\.

## Step 1: Configure the Journey<a name="journeys-create-step-1-configure"></a>

The first step in building your journey is to create and configure it\. You can configure the journey to begin immediately, or at a certain date and time\. You can also configure it to end on a specific date and time\.

**To configure a journey**

1. On the **All projects** page, choose the Amazon Pinpoint that you want to create the journey in\.
**Note**  
In Amazon Pinpoint, segments and endpoints are unique to each project\. The project that you choose should contain the segments and endpoints that you want to engage with in this journey\.

1. In the navigation pane, choose **Journeys**\.

1. Choose **Create a journey**\. The journey workspace appears\.

1. On the **Actions** menu, choose **Settings**\. The **Journey settings** window appears\. An example of this window is shown in the following image\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-settings.png)

1. On the **Journey settings** window, do the following:

   1. For **Journey title**, enter a name that describes the journey\.

   1. \(Optional\) For **Start date and time** and **End date and time**, enter the date and times when the journey should start and end, respectively\. If you don't enter a start date, customers enter the journey 5 minutes after you launch it\. If you don't enter an end date, the journey runs continuously for up to 540 days \(approximately 18 months\)\.

   1. \(Optional\) For **Time zone**, choose the time zone that the start date and end date should be based on\. You only need to complete this step if you set a start date or end date\. Optionally, you can choose **Use recipient's local time** to use the time zone value in each endpoint record\.
**Note**  
Amazon Pinpoint automatically chooses a time zone from this list based on your location\.

   1. \(Optional\) Under **Advanced settings**, configure the following settings:
      + **Quiet time settings** – Choose **Override project\-level settings** to override the quiet hours settings for the project that contains this journey\. If a message would be sent to a journey participant between the **Start time** and **End time** that you specify, Amazon Pinpoint doesn't attempt to send the message\.
      + **Maximum daily messages per endpoint** – Choose **Override project\-level settings** to override the maximum daily message setting for the project that contains this journey\. If you specify a value in this section, Amazon Pinpoint will limit the number of messages that are sent to each individual endpoint\.
      + **Maximum number of journey messages per second ** – Choose **Override project\-level settings** to override the maximum messages per second setting for the project that contains this journey\. If you specify a value in this section, Amazon Pinpoint will limit the number of messages that the journey can send each second\. The value that you specify should be less than or equal to the maximum sending rate for your account\. You can find the maximum sending rate for your account on the [Email settings](settings-email.md) page in the Amazon Pinpoint console\.
      + **Maximum entries per endpoint** – Choose **Override project\-level settings** to override the maximum entry setting for the project that contains this journey\. If you specify a value in this section, Amazon Pinpoint will limit the number of times that a participant can enter the journey\. For example, if you specify a value greater than 1, a participant could enter a journey, complete several activities in the journey, arrive at an **End** activity, and start the journey over again\. If a participant is eligible for a journey, but they've already entered the journey the maximum number of times, they are prevented from entering the journey\.

   1. Choose **Save**\.

## Step 2: Set Up then Journey Entry Activity<a name="journeys-create-step-2-set-entry-activity"></a>

Now you can choose the segment that will participate in the journey\. You can optionally configure the **Journey entry** activity to add new journey participants by periodically searching for new segment members\.

**To set up the Journey entry activity**

1. Choose the **Journey entry** activity\. The following image shows what the **Journey entry** activity looks like when it's selected\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-entry-activity.png)

1. For **Segments**, choose the segment that you want to add to the journey\.
**Tip**  
You can only include one segment in the **Journey entry** activity\. If you need to add more segments, you can create a new segment that includes all of the segments that you want to add to the journey\. Then, later in the journey, you can use a **Multivariate split** action to divide the journey participants into separate groups based on their segment membership\.

1. \(Optional\) For **Specify how ofter to add new segment members**, choose how often the segment membership should be evaluated\. For example, if you choose **12 hours**, Amazon Pinpoint checks for new segment members every 12 hours\. During one of these checks, if Amazon Pinpoint finds any new segment members, it adds them to the journey\.

1. \(Optional\) For **Description**, enter some text that describes the activity\. When you save the activity, this text appears as its label\. 

1. Choose **Save**\.

## Step 3: Add Activities to the Journey<a name="journeys-create-step-3-add-activities"></a>

Activities are the most important parts of any journey\. Activities represent the steps that are applied to journey participants\. You can use activities to send messages to journey participants, or to split them into smaller groups, or just to wait for a period of time\. There are several different types of activities that you can add to your journeys\. This section provides basic information about adding activities to your journeys\. For detailed instructions for setting up each type of activity, see [Setting Up Journey Activities](#journeys-create-step-3-add-activities-procedures)\.

**To add steps to a journey**

1. Choose **Add activity**\.

1. For **Actions**, choose one of the following journey actions:
   + **Send email** – When a participant arrives on a **Send email** activity, Amazon Pinpoint sends them an email\. When you create a **Send email** activity, you specify an [email template](message-templates-creating-email.md)\. Email templates can include substitution values, helping you to create a more personalized experience\.
   + **Wait** – When a participant arrives on a **Send email** activity, they remain on that activity until a certain date, or for a specific amount of time\.
   + **Yes/no split** – Sends customers down one of two paths based on certain criteria\. For example, you can send all customers who read an email down one path, and all other customers down the other path\.
   + **Multivariate split** – Sends customers down one of up to four paths, based on certain criteria\. Customers who don't meet any of the criteria that you define go down an "Else" path\.
   + **Holdout** – Ends the journey for a specified percentage of users\.
   + **Random split** – Randomly sends customers down one of up to five paths\.
**Tip**  
Amazon Pinpoint automatically saves your journey every few minutes, and every time you configure an activity\. The text in the upper right corner of the screen tells you when your journey was last saved\. You can close the window that contains the journey workspace at any time and return to it later\.

   For procedures for setting up each of these types of activities, see [Setting Up Journey Activities](#journeys-create-step-3-add-activities-procedures)\.

### Setting Up Journey Activities<a name="journeys-create-step-3-add-activities-procedures"></a>

Each type of journey activity has separate components that you have to configure\. The following sections provide additional information about setting up each type of activity\.

#### Set Up an Email Activity<a name="journeys-create-step-3-add-activities-procedures-email"></a>

When a journey participant arrives on an **Email** activity, Amazon Pinpoint sends them an email immediately\. Before you can configure the email activity, you have to create an email template\. For more information about creating email templates, see [Creating Email Templates](message-templates-creating-email.md)\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-email-activity.png)

**To set up an email activity**

1. Choose the **Email** activity that you want to configure\.

1. For **Choose an email template**, choose the email template that you want recipients to receive\.
**Tip**  
You can send yourself a preview of the message template, even if your Amazon Pinpoint account doesn't contain an endpoint record for your email address\. To send a preview, choose **Send a test message**\.

1. For **Sender email address**, choose the email address that you want to send the message from\. This list contains all of the verified email addresses for your Amazon Pinpoint account in the current AWS Region\. For information about verifying additional email addresses or domains, see [Verifying Email Identities](channels-email-manage-verify.md)\.

1. \(Optional\) For **Description**, enter some text that describes the message you're sending\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set Up a Wait Activity<a name="journeys-create-step-3-add-activities-procedures-wait"></a>

When a journey participant arrives on a **Wait** activity, they remain on that activity for a certain period of time, or until a specific date and time\. This type of activity is a useful way to schedule the sending of time\-sensitive communications, or to give customers time to interact with messages that you sent earlier in the journey\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-wait-activity.png)

**To set up a Wait activity that waits for a period of time**

1. Choose the **Wait** activity that you want to configure\.

1. Choose one of the following options:
   + **For a period of time** – Choose this option if you want journey participants to remain on this activity for a certain amount of time\. Then, for **Wait for this period of time**, enter the amount of time that you want journey participants to wait on this activity before they proceed to the next activity\. You can specify a value as short as 1 hour, or as long as 365 days\.
   + **Until a specific date** – Choose this option if you want journey participants to remain on this activity until a specific date and time\. Then, for **Wait until the following date**, enter the date and time when journey participants should move to the next activity\. You can choose any date up to End date of the journey\.

1. \(Optional\) For **Description**, enter some text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set Up a Yes/No Split Activity<a name="journeys-create-step-3-add-activities-procedures-yes-no-split"></a>

When journey participants arrive on a **Yes/no split** activity, they're sent down one of two paths based on their attributes or behaviors\. You can use this type of split to send journey travelers down separate paths based on their membership in a segment\. You can also send participants down separate paths based on their interactions with other journey activities\. For example, you can divide journey participants based on whether or not they opened an email that was sent earlier in the journey\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-yes-no-split-activity.png)

**To set up a Yes/no split activity**

1. Choose the **Yes/no split** activity that you want to configure\.

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
   + **Evaluate immediately** – If you choose this option, Amazon Pinpoint checks to see if the event condition that you specified has been met at the moment the journey participant arrives on the **Yes/no split** activity\.
   + **Evaluate after** – If you choose this option, Amazon Pinpoint waits for a specified period of time\. After the specified period of time has elapsed, Amazon Pinpoint checks to see if the event condition that you specified has been met\.
   + **Evaluate on** – If you choose this option, Amazon Pinpoint waits until a specific date and time\. When that date and time arrives, Amazon Pinpoint checks to see if the event condition that you specified has been met\.

1. \(Optional\) For **Description**, enter some text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set Up a Multivariate Split Activity<a name="journeys-create-step-3-add-activities-procedures-multivariate-split"></a>

When journey participants arrive on a **Multivariate split** activity, they're sent down one of several paths based on their attributes or behaviors\. This type of split is similar to a Yes/no split\. The advantage of using a Multivariate split activity is that it can evaluate more than one condition\. Additionally, every Multivariate split activity contains an "Else" branch\. Journey participants who don't meet any of the conditions that you specified in other branches are automatically sent down this branch\.

You can use this type of split to send journey travelers down separate paths based on their membership in a segment\. You can also send participants down separate paths based on their interactions with other journey activities\. For example, you can divide journey participants based on whether or not they opened an email that was sent earlier in the journey\.

**Note**  
If a journey participant meets more than one condition in a conditional split, they are sent down the first condition that they meet, in alphabetical order\. For example, if a participant meets the conditions in Branch A and Branch D, they're sent down the path that corresponds with Branch A\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-multivariate-split-activity.png)

**To set up a Multivariate split activity**

1. Choose the **Multivariate split** activity that you want to configure\.

1. Determine how many different paths you want to create\. Choose **Add another branch** to create additional branches\.

1. On each branch, for **Select a condition type**, choose one of the following options:
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

   Repeat this step for each branch in the **Multivariate split** activity\.

1. For **Condition evaluation**, choose when Amazon Pinpoint should evaluate the condition\. You can choose from the following options:
   + **Evaluate immediately** – If you choose this option, Amazon Pinpoint checks to see if the event condition that you specified has been met at the moment the journey participant arrives on the **Multivariate split** activity\.
   + **Evaluate after** – If you choose this option, Amazon Pinpoint waits for a specified period of time\. After the specified period of time has elapsed, Amazon Pinpoint checks to see if the event condition that you specified has been met\.
   + **Evaluate on** – If you choose this option, Amazon Pinpoint waits until a specific date and time\. When that date and time arrives, Amazon Pinpoint checks to see if the event condition that you specified has been met\.

1. \(Optional\) For **Description**, enter some text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set Up a Holdout Activity<a name="journeys-create-step-3-add-activities-procedures-holdout"></a>

When journey participants arrive on a **Holdout** activity, the journey ends for a random selection of participants\. You can specify the percentage of total journey participants who are held out\. **Holdout** steps help you to measure the impact of your journeys by creating control groups that don't receive your messages\. When a journey finishes running, you can compare the behaviors of the users who participated in the journey against those of the control group\.

**Note**  
Amazon Pinpoint uses a probability\-based algorithm to determine which journey participants are held out\. The percentage of journey participants who are held out will be very close to the percentage that you specify, but it might not be perfectly equal\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-holdout-activity.png)

**To set up a Holdout activity**

1. Choose the **Email** activity that you want to configure\.

1. For **Holdout percentage**, enter the percentage of journey participants who should be prevented from proceeding to the next activity in the journey\.

1. \(Optional\) For **Description**, enter some text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

#### Set Up a Random Split Activity<a name="journeys-create-step-3-add-activities-procedures-random-split"></a>

When journey participants arrive on a **Random split** activity, they're randomly sent down one of up to 5 paths\. You can use **Random split** activities to create between 2 and 5 separate paths\. This type of activity is useful when you want to measure the effectiveness of different message variants\.

**Note**  
Amazon Pinpoint uses a probability\-based algorithm to determine which journey participants are sent down each branch in a **Random split** activity\. The percentages of journey participants who are sent down each branch will be very close to the percentages that you specify, but they might not be perfectly equal\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-random-split-activity.png)

**To set up a Random split activity**

1. Choose the **Email** activity that you want to configure\.

1. Determine how many different paths you want to create\. Choose **Add another branch** to create additional branches\.

1. In the text field next to each branch, enter the percentage of journey participants who should be sent down that branch\. The values that you specify have to be positive numbers, and they can't contain decimals\. The sum of the values that you enter across all branches has to equal exactly 100%\.

1. \(Optional\) For **Description**, enter some text that describes the purpose of the activity\. When you save the activity, this text appears as its label\.

1. When you finish, choose **Save**\.

**Next**: [Review and Test a Journey](journeys-review-test.md)