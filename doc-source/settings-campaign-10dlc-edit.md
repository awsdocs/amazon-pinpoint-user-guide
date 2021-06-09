# Editing or deleting a 10DLC campaign<a name="settings-campaign-10dlc-edit"></a>

You can edit Help, Stop, and Sample message for your 10DLC campaign using the Amazon Pinpoint console\. In addition, you can also delete your 10DLC campaign using the console\.

## Editing a 10DLC campaign<a name="edit-campaign-10dlc"></a>

Once your campaign is approved you can modify the Help, Stop, and any sample SMS messages\. You can also add additional sample messages up to the limit of five\. However, you can't reduce the number of sample messages that you originally registered\. For example, if you registered your campaign with three sample SMS messages, you can't reduce the number of sample SMS messages to less than three\. 

No other fields can be modified once the 10DLC campaign is approved\. Changes to these fields do not require re\-approval from The Campaign Registry or from carriers\.

**Note**  
If you want to modify any fields other than sample messages, you should first delete the 10DLC campaign and then recreate the campaign to include the updated information\.

**To edit a 10DLC campaign**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, and then under **SMS and voice**, choose **10DLC campaigns**\.

1. Choose the 10DLC campaign that you want to modify sample messages for\. 

1. In the** Campaign messages** section of the campaign details page, choose **Edit\.**

1. Update any of the following fields:
   + **Help message**
   + **Stop message**
   + **Sample SMS message**

     You can't delete a previously added sample message, or delete the contents of a sample message so that the field is empty\. If you delete the contents of a message without replacing that content, the original message will be used on updating\.

1. Choose **Update**\.

1. A confirmation banner appears letting you know the campaign messages were updated\.

## Deleting a 10DLC campaign<a name="delete-campaign-10dlc"></a>

You can delete a 10DLC campaign using the Amazon Pinpoint console\. Before deleting a 10DLC campaign you must first remove any numbers associated with that campaign\. You cannot recover a deleted 10DLC campaign\.

**Important**  
If you have any 10DLC numbers associated with a campaign you want to delete, first remove those numbers from the campaign\. Once you remove a 10DLC number from a campaign you no longer have access to that number\. 

**To delete a 10DLC campaign**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, and then under **SMS and voice**, choose **10DLC campaigns**\.

1. Choose the 10DLC campaign that you want to delete\. 

1. In the **Phone numbers** section, note the phone numbers associated with the campaign\.
**Note**  
This step is only required if you have multiple 10DLC phone numbers associated with the campaign\. If you have only a single phone number associated with the 10DLC campaign that number will appear on the **10DLC campaigns** tab\. Note the number displayed on the tab\.

1. On the **Phone numbers** tab, choose the 10DLC number you want to remove, and then choose **Remove phone number**\.

1. Enter **delete** into the confirmation box, and then choose **Confirm**\. A success message appears at the top of the SMS and voice page\.

1. Repeat the previous two steps for each 10DLC number associated with the campaign\.

1. After removing any numbers associated with the 10DLC campaign, choose the **10DLC campaigns** tab\.

1. Choose the 10DLC campaign you want to delete\.

1. In the upper right\-hand corner of the **10DLC campaign details** page, choose **Delete**\.

1. Enter **delete** into the confirmation box, and then choose **Confirm**\. A success message appears at the top of the SMS and voice page\.