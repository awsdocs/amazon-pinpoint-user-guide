# Amazon Pinpoint Channels<a name="channels"></a>

A *channel* represents the platform through which you engage your audience segment with messages\. For example, to send messages to your mobile app users, you must have an Amazon Pinpoint project in which the *mobile push* channel is enabled\. Amazon Pinpoint supports the following channel types:
+ [Mobile push](channels-mobile.md)
+ [Email](channels-email.md)
+ [SMS](channels-sms.md)

Before you can use Amazon Pinpoint to engage your audience, you must create an Amazon Pinpoint project, and that project must support one or more channels\. To add a new project to Amazon Pinpoint, create a project using AWS Mobile Hub, and add the **Messaging & Analytics** feature to the project\. After you create a project in Mobile Hub, it becomes available in Amazon Pinpoint\.

After you create a project and enable a channel, you can use your project to send messages\. You can [define the audience segment](segments.md) that you want to engage and then [define a campaign](campaigns.md) that sends messages to that segment\. Or, to quickly send a message to a limited audience, you can [send a direct message](messages.md) without creating a campaign\.

**Topics**
+ [Amazon Pinpoint Mobile Push Channels](channels-mobile.md)
+ [Amazon Pinpoint Email Channel](channels-email.md)
+ [Amazon Pinpoint SMS Channel](channels-sms.md)