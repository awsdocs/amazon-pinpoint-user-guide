# Creating Email Templates<a name="message-templates-creating-email"></a>

An *email template*is a type of message template that contains content that you want to create, save, and reuse in email messages that you send for any of your Amazon Pinpoint projects\. You can use an email template in email messages that you send as campaign messages, journey messages, transactional messages, direct messages, or test messages\.

When you create an email template, you specify the content that you want to reuse in various components of email messages that are based on the template\. These components, referred to as *template parts*, can be the message subject, the message body, or both\. When you create an email message that’s based on the template, Amazon Pinpoint populates the message with the content that you defined in the template\. You can then send the message as it is or customize it\.

**To create an email template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. Choose **Create a template**\.

1. Under **Channel**, choose **Email**\.

1. Under **Template details**, for **Template name**, enter a name for the template\. The name has to begin with a letter or number\. It can contain up to 128 characters\. The characters can be letters, numbers, underscores \(\_\), or hyphens \(‐\)\.

1. Under **Email details**, for **Subject**, enter the text that you want to display in the subject line of messages that use the template\.

1. Under **Message**, enter the content that you want to display in the body of messages that use the template\. You can enter the content by using either the HTML or Design view\. In the HTML view, you can manually enter HTML content, including formatting, links, and other features that you want to include in the template\. In the Design view, you can use a rich text editor to enter the content, and use the formatting toolbar to apply formatting and add links and other features to the content\. To switch views, choose **HTML** or **Design** from the view selector above the message editor\.

1. \(Optional\) Under **Plain text version**, enter the content that you want to display in the body of messages that use the template and are sent to recipients whose email applications don't display HTML\.

1. When you finish entering content for the template, choose **Create**\.
