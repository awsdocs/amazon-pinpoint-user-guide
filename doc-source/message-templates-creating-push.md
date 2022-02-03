# Creating push notification templates<a name="message-templates-creating-push"></a>

A *push notification template* is a message template that contains content and settings that you can use with your Amazon Pinpoint projects\. When you use a template to send a push notification, Amazon Pinpoint populates the notification with the content and settings that you defined in the template\.

When you create a push notification template, you specify the content and settings that you want to reuse in various components of push notifications that are based on the template\. These components, referred to as *template parts*, can contain text \(such as the title or body of a notification\) or settings \(such as a custom sound to play when a recipient receives a notification\)\.

To customize a template for specific push notification channels, you can create multiple sets of template parts in each template—a default set, and optionally one or more service\-specific sets\. The default set contains the content and settings that you want to use by default for any push notification channel\. A service\-specific set contains any content and settings that you want to use for a specific notification service, such as Apple Push Notification service or Firebase Cloud Messaging\. By adding service\-specific settings to a template, you can tailor your notifications to display content that is unique to each recipient's device type\.

You can also [create templates that contain raw message data](#message-templates-creating-push-raw)\. This option is more advanced, but is helpful if you want to specify settings for a specific channel that aren't present in the standard Amazon Pinpoint push notification template\.

## Creating a standard push notification template<a name="message-templates-creating-push-standard"></a>

Complete this procedure if you want to specify the basic message content, such as the title, message body, image, and action\. If you need to specify the raw message content, complete the procedure in [Creating a push notification template with raw message data](#message-templates-creating-push-raw) instead\.

**To create a push notification template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. Choose **Create template**\.

1. Under **Channel**, choose **Push notifications**\.

1. Under **Template details**, for **Template name**, enter a name for the template\. The name has to begin with a letter or number\. It can contain up to 128 characters\. The characters can be letters, numbers, underscores \(\_\), or hyphens \(‐\)\.

1. \(Optional\) For **Version description**, enter a brief description of the template\. The description can contain up to 500 characters\.

1. Under **Push notification details**, do the following:
   + For **Notification type**, choose **Standard message**\.
   + For **Title**, enter the title that you want to display above the message body\.
   + For **Body**, enter the text that you want to display in the body of the notification message\.
**Tip**  
You can include personalized content in the title and body of the template\. To do this, add message variables that refer to specific attributes, such as an attribute that stores a user's first name\. By using message variables, you can display different content for each recipient of a push notification that uses the template\.   
To use a message variable, choose the name of an existing attribute from the **Attribute finder**\. Amazon Pinpoint creates a message variable for the attribute and copies it to your clipboard\. Paste the variable in the location that you want\. For more information, see [Adding personalized content to message templates](message-templates-personalizing.md)\.
   + For **Custom alert sound**, enter the name of the audio file that contains the custom sound that you want to play when a recipient receives the push notification\. This name has to match the name of an audio file on a recipient's device\.
   + For **Action**, choose what you want a recipient's device to do if the recipient taps the push notification:
     + **Open your app** – Open your app or bring it to the foreground if it was sent to the background\.
     + **Go to a URL** – Open the default browser on the recipient's device and load a specific webpage\. If you choose this option, enter the URL of the webpage in the **Destination URL** box\.
     + **Open a deep link** – Open your app and display a specific user interface in the app\. If you choose this option, enter the URL of the interface in the **Destination URL** box\.

1. \(Optional\) To customize the template for specific push notification services, choose the appropriate service tab under **Customize content for individual push services**\. Then choose the options that you want for that service\.

   If you select the **Override default push content** check box on the tab for a service, Amazon Pinpoint automatically replaces the default content and settings that you chose in the preceding step with the options that you choose on the tab\. If you want to keep the default content and settings and just customize the template to use additional channel\-specific settings, don't select this check box\.  
**Apple**  
Use these options to specify custom content and settings for push notifications that you send through the Apple Push Notification service \(APNs\) channel to apps that are running on iOS devices\.  
In addition to the standard content and settings, you can include a custom image or video in push notifications that use the template\. To do this, enter the URL for the image or video file in the **iOS media** box\. The URL must be publicly accessible\. Otherwise, the recipient's device won't be able to display the image or video\.   
**Google**  
Use these options to specify custom content and settings for push notifications that you send through the Google Firebase Cloud Messaging \(FCM\) channel to apps that are running on Android devices\.  
In addition to the standard content and settings, you can choose the following options to display custom images in push notifications that use the template:  
   + **Android image** – Enter the URL of the image to display in the body of the push notification\.
   + **Android icon** – Enter the URL of the large icon image to display in the content view of the push notification\.
   + **Android small icon** – Enter the URL of the small icon image to display in the status bar and in the content view of the push notification\.  
**Amazon**  
Use these options to specify custom content and settings for push notifications that you send through the Amazon Device Messaging \(ADM\) channel to apps that are running on Amazon devices, such as Kindle Fire tablets\.  
In addition to the standard content and settings, you can choose the following options to display custom images in push notifications that use the template:  
   + **Android image** – Enter the URL of the image to display in the body of the push notification\.
   + **Android icon** – Enter the URL of the large icon image to display in the content view of the push notification\.
   + **Android small icon** – Enter the URL of the small icon image to display in the status bar and in the content view of the push notification\.  
**Baidu**  
Use these options to specify custom content and settings for push notifications that you send through the Baidu channel to apps that use the Baidu Cloud Push platform\.  
In addition to the standard content and settings, you can choose the following options to display custom images in push notifications that use the template:  
   + **Android image** – Enter the URL of the image to display in the body of the push notification\.
   + **Android icon** – Enter the URL of the large icon image to display in the content view of the push notification\.
   + **Android small icon** – Enter the URL of the small icon image to display in the status bar and in the content view of the push notification\.

1. If you added personalized content to the template by using message variables, specify a default value for each variable\. If you do this, Amazon Pinpoint replaces the variable with the value that you specify, if a corresponding value doesn't exist for a recipient\. We recommend that you do this for each variable in the template\.

   To specify default values for variables, expand the **Default attribute values** section\. Then enter the default value that you want to use for each variable\. If you don't specify a default value and a value doesn't exist for a recipient, Amazon Pinpoint does not send the message\.

1. When you finish entering content and settings for the template, choose **Create**\.

## Creating a push notification template with raw message data<a name="message-templates-creating-push-raw"></a>

Complete this procedure if you want to specify the raw message payload manually\. You only need to specify the raw message payload if you want to use a feature of a specific push notification service that Amazon Pinpoint doesn't allow you to configure\. If you don't need to specify the raw message content, you should complete the procedure in [Creating a standard push notification template](#message-templates-creating-push-standard) instead\.

An example of a use case that requires you to use a raw message template is when you want to send messages to users of the desktop Safari web browser\. In this case, you need to include a specific attribute in the raw message payload\. For more information, see [Sending Safari web push notifications](channels-push-safari.md)\.

**To create a push notification template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. Choose **Create template**\.

1. Under **Channel**, choose **Push notifications**\.

1. Under **Template details**, for **Template name**, enter a name for the template\. The name has to begin with a letter or number\. It can contain up to 128 characters\. The characters can be letters, numbers, underscores \(\_\), or hyphens \(‐\)\.

1. \(Optional\) For **Version description**, enter a brief description of the template\. The description can contain up to 500 characters\.

1. Under **Push notification details**, for **Notification type**, choose **Raw message**\. The message editor displays an outline of the code to use for the template\. In the message editor, enter the settings that you want to use for each push notification service, including any optional settings—such as images, sounds, and actions—that you want to specify for the template\. For more information, see the documentation for the push notification services that you use\.

1. When you finish entering the raw message content, choose **Create**\.

If you want to test the template before you use it in a push notification that you send to users, you can [send a test notification](messages-mobile.md) that uses the template\. If you do this, ensure that you first complete step 10 to specify default values for all the variables in the template\. Otherwise, the push notification might not be sent or it might not render correctly\.