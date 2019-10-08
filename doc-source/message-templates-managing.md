# Managing Message Templates<a name="message-templates-managing"></a>

The **Message templates** page on the Amazon Pinpoint console provides a single location for you to create, view, and manage all the message templates for your Amazon Pinpoint account in the current AWS Region\. By using this page, you can manage your message templates as a single collection, which can help you design consistent messages and reuse content more easily and effectively\. You can use this page to perform management tasks such as viewing and editing templates, and copying, deleting, and creating templates\.

**Topics**
+ [Viewing Your Collection of Message Templates](#message-templates-managing-view-all)
+ [Opening a Message Template](#message-templates-managing-open)
+ [Copying a Message Template](#message-templates-managing-copy)
+ [Editing a Message Template](#message-templates-managing-edit)
+ [Deleting a Message Template](#message-templates-managing-delete)

For information about creating a message template, see [Creating Email Templates](message-templates-creating-email.md), [Creating Push Notification Templates](message-templates-creating-push.md), or [Creating SMS Templates](message-templates-creating-sms.md), depending on the type of template that you want to create\.

## Viewing Your Collection of Message Templates<a name="message-templates-managing-view-all"></a>

The **Message templates** page displays a list of all the message templates for your Amazon Pinpoint account in the current AWS Region\. To browse the list more easily or find specific templates quickly, you can sort and filter the list, choose which columns to display, and change other display settings for the list\.

**To view your collection of message templates**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\. The **Message templates** page opens and displays the number of templates in your collection and a list of those templates\.

1. To customize the list or find a specific template quickly, choose any of the following options:
   + To sort the list by a specific type of value, click the column heading for that value\. To change the sort order from ascending to descending or vice versa, click the column heading again\. 
   + To apply a filter that displays only a specific type of template, use the channel selector at the top of the page to choose the channel\. To remove the filter, choose **All message channels** from the channel selector\.
   + To apply a filter that displays only those templates whose names contain specific text, enter the text in the **Search** box above the list\. To remove the filter, click **X** in the **Search** box\.
   + To change the number of templates that are displayed in the list, choose the settings icon at the top of the page\. Then, for **Page size**, choose the number of templates that you want to display, and then choose **Save changes**\.
   + To add or remove columns from the list, choose the settings icon at the top of the page\. Then, for **Choose visible columns**, turn each column on or off, and then choose **Save changes**\.

## Opening a Message Template<a name="message-templates-managing-open"></a>

By using the **Message templates** page, you can quickly find and open a specific message template to view the contents of the template and information about the template, such as when the template was created and when the template was last updated\. After you open a template, you can also edit the template\.

**To open a message template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. On the **Message templates** page, choose the template that you want to open\. The template page opens and displays the contents of the template and information about the template\.

1. \(Optional\) To edit the template, choose **Edit**, and then make the changes that you want\. When you finish making changes, choose **Update**\.

**Note**  
If you edit a template, Amazon Pinpoint doesn't apply the changes to any existing messages that use the previous version of the template\. This includes messages that haven’t been sent yet, such as campaign messages that are scheduled to be sent at a later time\. This means that your changes won't affect any existing messages that use the template\.

## Copying a Message Template<a name="message-templates-managing-copy"></a>

To quickly create a new message template that's similar to an existing template, you can create a copy of the template\. You can then edit the template copy, without changing the original template\.

**To copy a message template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. On the **Message templates** page, select the check box next to the template that you want to copy\.

1. On the **Actions** menu, choose **Duplicate**\. The **Create your template** page opens and displays all the content and settings for the template that you copied\.

1. Under **Template details**, for **Template name**, enter a name for the template copy\. The name has to begin with a letter or number and it can contain up to 128 characters\. The characters can be letters, numbers, underscores \(\_\), or hyphens \(‐\)\.

1. In the message details section, make the changes that you want\.

1. When you finish making changes, choose **Create**\.

## Editing a Message Template<a name="message-templates-managing-edit"></a>

You can open a message template for editing in two ways: while you're authoring a message that uses the template, and by using the **Message templates** page\. This topic explains how to open and edit a template by using the **Message templates** page\.

If you edit a template, Amazon Pinpoint doesn't apply the changes to any existing messages that use the previous version of the template\. This includes messages that haven't been sent yet, such as campaign messages that are scheduled to be sent at a later time\. This means that your changes won't affect any existing messages that use the template\.

**To edit a message template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. On the **Message templates** page, choose the template that you want to edit\. The template page opens and displays the contents of the template and information about the template\.

1. Choose **Edit**\.

1. Make the changes that you want\. You can change any of the content, except the name of the template\. To change the name of the template, [create a copy of the template](#message-templates-managing-copy), save the copy with the name that you want, and then delete the original template\.

1. When you finish making changes, choose **Update**\.

## Deleting a Message Template<a name="message-templates-managing-delete"></a>

If you want to remove a message template from Amazon Pinpoint completely, you can delete the template\. If you delete a template, it won't affect any existing messages that use the template, such as a campaign messages that are scheduled to be sent at a later time\.

**Warning**  
If you delete a template, Amazon Pinpoint deletes all the content and settings for the template, and the template becomes unavailable for all future messages\. You can't recover a template after you delete it\. 

**To delete a message template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. On the **Message templates** page, select the check box next to each template that you want to delete\.

1.  On the **Actions** menu, choose **Delete**\.