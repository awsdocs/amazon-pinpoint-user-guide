# Setting up Amazon Pinpoint Mobile Push Channels<a name="channels-mobile-setup"></a>

Before you can use Amazon Pinpoint to send push notifications to your app, you must define your app as a project in AWS Mobile Hub and integrate your app with Amazon Pinpoint\. Mobile Hub is an AWS service that helps you create and configure mobile app backend features and integrate them into your app\.

When you define your project in Mobile Hub, you set up channels for Firebase Cloud Messaging \(FCM\), Google Cloud Messaging \(GCM\), or Apple Push Notification service \(APNs\)\. To set up channels for Baidu Cloud Push or Amazon Device Messaging \(ADM\), manage your channels using the **Settings** page for your project in the Amazon Pinpoint console\.

If you don't already have an app that is enabled for Amazon Pinpoint, see the following information in the *Amazon Pinpoint Developer Guide*:

+ [Setting Up Push Notifications for Amazon Pinpoint](http://docs.aws.amazon.com/pinpoint/latest/developerguide/mobile-push.html) – Provides steps to create and download the required credentials from the Apple Developer website or the Google Firebase console\.

+  [Getting Started: Creating an App With Amazon Pinpoint Support](http://docs.aws.amazon.com/pinpoint/latest/developerguide/getting-started.html) – Provides steps for adding your app as a project in AWS Mobile Hub and integrating your app with Amazon Pinpoint\.

After you add an app to Amazon Pinpoint, you can update your push notification credentials on the **Settings** page\. For more information, see [Managing Mobile Push Channels with Amazon Pinpoint](channels-mobile-manage.md)\.