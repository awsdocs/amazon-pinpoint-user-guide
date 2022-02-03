# Sending Safari web push notifications<a name="channels-push-safari"></a>

You can use Amazon Pinpoint to send messages to macOS computers that use Apple's Safari web browser\. To send a message to the Safari browser, you must specify the raw message content, and you must include a specific attribute in the message payload\. You can do this by [creating a push notification template with a raw message payload](message-templates-creating-push.md#message-templates-creating-push-raw), or by specifying the raw message content directly in a [campaign](campaigns-message.md#campaigns-message-push) message\.

**Note**  
This special attribute is required for sending to macOS laptop and desktop computers that use the Safari web browser\. It isn't required for sending to iOS devices such as iPhones and iPads\.

To send a message to Safari web browsers, you must specify the raw message payload\. The raw message payload must include a `url-args` array within the `aps` object\. The `url-args` array is required in order to send push notifications to the Safari web browser\. However, it is acceptable for the array to contain a single, empty element\.

The `APNSMessage` section of the raw message payload should resemble the following example:

```
{
    "APNSMessage": {
        "aps": {
            "alert": { 
                "title": "Title of my message", 
                "body": "This is a push notification for the Safari web browser."
            },
            "content-available": 1,
            "url-args": [""]
        }
    }
}
```

For more information about Safari push notifications, see [Configuring Safari Push Notifications](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/NotificationProgrammingGuideForWebsites/PushNotifications/PushNotifications.html) on the Apple Developer website\.