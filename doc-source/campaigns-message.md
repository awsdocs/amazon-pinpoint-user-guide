# Step 3: Write the Message<a name="campaigns-message"></a>

After you specify the target segment for the campaign, you can write the message for the campaign\. 

If you set up the campaign as a standard campaign, you write a single message\. If you set up the campaign as an A/B test campaign, you define two or more *treatments*\. A treatment is a variation of your message that the campaign sends to different portions of the segment\.

**Prerequisite**  
Before you begin, complete [Step 2: Specify the Audience for the Campaign](campaigns-segment.md)\.

## Set Up the Campaign<a name="campaigns-message-channel"></a>

1. If you created this campaign as an A/B test campaign \(as opposed to a standard campaign\), specify the percentage of segment members who should receive each treatment\. An A/B test campaign can include up to five treatments\. Choose **Add another treatment** to add additional treatments\.

1. On the **Create your message** page, write the message for the campaign\. The message options vary depending on the channel that you chose for the campaign\.

   If you chose **Email**, see [Writing an Email Message](#campaigns-message-email)\.

   If you chose **SMS**, see [Writing an SMS Message](#campaigns-message-sms)\.

   If you chose **Push notifications**, see [Writing a Push Notification](#campaigns-message-mobile)\.

### Writing an Email Message<a name="campaigns-message-email"></a>

This section contains information about writing an email message\.

1. Under **Email details**, for **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. If you choose to use an existing template, choose the template from the **Template** list\.

1. For **Subject**, enter the subject line for your email message\.

1. For **Message**, enter the email body\.
**Tip**  
You can enter the email body by using either HTML or Design view\. In the HTML view, you can manually enter HTML content for the email body, including formatting, links, and other features that you want to include in the message\. In the Design view, you can use a rich text editor to enter the content, and you can use the formatting toolbar to apply formatting and add links and other features to the content\. To switch views, choose **HTML** or **Design** from the view selector above the message editor\.

1. \(Optional\) Under **Plain text version**, enter a version of your message for email applications that don't display HTML\.

1. If you created this campaign as an A/B test campaign \(as opposed to a standard campaign\), repeat the steps in this section for each treatment\. You can switch between treatments by using the tabs at the top of the **Email details** section\.

1. Choose **Next**\.

### Writing an SMS Message<a name="campaigns-message-sms"></a>

This section contains information about writing an SMS message\.

1. For **Message type**, choose one of the following:
   + **Promotional** – Noncritical messages, such as marketing messages\. Amazon Pinpoint optimizes the message delivery to incur the lowest cost\.
   + **Transactional** – Critical messages that support customer transactions, such as one\-time passwords for multi\-factor authentication\. Amazon Pinpoint optimizes the message delivery to achieve the highest reliability\.

   This campaign\-level setting overrides your default message type, which you set on the SMS settings page for the project\.

1. For **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. If you choose to use an existing template, choose the template from the **Template** list\.

1. For **Message**, type the message body\. Your text message can have up to 160 characters\.

1. \(Optional\) For **Sender ID**, type a custom ID that contains up to 11 alphanumeric characters, including at least one letter and no spaces\. The sender ID is displayed as the message sender on the receiving device\. For example, you can use your business brand to make the message source easier to recognize\.

   Support for sender IDs varies by country or region\. For more information, see [Supported Countries and Regions \(SMS Channel\)](channels-sms-countries.md)\.

   This message\-level sender ID overrides your default sender ID, which you set on the SMS settings page for the project\.

1. If you created this campaign as an A/B test campaign \(as opposed to a standard campaign\), repeat the steps in this section for each treatment\. You can switch between treatments by using the tabs at the top of the **SMS details** section\.

1. Choose **Next**\.

### Writing a Push Notification<a name="campaigns-message-mobile"></a>

This section contains information about writing a push notification and setting up the action that occurs when a recipient taps the notification\.

**Choose the notification type**
+ For **Notification type**, choose one of the following options:
  + **Standard notification** – A push notification with a title and message\. Recipients are alerted by their mobile devices when they receive the notification\.
  + **Silent notification** – A custom JSON attribute\-value pair that Amazon Pinpoint sends to your app without producing notifications on recipients' devices\. Use silent notifications to send data that your app code is designed to receive and handle\. For example, you can use silent notifications to update the app's configuration or to show messages in an in\-app message center\.

#### To create a standard notification<a name="campaigns-message-mobile-standard"></a>

**To write a standard notification**

1. For **Message content**, choose whether you want to **Create a new message** or **Use an existing template**\. If you choose to use an existing template, choose the template from the **Template** list\.

1. For **Title**, enter the title you want to display above the message\.

1. For **Message**, enter the message body\. Your push notification can have up to 200 characters\. A character counter below the left edge of the field counts down from 200 as you add characters to the message\.

1. For **Action**, select the action you want to occur when recipients tap the notification:
   + **Open your app** – Your app launches, or it becomes the foreground app if it has been sent to the background\.
   + **Go to a URL** – The default mobile browser on the user's device launches and opens a web page at the URL you specify\. For example, this action can be useful for sending users to a blog post\.
   + **Open a deep link** – Your app opens to a specific page or component\. For example, this action can be useful to direct users to special promotions for in\-app purchases\.

1. \(Optional\) Under **Media URLs**, you can optionally provide URLs that point to media files that are displayed in your push notification\. The URLs must be publicly accessible so that the push notification services for Android or iOS can retrieve the images\.

1. If you created this campaign as an A/B test campaign \(as opposed to a standard campaign\), repeat the steps in this section for each treatment\. You can switch between treatments by using the tabs at the top of the **Push notification details** section\.

1. Choose **Next**\.

#### To create a silent notification<a name="campaigns-message-mobile-silent"></a>

**To create a silent notification**

1. For **Message content**, enter the content of the silent message in JSON format\. The exact content of the message varies depending on the notification service you use and the values that your application expects to receive\.

1. If you created this campaign as an A/B test campaign \(as opposed to a standard campaign\), repeat the steps in this section for each treatment\. You can switch between treatments by using the tabs at the top of the **Push notification details** section\.

1. Choose **Next**\.

## Use Message Variables<a name="campaigns-message-variables"></a>

To create a message that's personalized for each recipient, use message variables\. Message variables refer to specific *endpoint* attributes\. These attributes can include characteristics that you add to the endpoint resource, such as the recipient's name, city, device, or operating system\. When Amazon Pinpoint sends the message, it substitutes the variables with the corresponding attribute values for the receiving endpoint\. For information about the attributes that you can use, see [Endpoint Properties](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-endpoints-endpoint-id.html#apps-application-id-endpoints-endpoint-id-properties) in the *Amazon Pinpoint API Reference*\.

To include a variable in your message, enclose the attribute name in double brackets, as in `{{Demographic.AppVersion}}`\.

Often, the most useful endpoint attribute for message variables is `{{Attributes.customAttributeName}}`, where `customAttributeName` refers to custom attributes that you add to the endpoint\. By using custom attributes for your variables, you can display personalized messages that are unique for each recipient\.

For example, if your app is a fitness app for runners and it includes custom attributes for the user's name, activity, and personal record, you could use variables in the following message:

`Hey {{Attributes.userName}}, congratulations on your new {{Attributes.activity}} PR of {{Attributes.personalRecord}}!`

When Amazon Pinpoint delivers this message, the content varies for each recipient after the variables are substituted\. Possible final messages are:

`Hey Jane Doe, congratulations on your new half marathon PR of 1:42:17!`

Or:

`Hey John Doe, congratulations on your new 5K PR of 20:52!`

For examples of custom attributes for your app's code, see the [iOS example](https://docs.aws.amazon.com/pinpoint/latest/developerguide/mobile-sdk-ios-register.html#mobile-sdk-ios-custom-attributes) or the [Android example](https://docs.aws.amazon.com/pinpoint/latest/developerguide/mobile-sdk-android-register.html#mobile-sdk-android-custom-attributes) in the *Amazon Pinpoint Developer Guide*\.

## Test the Message<a name="campaigns-message-test"></a>

Amazon Pinpoint can display a preview of an email message that you can view before you schedule the message to be sent\. For email and other types of messages, you can also send a test message to a small group of recipients for testing purposes\. You can send test messages for email, SMS, and mobile push campaigns\.

### Previewing an Email Message Without Sending It<a name="campaigns-message-test-preview"></a>

The Design view in the Amazon Pinpoint message editor shows a preview of an email message as it would appear if it was rendered by your web browser\.

If you're working in HTML view, instead of Design view, you can display a preview of an email message next to the HTML content of the message\. This feature is helpful when you want to verify that a message renders as you expect, before you send a test\. 

Note that this preview only shows how the message would appear if it was rendered by your web browser\. As a best practice, you should still send test emails to several recipients and view those test messages by using a variety of devices and email clients\.

**To preview an email**

1. In the area above the HTML view of the message editor, choose **No preview**, and then choose **Preview**\. Amazon Pinpoint displays a preview pane next to the HTML editor\.

1. \(Optional\) To display the HTML content and the preview in a larger window, choose **Fullscreen** in the area above the message editor\.

### Sending a Test Message<a name="campaigns-message-test-send"></a>

It's often helpful to send a test message to actual recipients in order to make sure that your message appears correctly when your customers receive it\. By sending a test version of a message, you can test incremental improvements to the content and appearance of your message without impacting the status of your campaign\.

When you send test messages, consider the following factors:
+ You're charged for sending test messages as if they were regular campaign messages\. For example, if you send 10,000 test emails in a month, you're charged $1\.00 \(USD\) for sending the test emails\. For more information about pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/)\.
+ Test messages count toward your account's sending limits\. For example, if your account is authorized to send 10,000 emails per 24\-hour period, and you send 100 test emails, you can send up to 9,900 additional emails in the same 24\-hour period\.
+ When you send a test message to specific users, you can specify up to 10 addresses\. Use commas to separate multiple addresses\.
**Note**  
The word "address" \(as it's used in this section\) can refer to any of the following: an email address, a mobile phone number, an endpoint ID, or a device token\.
+ When you send a test SMS message to specific phone numbers, the numbers must be listed in E\.164 format\. That is, they must include a plus sign \(\+\), the country code without a leading zero, and the complete subscriber number, including area code—for example, \+12065550142\. E\.164\-formatted numbers shouldn't contain parentheses, periods, hyphens, or any symbols other than the plus sign\. E\.164 phone numbers can have a maximum of 15 digits\.
+ When you send a test push notification, the addresses must be either endpoint IDs or device tokens\.
+ When you send a test message to a segment, you can only choose one segment\. Additionally, you can only choose segments that contain 100 endpoints or fewer\.
+ When you send a test message to a segment, Amazon Pinpoint creates a campaign for that test\. The name of the campaign contains the word "test", followed by four random alphanumeric characters, followed by the name of the campaign\. These campaigns aren't counted toward the maximum number of active campaigns that your account can contain\. Amazon Pinpoint doesn't create a new campaign when you send a test message to specific recipients\.
+ Events that are associated with test messages are counted in the metrics for the parent campaign\. For example, the **Endpoint deliveries** chart on the **Campaigns** analytics page includes the number of test messages that were successfully delivered\.

There are two ways to send a test message\. You can send it to an existing segment or you can send it to a list of addresses that you specify\. The best method depends on your use case\. For example, if you have a regular group of people who test your messages, you might find it helpful to create a segment that contains all of their endpoints\. If you need to send test messages to a group of testers that changes regularly, or to a dynamically generated address, you might find it easier to specify your recipients manually\.

**To send a test message to a segment**

1. Under the message editor, choose **Send a test message**\.

1. In the **Send a test message** dialog box, under **Send a test message to**, choose **A segment**\.

1. Use the drop\-down list to choose the segment that you want to send the test message to\.
**Note**  
Amazon Pinpoint automatically excludes all segments that contain 100 endpoints or more from this list\.

1. Choose **Send message**\.

**To send a test message to specific recipients**

1. Under the message editor, choose **Send a test message**\.

1. In the **Send a test message** dialog box, under **Send a test message to**, choose one of the options in the following table\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/campaigns-message.html)

1. Choose **Send message**\.

**Next**  
[Step 4: Choose When to Send the Campaign](campaigns-schedule.md)