# Managing Pools in Amazon Pinpoint<a name="channels-voice-managing-pools"></a>

A pool is a collection of phone numbers and Sender IDs, which are names that contain alphanumeric characters\. When you create a pool, you can configure a specified origination identity\. This identity includes keywords, message type, opt\-out list, two\-way configuration, and self\-managed opt\-out configuration\.

Before you can use Amazon Pinpoint to create a new pool, you have to activate the SMS and voice channel for one or more projects\. To do this task, go to the **SMS and voice** settings page on the Amazon Pinpoint console\. For more information, see [Managing SMS and voice settings in Amazon Pinpoint](settings-sms-managing.md)\.

**Note**  
Pools are not available in the US East \(Ohio\) region\.

## Creating a pool<a name="channels-voice-managing-pools-create"></a>

A pool includes one or more phone numbers and Sender IDs that are associated with your AWS account\.

**To create a pool**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Pools** tab, choose **Create pool**\.

1. \(Optional\) Under the **Pool setup** section, add a name for your pool\.

1. Select one of the following options:
   + **Sender ID** – If you select this option, under the **Provide Sender ID for association** section, do the following:
     + For **Sender ID**, enter your sender ID\.
     + For **Country**, select the country\.
     + For **Message type**, select **Transactional** for time\-sensitive content, such as alerts and one\-time passwords, or choose **Promotional** for marketing\-related content\.
     + Choose **Create pool**\.
   + **Phone number** – If you select this option, under the **Numbers available for association** section, do the following:
     + Select a phone number to create the pool\.
     + Choose **Create pool**\.

## Associating and disassociating origination identities<a name="channels-voice-managing-pools-associating-and-disassociating"></a>

After you have created a pool, you can associate origination identities to it\.

**To associate an origination identity to a pool**

1. On the **Pool detail** page, under the **Origination identities** section, select the origination identity you want to associate to a pool\.

1. Choose **Associate to pool**\.

**To disassociate an existing origination identity from a pool**

1. On the **Pool detail** page, under the **Origination identities** section, select the origination identity you want to disassociate from a pool\.

1. Choose **Disassociate from pool**\.

1. In the **Disassociate confirmation** window, enter **disassociate** in the text field\.

1. Choose **Disassociate**\.

## Configuring pool settings<a name="channels-voice-managing-pools-configure"></a>

On the **Pool detail** page, you can configure settings that you want to apply to a pool\.

**To configure pool settings**

1. Under the **Pool settings** section, you have the option to configure any of the following settings:
   + **Two\-way SMS** – When you turn on two\-way SMS, you can receive incoming messages from your customers\.
   + **Deletion protection** – When you turn on deletion protection, you can protect the pool from being deleted\.
   + **Shared routes** – In some countries, Amazon Pinpoint maintains a pool of shared origination identities\. When you activate shared routes, Amazon Pinpoint makes an effort to deliver your message using one of the shared identities\. Shared identities are unavailable in some countries, including the United States\.
   + **Keywords** – When your number receives a message that begins with a keyword, Amazon Pinpoint responds with a customizable message\. Keywords can contain up to 25 characters\.
     + If you want to add more keywords, select **Add another keyword**\.
     + If you want to remove a keyword, choose **Remove keyword**\.
   + **Tags** – Tags are pairs of keys and values that you can optionally apply to your AWS resources to control access or usage\. You can add up to 50 tags\.
     + If you want to add a tag, choose **Add new tag**\.

1. When you finish, choose **Save changes**\.

## Deleting a pool<a name="channels-voice-managing-pools-delete"></a>

You can delete an existing pool from Amazon Pinpoint\. When you delete a pool, Amazon Pinpoint disassociates all origination identities from that pool\.

**To delete a pool**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Pools** tab, select the pool you want to delete\.

1. Choose **Delete pool**\.

1. In the **Delete pool confirmation** window, enter **delete** in the text field\.

1. Choose **Delete**\.