# Sending an Email Message<a name="messages-email"></a>

To send a test email message, you have to use a project in which the email channel is enabled\. To create a new project with email support, see [Setting up the Amazon Pinpoint Email Channel](channels-email-setup.md)\. To add email support to an existing project, see [Managing the Amazon Pinpoint Email Channel](channels-email-manage.md)\.

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose a project in which the push notification channel is enabled\.

1. In the navigation pane, choose **Test messaging**\.

1. Under **Channel**, choose **Email**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Email addresses** – Each destination is the recipient's email address\.
   + **Endpoint IDs** – Each destination is a unique ID assigned to an Amazon Pinpoint *endpoint* resource\.

1. Depending on your selection for **Destination type**, type one or more **Endpoint IDs** or **Email addresses**\. You can type up to 15 values\. Use commas to separate multiple values\.

1. Under **Message**, for **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. 

   If you choose to use an existing template, choose a template from the **Template** menu\.

   If you choose to create a new message, specify a title in the **Title** field, and a message body in the **Message** field\. You can also modify the title and body of the message if you choose an existing template\.

1. \(Optional\) Under **Plain text message**, type a version of your message for email clients that accept only plain text emails\.

1. When you finish, choose **Send message**\.