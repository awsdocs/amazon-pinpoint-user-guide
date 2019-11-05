# Sending an Email Message<a name="messages-email"></a>

To send a test email message, you have to use a project in which the email channel is enabled\. To create a new project with email support, see [Setting up the Amazon Pinpoint Email Channel](channels-email-setup.md)\. To add email support to an existing project, see [Managing the Amazon Pinpoint Email Channel](channels-email-manage.md)\.

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project in which the email channel is enabled\.

1. In the navigation pane, choose **Test messaging**\.

1. Under **Channel**, choose **Email**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Email addresses** – Each destination is a recipient's email address\.
   + **Endpoint IDs** – Each destination is a unique ID assigned to an Amazon Pinpoint *endpoint* resource\.

1. Depending on your selection for **Destination type**, enter one or more **Endpoint IDs** or **Email addresses**\. You can enter up to 15 values\. Use commas to separate multiple values\.

1. For **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. 

   If you choose to use an existing template, choose the template from the **Template** list\.

   If you choose to create a new message, specify a subject in the **Subject** field, and a message body in the **Message** field\. You can also modify the subject and body of the message if you choose an existing template\.
**Tip**  
You can enter the message body by using either HTML or Design view\. In the HTML view, you can manually enter HTML content for the message body, including formatting, links, and other features that you want to include in the message\. In the Design view, you can use a rich text editor to enter the content of the message body, and use the formatting toolbar to apply formatting and add links and other features to the message body\. To switch views, choose **HTML** or **Design** from the view selector above the message editor\.  
You can also include personalized content in your message\. You do this by adding variables to the message\. Each message variable refers to a specific endpoint attribute, such as a recipient's first name\. When Amazon Pinpoint sends the message, it substitutes the variable with the corresponding attribute value for the receiving endpoint\. To include a variable in your message, surround the attribute name with two sets of curly braces\. For example, you could include the recipient's first name in the body of the message by entering `{{User.UserAttributes.FirstName}}` in the body of the message\.

1. \(Optional\) Under **Plain text message**, enter a version of your message for email applications that don't display HTML\.

1. When you finish, choose **Send message**\.