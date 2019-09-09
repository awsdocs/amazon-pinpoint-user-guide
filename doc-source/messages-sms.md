# Sending an SMS Message<a name="messages-sms"></a>

To send a test SMS message, you have to use a project in which the SMS channel is enabled\. To create a new project with SMS support, see [Setting up the Amazon Pinpoint SMS Channel](channels-sms-setup.md)\. To add SMS support to an existing project, see [Managing the Amazon Pinpoint SMS Channel](channels-sms-manage.md)\.

**To send a test SMS message**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project in which the push notification channel is enabled\.

1. In the navigation pane, choose **Test messaging**\.

1. Under **Channel**, choose **SMS**\.

1. On the **Test messaging** page, choose **SMS**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Phone numbers** – Each destination is the recipient's phone number\.
   + **Endpoint IDs** – Each destination is a unique ID assigned to an Amazon Pinpoint *endpoint* resource\.

1. Depending on your selection for **Destination type**, type one or more **Endpoint IDs** or **Phone numbers**\. You can type up to 15 values\. Use commas to separate multiple values\.

   If you use phone numbers as the destination type, specify each number in E\.164 format\. E\.164 is a standard for the phone number structure used for international telecommunication\. Phone numbers that follow this format typically have up to 15 digits, and they are prefixed with the plus character \(\+\) and the country code\. For example, a US phone number in E\.164 format appears as \+12065550100\.

1. For **Message type**, choose one of the following:
   + **Promotional** – Noncritical messages, such as marketing messages\. Amazon Pinpoint optimizes the message delivery to incur the lowest cost\.
   + **Transactional** – Critical messages that support customer transactions, such as one\-time passcodes for multi\-factor authentication\. Amazon Pinpoint optimizes the message delivery to achieve the highest reliability\.
**Note**  
This message\-level setting overrides the default message type that you set on the **Settings** page for the project\.

1. Under **Message**, for **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. 

   If you choose to use an existing template, choose a template from the **Template** menu\.

   If you choose to create a new message, specify the content of message in the **Message** field\. You can also modify the body of the message if you choose an existing template\.

1. \(Optional\) For **Sender ID**, type a custom ID that contains up to 11 alphanumeric characters, including at least one letter and no spaces\. The sender ID is displayed as the message sender on the receiving device\. For example, you can use your business brand to make the message source easier to recognize\.

   Support for sender IDs varies by country and/or region\. For more information, see [Supported Countries and Regions \(SMS Channel\)](channels-sms-countries.md)\.

   This message\-level sender ID overrides your default sender ID, which you set on the **Settings** page\.

1. When you finish, choose **Send message**\.