# Step 4: Set the Campaign Schedule<a name="campaigns-schedule"></a>

Schedule when and how often the campaign sends your message to your segment\. By default, a campaign sends its message just once on the date and time you choose\.

You create a recurring campaign by selecting a **Frequency**, which sets the time interval between successive deliveries of the message\. A recurring campaign runs for a fixed duration, beginning and ending when you specify\. 

If you chose to create a standard campaign, you set only one schedule\. After you launch the campaign, you can change any of the schedule's settings except for the frequency\.

If you chose to create an A/B test for your campaign's schedule, you define two or more *treatments*, which are variations of the schedule that apply to different portions of the segment\. You cannot revise your treatments after you launch the campaign\.

**Prerequisite**  
Before you begin, complete [Step 3: Write the Message](campaigns-message.md)\.

**To set a schedule**

1. Select the frequency with which the campaign runs\. The default selection is once, but you can choose a recurring frequency \(such as **Weekly**\), or you can choose **Immediate** to send the message when you launch the campaign\.  
![\[The schedule frequency options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/campaigns_frequency.png)![\[The schedule frequency options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The schedule frequency options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. Unless you are sending the message immediately, choose when the message is sent:

   + If you chose to send the message only once, for **When**, select the date, time, and time zone\.

   + If you chose a recurring frequency, for **Start**, select the date, time, and time zone for the beginning of the campaign\. The default date is the current date and the default time is immediately \(approximately 15 minutes from the current time\)\. For **End**, select a date and time to end the campaign\.  
![\[The settings for the schedule start and end.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/campaigns_schedule.png)![\[The settings for the schedule start and end.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The settings for the schedule start and end.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. Enable **User’s local time** if you want to make the schedule take effect according to each recipient’s local time\. For example, if the campaign start time is 2:00 PM, and the time zone is UTC\-05:00 \(Eastern Standard Time\), then recipients in New York receive the message at 2:00 PM in their local time\. One hour later, when the campaign sends its message for UTC\-06:00 \(Central Standard Time\), users in Kansas City receive the message at 2:00 PM in their local time\.

   Disable **User’s local time** if you want all recipients to receive the message simultaneously, regardless of their local time\. For example, this can be useful if you want to send a critical alert to all of your organization’s employees at the same moment\.

1. For **Quiet Time Start** and **Quiet Time End**, set the time interval during which your campaign sends no messages\. For example, set a quiet time to ensure users receive no messages at night\. The quiet time takes effect in each user's local time, regardless of whether the **User's local time** option is disabled\.

1. If you are creating an A/B test for the campaign schedule, use the following steps\. Otherwise, choose **Next step** to move on to the final step\.

**To create a schedule A/B test**

1. To help you start, Amazon Pinpoint provides two treatments\. If you want more treatments, choose **Add more**\.  
![\[Amazon Pinpoint provides two treatments to get you started, and you can add more.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/campaigns_allocation.png)![\[Amazon Pinpoint provides two treatments to get you started, and you can add more.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[Amazon Pinpoint provides two treatments to get you started, and you can add more.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. For each treatment, do the following:

   1. Customize the treatment name to make it easy to recognize later\.

   1. Set the schedule\. 

   1. Set the **Treatment Allocation** to specify the percentage of users in the segment who will receive messages according to the treatment's schedule\.

      As you set the allocation for each treatment, the **Holdout** value adjusts to represent the total percentage of users who will not receive messages delivered by the campaign\.

1. When you are finished defining your treatments, choose **Next step**\.

**Next**  
[Step 5: Review and Launch the Campaign](campaigns-review.md)