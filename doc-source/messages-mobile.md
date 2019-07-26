# Sending a Push Notification<a name="messages-mobile"></a>

To send a test push notification, you first have to create a project in which the push notifications channel is enabled\. To create a new project with push notification support, see [Setting up Amazon Pinpoint Mobile Push Channels](channels-mobile-setup.md)\. To add push notification support to an existing project, see [Managing Mobile Push Channels with Amazon Pinpoint](channels-mobile-manage.md)\.

You can send push notifications through Apple Push Notification service \(APNs\), Firebase Cloud Messaging \(FCM\), Amazon Device Messaging \(ADM\), or Baidu Cloud Push\.

**To send a test push notification**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project in which the push notification channel is enabled\.

1. In the navigation pane, choose **Test messaging**\.

1. Under **Channel**, choose **Push notifications**\.

1. For **Destination type**, choose one of the following destinations for your message:
   + **Endpoint IDs** – Each destination is a unique ID assigned to an Amazon Pinpoint *endpoint* resource\.
   + **Device tokens** – Each destination is a token assigned to the instance of the app that you are messaging\. For example, this value can be the device token assigned by APNs, or the registration token assigned by FCM\.

1. Depending on your selection for **Destination type**, type one or more **Endpoint IDs** or **Device tokens**\. You can type up to 15 values\. Use commas to separate multiple values\. 

   If you use device tokens as the destination type, you should only specify tokens that are associated with a single push notification service\. Amazon Pinpoint can send the message through only one push notification provider in a single delivery\.

   If you use endpoint IDs as the destination type, this limitation does not apply, and you can specify endpoint resources that use any push notification service\.

1. For **Push notification service**, specify the push notification service through which you are sending the message\. If you use endpoint IDs as the destination type, Amazon Pinpoint detects the service automatically\.

1. Under **Message**, for **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. 

   If you choose to use an existing template, choose a template from the **Template** menu\.

   If you choose to create a new message, specify a **Title** and **Body** for the message\. You can also modify the **Title** and **Body** of the message if you choose an existing template\.

1. For **Action**, select the action you want to occur if the user opens the notification:
   + **Open app** – Your app launches, or it becomes the foreground app if it has been sent to the background\.
   + **Go to URL** – The default mobile browser on the user's device launches and opens a webpage at the URL you specify\. For example, this action is useful for sending users to a blog post\.
   + **Open a deep link** – Your app opens and displays a designated user interface within the app\. Deep link is an iOS and Android feature\. For example, this action is useful to direct users to special promotions for in\-app purchases\.

1. \(Optional\) In the **Media URLs** section, provide URLs that point to media files that are displayed in your push notification\. The URLs must be publicly accessible so that the push notification services for Android or iOS can retrieve the images\.

1. When you finish, choose **Send message**\.