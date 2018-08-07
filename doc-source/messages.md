# Direct Messages with Amazon Pinpoint<a name="messages"></a>

With Amazon Pinpoint, you can send a *direct message*, which is a one time message that you send to a limited audience without creating a campaign\. Sending a direct message is useful if, before creating a campaign, you want to test how your message appears to recipients\.

You can send the message to up to 15 recipients\. You cannot use the message to engage a segment\. When you send the message, Amazon Pinpoint delivers it immediately, and you cannot schedule the delivery\. To engage a user segment, and to schedule the message delivery, [create a campaign](campaigns.md) instead of sending a direct message\.

You can send a direct messages using any channel that is supported by Amazon Pinpoint: mobile push, email, or SMS\.

Send direct messages by using the **Direct** page in the Amazon Pinpoint console\.

**To access the Direct page**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project for which you want to send a message\.

1. In the navigation menu, choose **Direct**\.

## Sending a Mobile Push Notification<a name="messages-mobile"></a>

To send a direct push notification, you must use a project in which the mobile push channel is enabled\. To create a new project with mobile push support, see [Setting up Amazon Pinpoint Mobile Push Channels](channels-mobile-setup.md)\. To add mobile push support to an existing project, see [Managing Mobile Push Channels with Amazon Pinpoint](channels-mobile-manage.md)\.

You can send push notifications through Apple Push Notification service \(APNs\), Firebase Cloud Messaging \(FCM\), or the FCM predecessor, Google Cloud Messaging \(GCM\)\.

**To send a direct push notification**

1. On the **Direct** page, choose **Mobile push**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Endpoint ID** – Each destination is a unique ID assigned to an Amazon Pinpoint *endpoint* resource\.
   + **Device token** – Each destination is a token assigned to the instance of the app that you are messaging\. This can be the device token assigned by APNs or the registration token assigned by FCM or GCM\.

1. Depending on your selection for **Destination type**, type one or more **Endpoint IDs** or **Device tokens**\. You can type up to 15 values\. Separate each on its own line\. 

   If you use device tokens as the destination type, specify tokens assigned only by Apple \(APNs\) or only by Google \(FCM or GCM\)\. Amazon Pinpoint can send the message through only one of these push notification providers in a single delivery\.

   If you use endpoint IDs as the destination type, this limitation does not apply, and you can specify endpoint resources that use either push notification provider\.

1. For **Service**, specify the push notification service through which you are sending the message: **FCM/GCM** or **APNs**\. If you use endpoint IDs as the destination type, Amazon Pinpoint detects the service automatically\.

1. If you previously saved a template that you want to use for your message, load it by choosing **Load template**\. The **Title** and **Message** are populated with the contents of the template\.

1. For **Title**, type the title you want to display above the message\.

1. For **Message**, type the message body\. A character counter below the right edge of the field counts down from 200 as you enter the text of the message\.

   When you finish writing your message, you can save it as a template for later use by choosing **Save as template**\.

1. For **Action**, select the action you want to occur if the user opens the notification:
   + **Open app** – Your app launches, or it becomes the foreground app if it has been sent to the background\.
   + **Go to URL** – The default mobile browser on the user's device launches and opens a webpage at the URL you specify\. For example, this action is useful for sending users to a blog post\.
   + **Deep link** – Your app opens and displays a designated user interface within the app\. Deep link is an iOS and Android feature\. For example, this action is useful to direct users to special promotions for in\-app purchases\.

1. \(Optional\) In the **Media URLs** section, provide URLs that point to media files that are displayed in your push notification\. The URLs must be publicly accessible so that the push notification services for Android or iOS can retrieve the images\.

1. When you finish, choose **Send**\.

## Sending an Email Message<a name="messages-email"></a>

To send a direct email, you must use a project in which the email channel is enabled\. To create a new project with email support, see [Setting up the Amazon Pinpoint Email Channel](channels-email-setup.md)\. To add email support to an existing project, see [Managing the Amazon Pinpoint Email Channel](channels-email-manage.md)\.

1. On the **Direct** page, choose **Email**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Endpoint ID** – Each destination is a unique ID assigned to an Amazon Pinpoint *endpoint* resource\.
   + **Email address** – Each destination is the recipient's email address\.

1. Depending on your selection for **Destination type**, type one or more **Endpoint IDs** or **Email addresses**\. You can type up to 15 values\. Separate each on its own line\.

1. If you previously saved a template that you want to use for your message, load it by choosing **Load template**\. The **Subject** and **Message** are populated with the contents of the template\.

