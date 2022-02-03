# Creating in\-app templates<a name="message-templates-creating-inapp"></a>

An *in\-app template* is a template for messages that you send from Amazon Pinpoint to users of your application\. Use in\-app templates to create, save, and reuse settings and content for your in\-app messages\.

When you create an in\-app template, you specify the settings and content that you want to reuse in the body of the in\-app messages that use the template\. When you create a message using the template, Amazon Pinpoint populates the message with the settings and content that you defined\.

In\-app messages are highly customizable\. They can include buttons that open websites or take users to specific parts of your app\. You can configure background and text colors, position the text, and add images to the notification\. You can send a single message, or create a *carousel* that contains up to five unique messages that your users can scroll through\.

**To create an in\-app template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. Choose **Create template**\.

1. Under **Channel**, choose **In\-app messaging**\.

1. Under **Template details**, for **Template name**, enter a name for the template\. The name has to begin with a letter or number\. It can contain up to 128 characters\. The characters can be letters, numbers, underscores \(\_\), or hyphens \(‐\)\.

1. \(Optional\) For **Version description**, enter a brief description of the template\. The description can contain up to 500 characters\.

1. In the **In\-app message details** section, under **Layout**, choose the type of layout for the message template\. You can choose from the following options:
   + **Top banner** – a message that appears as a banner at the top of the page\.
   + **Bottom banner** – a message that appears as a banner at the bottom of the page\.
   + **Middle banner** – a message that appears as a notification in the middle of the page\.
   + **Full screen** – a message that covers entire screen\.
   + **Modal** – a message that appears in a window in front of the page\.
   + **Carousel** – a scrollable layout of up to five unique messages\.

1. Under **Header**, configure the title that appears at the beginning of the message\. If you created a Carousel message, you must create the first message for the Carousel, which includes the header\.

   1. For **Header text** to display in the banner\. You can enter up to 64 characters\.

   1. For **Header text color**, choose the text color for the header\. You can optionally enter RGB values or a hex color code\.

   1. For **Header alignment**, choose whether you want the text to be **Left**, **Center**, or **Right** justified\.

1. Under **Message**, configure the body of the message\.

   1. For **Message**, enter the body text for the message\. The message can contain up to 150 characters\.

   1. For **Text color**, choose the text color for the message body\. You can optionally enter RGB values or a hex color code\.

   1. For **Text alignment**, choose whether you want the text to be **Left**, **Center**, or **Right** justified\.

1. \(Optional\) Change the background color of the message\. Under **Background **, choose a background color for the message\. You can optionally enter RGB values or a hex color code\.

1. \(Optional\) Add an image to the message\. Under **Image URL**, enter the URL of the image that you want to appear in the message\. Only \.jpg and \.png files are accepted\. The dimensions of the image depend on the message type:
   + For a **Banner**, the image should be 100 pixels by 100 pixels, or a 1:1 aspect ratio\.
   + For a **Carousel**, the image should be 300 pixels by 200 pixels, or a 3:2 aspect ratio\.
   + For a **Fullscreen** message, the image should be 300 pixels by 200 pixels, or a 3:2 aspect ratio\.

1. \(Optional\) Add a button to the message\. Under **Primary button**, do the following:

   1. Choose **Add primary button**\.

   1. For **Button text**, enter the text to display on the button\. You can enter up to 64 characters\.

   1. \(Optional\) For **Button text color**, choose a color for the button text\. You can optionally enter RGB values or a hex color code\.

   1. \(Optional\) For **Background color**, choose a background color for the button\. You can optionally enter RGB values or a hex color code\.

   1. \(Optional\) For **Border radius**, enter a radius value\. Lower values result in sharper corners, while higher numbers result in more rounded corners\. 

   1. Under **Actions**, choose the event that occurs when the user taps the button:
      + **Close** – Dismisses the message\.
      + **Go to URL** – Opens a website\.
      + **Go to deep link** – Opens an app or opens a particular place in an app\. 

      If you want the button behavior to be different for different device types, you can override the default action\. Under **Action**, use the tabs to choose the device type that you want to modify the button behavior for\. For example, choose **iOS** to modify the button behavior for iOS devices\. Next, choose **Override the default actions**\. Finally, specify an action\.

1. \(Optional\) Add a secondary button to the message\. Under **Secondary button**, choose **Add secondary button**\. Follow the procedures in the preceding step to configure the secondary button\.

1. \(Optional\) Add custom data to the message\. Custom data are key\-value pairs delivered with your message\. For example, you might want to pass a promotional code along with your message\. If you're sending a carousel message, you can add custom data to each of the carousel messages\. To add custom data, do the following:

   1. Under **Custom data**, choose **Add new item**\.

   1. Enter a **Key**\. For example, this might be *PromoCode*\. 

   1. Enter a **Value** for the key\. Your *PromoCode* might be *12345*\.

   1. When the message is sent, the code *12345* is included in your message\.

   1. To add more key\-value pairs, choose **Add new item**\. You can add up to 10 key\-value pairs to the message\. When you finish adding custom data, proceed to the next step\.

1. If your message is a carousel, you can add up to four more unique messages\. To add messages to a carousel, expand the **Carousel overview** section\. Next, choose **Add new message**\. Repeat the preceding steps to configure the message\.

   As you add messages to the carousel, the **Preview** page updates by displaying icons at the bottom of page showing the number of messages included in the carousel\.

   The following image shows a carousel with two messages:  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-inapp-carousel.png)

1. When you finish, choose **Create**\.