# Requesting short codes for SMS messaging with Amazon Pinpoint<a name="channels-sms-awssupport-short-code"></a>

A short code is a number that you can use for high\-volume SMS message sending\. Short codes are often used for application\-to\-person \(A2P\) messaging, two\-factor authentication \(2FA\), and marketing\. A short code typically contains between three and seven digits, depending on the country or region that it's based in\.

You can only use short codes to send messages to recipients in the same country where the short code is based\. If your use case requires you to use short codes in more than one country, you have to request a separate short code for each country that your recipients are located in\.

For information about short code pricing, see [Amazon Pinpoint pricing](https://aws.amazon.com/pinpoint/pricing/#Dedicated_Short_Codes)\.

## Important considerations<a name="channels-sms-awssupport-short-code-considerations"></a>

Before you request a short code, consider the following information:
+ If you plan to use the short code to send messages that contain Protected Health Information \(PHI\), you should identify this purpose in the **Case description** field of your support case\.
+ Amazon Pinpoint currently only supports standard short codes\. Free\-to\-End\-User \(FTEU\) short codes aren't supported\.
+ If you're new to SMS messaging with Amazon Pinpoint, you should request a monthly SMS spending threshold that meets the expected demands of your SMS use case\. By default, your monthly spending threshold is $1\.00 \(USD\)\. You can request to increase your spending threshold in the same support case that includes your request for a short code\. For more information, see [Requesting increases to your monthly SMS spending quota for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

## Step 1: Open a support case<a name="channels-sms-awssupport-short-code-open"></a>

Open a case with AWS Support by completing the following steps\.

**To request a short code**

1. Sign in to the AWS Management Console at [https://console\.aws\.amazon\.com/](https://console.aws.amazon.com/)\.

1. On the **Support** menu, choose **Support Center**, as shown in the following image\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/console_region_selector.png)

1. On the **Open support cases** tab, choose **Create case**\.

1. Choose **Service limit increase**\.

1. Under **Case details**, complete the following sections:
   + For **Limit type**, choose **Pinpoint SMS**\.
   + \(Optional\) For **Provide a link to the site or app which will be sending SMS messages**, provide information about the website, application, or service that will send SMS messages\.
   + \(Optional\) For **What type of messages do you plan to send**, choose the type of message that you plan to send using your short code:
     + **One Time Password** – Messages that provide passwords that your customers use to authenticate with your website or application\.
     + **Promotional** – Noncritical messages that promote your business or service, such as special offers or announcements\.
     + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or account alerts\. Transactional messages must not contain promotional or marketing content\.
   + \(Optional\) For **Which AWS Region will you be sending messages from**, choose the region that you'll be sending messages from\.
   + \(Optional\) For **Which countries do you plan to send messages to**, enter the country or region that you want to purchase short codes in\.
   + \(Optional\) In the **How do your customers opt to receive messages from you**, provide details about your opt\-in process\.
   + \(Optional\) In the **Please provide the message template that you plan to use to send messages to your customers** field, include the template that you will be using\.

1. Under **Requests**, complete the following sections:
   + For the **Region**, choose the Region from which you'll be sending messages\. 
**Note**  
The Region is required in the **Requests** section\. Even if you provided this information in the **Case details** section you must also include it here\.
   + For **Resource Type**, choose **Dedicated SMS Short Codes**\.
   + For **New limit value**, enter the number of short codes that you want to purchase\.

1. Under **Case description**, for **Use case description**, provide details about your use case\.

1. \(Optional\) If you want to submit any further requests, choose **Add another request**\. For the required information, see the other sections within [Requesting support for SMS messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

1. Under **Contact options**, for **Preferred contact language**, choose whether you want to receive communications for this case in **English** or **Japanese**\.

1. When you finish, choose **Submit**\.
**Important**  
Mobile carriers require us to provide all of the information listed above in order to provision short codes\. We can't process your request until you provide all of this information\.

1. After we receive your request, we will evaluate your requirements and reply back with a Short Code registration form within 24 hours for an initial response\. This form is dependent on your location\.

1. Complete the registration form that is sent to you in its entirety\. Incomplete or insufficient information might result in a delay processing your request\.

1. Once you complete the form, you should reply back to the support case you just filed and attach the form for review\.

After we receive your request, we provide an initial response within 24 hours\. We might contact you to request additional information\. If we're able to provide you with a short code, we send you information about the costs associated with obtaining a short code in the country or region that you specified in your request\. We also provide an estimate of the amount of time that's required to provision a short code in your country or region\. It usually takes several weeks to provision a short code, although this delay can be much shorter or much longer depending on the country or region where the short code is based\.

**Note**  
The fees associated with using short codes begin immediately after we initiate your short code request with carriers\. You're responsible for paying these charges, even if the short code hasn't been completely provisioned yet\. In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. We might not be able to grant your request if your use case doesn't align with our policies\.

## Step 2: Update your SMS settings in the Amazon Pinpoint console<a name="channels-sms-awssupport-short-code-settings"></a>

After we notify you that your short code has been provisioned, complete the following steps\.

**Note**  
You can't complete this steps until we've obtained the short code and associated it with your account\.

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project that the SMS channel is enabled in\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\. 

1. Under **Number settings**, choose the short code\.

1. Under **Default keywords**, verify that the responses for the *HELP* and *STOP* keywords match the values that you specified in your request\.

1. Under **Registered keyword**, verify that the opt\-in keyword and response match the values that you specified in your request\.

1. \(Optional\) If you want to specify additional keyword responses, or if you want to process inbound messages outside of Amazon Pinpoint, you can enable two\-way SMS\. For more information, see [Two\-way SMS settings](settings-sms-managing.md#settings-account-sms-number-2way)\.

1. When you finish, choose **Save**\.

## Next steps<a name="channels-sms-awssupport-short-code-next"></a>

You've registered a short code with wireless carriers and reviewed your settings in the Amazon Pinpoint console\. Now you can use Amazon Pinpoint to send SMS messages with your short code as the origination number\.

To engage an audience segment with an SMS campaign, see [Amazon Pinpoint campaigns](campaigns.md)\.