1. For **Subject**, type the subject for your email\.

1. For **Message**, type the email body\. You can use the rich text editor to format your message:  
![\[The icons in the email message rich text editor.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/campaigns_email_editor.png)![\[The icons in the email message rich text editor.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The icons in the email message rich text editor.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

   To write your message body as HTML, choose the source icon:  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/campaigns_email_source.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

   When you finish writing your message, you can save it as a template for later use by choosing **Save as template**\.

1. \(Optional\) Under **Plain text message**, type a version of your message for email clients that accept only plain text emails\.

1. When you finish, choose **Send**\.

## Sending an SMS Message<a name="messages-sms"></a>

To send a direct SMS message, you must use a project in which the SMS channel is enabled\. To create a new project with SMS support, see [Setting up the Amazon Pinpoint SMS Channel](channels-sms-setup.md)\. To add SMS support to an existing project, see [Managing the Amazon Pinpoint SMS Channel](channels-sms-manage.md)\.

**To send a direct SMS message**

1. On the **Direct** page, choose **SMS**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Endpoint ID** – Each destination is a unique ID assigned to an Amazon Pinpoint *endpoint* resource\.
   + **Phone number** – Each destination is the recipient's phone number\.

1. Depending on your selection for **Destination type**, type one or more **Endpoint IDs** or **Phone numbers**\. You can type up to 15 values\. Separate each on its own line\.

   If you use phone numbers as the destination type, specify each number using E\.164 format\. E\.164 is a standard for the phone number structure used for international telecommunication\. Phone numbers that follow this format typically have up to 15 digits, and they are prefixed with the plus character \(\+\) and the country code\. For example, a US phone number in E\.164 format appears as \+12065550100\.

1. For **Message type**, choose one of the following:
   + **Promotional** – Noncritical messages, such as marketing messages\. Amazon Pinpoint optimizes the message delivery to incur the lowest cost\.
   + **Transactional** – Critical messages that support customer transactions, such as one\-time passcodes for multi\-factor authentication\. Amazon Pinpoint optimizes the message delivery to achieve the highest reliability\.

   This message\-level setting overrides your default message type, which you set on the **Settings** page\.

1. If you previously saved a template that you want to use for your message, load it by choosing **Load template**\. The **Message** is populated with the contents of the template\.

1. For **Message**, type the message body\. 

   The character limit for a single SMS message is 160\. A character counter below the right edge of the field counts down from 160 as you enter the text of the message\.

   When you finish writing your message, you can save it as a template for later use by choosing **Save as template**\.

1. \(Optional\) For **Sender ID**, type a custom ID that contains up to 11 alphanumeric characters, including at least one letter and no spaces\. The sender ID is displayed as the message sender on the receiving device\. For example, you can use your business brand to make the message source easier to recognize\.

   Support for sender IDs varies by country and/or region\. For more information, see [Supported Countries and Regions](channels-sms-countries.md)\.

   This message\-level sender ID overrides your default sender ID, which you set on the **Settings** page\.

1. When you finish, choose **Send**\.

## Message Templates<a name="messages-templates"></a>

To save your message and reuse it in a separate campaign or direct message, choose **Save as template** and provide a template name\. Then, you can load the template for any message by choosing **Load template** and selecting it from a list of saved templates\. Amazon Pinpoint populates your message with the template's content\. Then, you can send the message as\-is or customize as needed\.

You can base a template on any supported message type, and you can use the same template for other message types\. For example, you can write a push notification message, save it as a template, and use that template for an SMS message\. Note that if you use a single template for multiple message types, Amazon Pinpoint loads the content differently for each type\. For example, if you base a template on a mobile push message, and you load this template for an email message, the push notification *title* is used as the email *subject*\. The correlations between message parts are as follows:


**Mobile push templates**  

| The mobile push \. \. \.  | Is used as the email \. \. \. | Is used as the SMS \. \. \. | 
| --- | --- | --- | 
| Title | Subject | Not used | 
| Message body | Plain text message | Message body | 


**Email templates**  

| The email \. \. \. | Is used as the mobile push \. \. \.  | Is used as the SMS \. \. \. | 
| --- | --- | --- | 
| Subject | Title | Not used | 
| Message body \(HTML\) | Not used | Not used | 
| Plain text message | Message body | Message body | 


**SMS templates**  

| The SMS \. \. \. | Is used as the mobile push \. \. \.  | Is used as the email \. \. \. | 
| --- | --- | --- | 
| Message type | Title | Subject | 
| Message body | Message body | Plain text message | 