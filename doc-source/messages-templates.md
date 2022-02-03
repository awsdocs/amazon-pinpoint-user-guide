# Amazon Pinpoint message templates<a name="messages-templates"></a>

If you frequently design and send a certain type of message, such as a weekly newsletter or an appointment reminder, you can create and save it as a message template\. You can then use the template as a starting point each time you need to send that type of message, instead of designing and writing the message again\.

A *message template* is a set of content and settings that you can create, save, and then reuse in messages that you send for any of your Amazon Pinpoint projects\. When you create a template, you specify the content that you want to reuse in various components of messages that are based on the template\. 

These components are referred to as *template parts*\. They can contain static text, personalized content, images, and other design elements, depending on the type of template\. A template part can also contain channel\-specific settings\. For example, a template part in a push notification template can specify a custom sound to play or an image to display when a recipient receives a push notification that's based on the template\.

When you create a message, you can choose a template to use for the message\. If you choose a template, Amazon Pinpoint populates the message with the content and settings in the template\.

You can design the following types of message templates in Amazon Pinpoint:
+ *Email templates* for email messages that you send from campaigns or journeys, or to a limited audience as direct or test messages\.
+ *Push notification templates* for push notifications that you send from campaigns, or to a limited audience as direct or test messages\.
+ *SMS templates* for SMS text messages that you send from campaigns, or to a limited audience as direct or test messages\.
+ *Voice templates* for voice messages that you send as direct or test messages\.

In addition to supporting multiple types of message templates, Amazon Pinpoint supports versioning for message templates\. Versioning provides a way for you to design and change a template over time, while also creating and maintaining a history of the template\. Versioning also provides a way for you to specify which version of a template can be used in messages\. To learn more about template versions, see [Managing versions of message templates](message-templates-versioning.md)\.

The topics in this chapter explain how to create and manage message templates for your Amazon Pinpoint account\.

**Topics**
+ [Creating email templates](message-templates-creating-email.md)
+ [Creating in\-app templates](message-templates-creating-inapp.md)
+ [Creating push notification templates](message-templates-creating-push.md)
+ [Creating SMS templates](message-templates-creating-sms.md)
+ [Creating voice templates](message-templates-creating-voice.md)
+ [Adding personalized content to message templates](message-templates-personalizing.md)
+ [Using message template helpers](message-template-helpers.md)
+ [Managing message templates](message-templates-managing.md)
+ [Managing versions of message templates](message-templates-versioning.md)