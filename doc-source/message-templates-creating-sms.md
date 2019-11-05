# Creating SMS Templates<a name="message-templates-creating-sms"></a>

An *SMS template* is a type of message template that contains content that you want to create, save, and reuse in SMS text messages that you send for any of your Amazon Pinpoint projects\. You can use an SMS template in text messages that you send as campaign messages, transactional messages, direct messages, or test messages\.

When you create an SMS template, you specify the content that you want to reuse in the body of text messages that are based on the template\. When you create a message that’s based on the template, Amazon Pinpoint populates the message with the content that you defined in the template\. You can then send the message as it is or customize it\.

**To create an SMS template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. Choose **Create a template**\.

1. Under **Channel**, choose **SMS**\.

1. Under **Template details**, for **Template name**, enter a name for the template\. The name has to begin with a letter or number\. It can contain up to 128 characters\. The characters can be letters, numbers, underscores \(\_\), or hyphens \(‐\)\.

1. Under **SMS details**, for **Message**, enter the content that you want to display in the body of messages that use the template\. The message body can contain up to 1,600 characters\.

1. When you finish entering content for the template, choose **Create**\.