# Step 4: Set the Campaign Schedule<a name="campaigns-schedule"></a>

After you write your message, you can schedule when and how often the campaign sends your message to your segment\. By default, a campaign sends its message just once on the date and time you choose\.

You create a recurring campaign by selecting a frequency, which sets the time interval between successive deliveries of the message\. A recurring campaign runs for a fixed duration, beginning and ending when you specify\. 

**Prerequisite**  
Before you begin, complete [Step 3: Write the Message](campaigns-message.md)\.

**To set a schedule**

1. Under **How often should this campaign be sent?**, choose the frequency with which the campaign runs\. The default selection is **Immediately**, but you can choose a recurring frequency \(such as **Weekly**\), or you can choose **Once** to send the message at a specific date and time\.

1. If you choose to send the message at a specific time or on a recurring basis, specify when the message is sent:
   + If you chose **Once**, choose a **Start date and time**, as well as the **Time zone** that the start time is based on\. The date and time you choose represent the date and time at which Amazon Pinpoint sends your message\.

     If you want to ensure that the message arrives at the specified time in each recipient's time zone, choose **Use recipient's local time**\.
   + If you chose a recurring frequency, specify a **Start date and time** and an **End date and time**\. Also specify the **Time zone** that the start and end times are based on\. The **Start date and time** represent the time at which Amazon Pinpoint sends the first message in the recurring campaign, and the **End date and time** represents the date and time at which Amazon Pinpoint sends the final message in the recurring campaign\.

     If you want to ensure that the campaign begins and ends at the specified time in each recipient's time zone, choose **Use recipient's local time**\.

1. Choose **Next** to continue to the final step\.

**Next**  
[Step 5: Review and Launch the Campaign](campaigns-review.md)