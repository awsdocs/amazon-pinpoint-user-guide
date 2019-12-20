# Sending a Test Email Message<a name="messages-email"></a>

To send a test email message, you have to use a project in which the email channel is enabled\. To learn how to create a new project with email support, see [Setting up the Amazon Pinpoint Email Channel](channels-email-setup.md)\. To learn how to add email support to an existing project, see [Managing the Amazon Pinpoint Email Channel](channels-email-manage.md)\.

**To send a test email message**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that you want to send a test message for\.

1. In the navigation pane, choose **Test messaging**\.

1. On the **Test messaging** page, under **Channel**, choose **Email**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Email addresses** – Each destination is a recipient's email address\.
   + **Endpoint IDs** – Each destination is a unique ID that's assigned to an endpoint for the project\.

1. Depending on your selection for **Destination type**, enter one or more **Endpoint IDs** or **Email addresses**\. You can enter up to 15 values\. Use commas to separate multiple values\.

1. For **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. 

   If you choose to use an existing template, choose the template from the **Template** list\. After you choose a template, Amazon Pinpoint displays a preview of the active version of the template\. The active version is typically the version of a template that's been reviewed and approved for use, depending on your workflow\.

   If you choose to create a new message, specify a subject in the **Subject** field, and a message body in the **Message** field\.
**Tip**  
You can enter the message body by using either HTML or Design view\. In the HTML view, you can manually enter HTML content for the message body, including formatting, links, and other features that you want to include in the message\. In the Design view, you can use a rich text editor to enter the content of the message body, and use the formatting toolbar to apply formatting and add links and other features to the message body\. To switch views, choose **HTML** or **Design** from the view selector above the message editor\.  
You can also include personalized content in your message\. To do this, add message variables that refer to specific attributes that you or Amazon Pinpoint created for the project, such as an attribute that stores a user's first name\. By using message variables, you can display different content for each recipient of a message\. To use a message variable, add the name of an existing attribute to the message\. Enclose the name in two sets of curly braces, and use the exact capitalization of the name—for example, `{{User.UserAttributes.FirstName}}`\.

   In the field below the message editor, optionally enter the content that you want to display in the body of messages that are sent to recipients whose email applications don't display HTML content\.

1. When you finish, choose **Send message**\.