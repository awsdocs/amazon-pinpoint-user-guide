# Amazon Pinpoint push notifications<a name="channels-push"></a>

With Amazon Pinpoint, you can engage users of your apps by sending push notifications through a push notification channel\. You can send push notifications to your apps using separate channels for the following push notification services:
+ Firebase Cloud Messaging \(FCM\)
+ Apple Push Notification service \(APNs\)
**Note**  
You can use APNs to send messages to iOS devices such as iPhones and iPads, as well as to the Safari browser on macOS devices, such as Mac laptops and desktops\.
+ Baidu Cloud Push
+ Amazon Device Messaging \(ADM\)

**Note**  
Amazon Pinpoint sets the push endpoints with the oldest **EffectiveDate** to `INACTIVE` if a user has 15 endpoints and you add more push endpoints\. See [Older push endpoints automatically set to inactive](https://docs.aws.amazon.com/pinpoint/latest/developerguide/audience-define-auto-inactive.html) for more information\.

**Topics**
+ [Setting up Amazon Pinpoint mobile push channels](channels-push-setup.md)
+ [Monitoring push notification activity with Amazon Pinpoint](channels-push-monitor.md)
+ [Managing mobile push channels with Amazon Pinpoint](channels-push-manage.md)
+ [Sending Safari web push notifications](channels-push-safari.md)
+ [Best practices](channels-push-best-practices.md)