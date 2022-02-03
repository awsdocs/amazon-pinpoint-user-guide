# Requesting short codes for SMS messaging with Amazon Pinpoint<a name="channels-sms-awssupport-short-code"></a>

A short code is a number that you can use for high\-volume SMS message sending\. Short codes are often used for application\-to\-person \(A2P\) messaging, two\-factor authentication \(2FA\), and marketing\. A short code typically contains between three and seven digits, depending on the country that it's based in\.

You can only use short codes to send messages to recipients in the same country where the short code is based\. If your use case requires you to use short codes in more than one country, you have to request a separate short code for each country that your recipients are located in\.

For information about short code pricing, see [Amazon Pinpoint pricing](http://aws.amazon.com/pinpoint/pricing/#Dedicated_Short_Codes)\.

## Important considerations<a name="channels-sms-awssupport-short-code-considerations"></a>

Before you request a short code, consider the following information:
+ If you plan to use the short code to send messages that contain Protected Health Information \(PHI\), you should identify this purpose in the **Case description** field of your support case\.
+ Amazon Pinpoint currently only supports standard short codes\. Free\-to\-End\-User \(FTEU\) short codes aren't supported\.
+ If you're new to SMS messaging with Amazon Pinpoint, you should request a monthly SMS spending threshold that meets the expected demands of your SMS use case\. By default, your monthly spending threshold is $1\.00 \(USD\)\. You can request to increase your spending threshold in the same support case that includes your request for a short code\. For more information, see [Requesting increases to your monthly SMS spending quota for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

## Step 1: Open a support case<a name="channels-sms-awssupport-short-code-open"></a>

The first step in requesting a short code is to open a Service Limit Increase case in the Support Center Console\.

**To request a short code**

1. Open the Support Center Console at [https://console\.aws\.amazon\.com/support/home](https://console.aws.amazon.com/support/home)\.

1. In the **Open support cases** section, choose **Create case**\.

1. On the **Create case** page, choose **Service limit increase**\.

1. In the **Case details** section, do the following:
   + For **Limit type**, choose **Pinpoint SMS**\.
   + For **Provide a link to the site or app which will be sending SMS messages**, provide information about the website, application, or service that will send SMS messages\.
   + For **What type of messages do you plan to send**, choose the type of messages that you plan to send using your short code:
     + **One Time Password** – Messages that provide passwords that your customers use to authenticate with your website or application\.
     + **Promotional** – Noncritical messages that promote your business or service, such as special offers or announcements\.
     + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or account alerts\. Transactional messages must not contain promotional or marketing content\.
   + For **Which AWS Region will you be sending messages from**, choose the region that you'll be sending messages from\.
**Note**  
A short code can only exist in one AWS Region\. If you want to be able to use short codes in more than one AWS Region, you must request separate short codes for each Region\.
   + For **Which countries do you plan to send messages to**, enter the country that you want to purchase short codes in\.
**Note**  
Each short code is specific to a single country\. For example, you can't use a United States\-based short code to send messages to recipients with Canadian phone numbers\.
   + In the **How do your customers opt to receive messages from you**, provide details about your opt\-in process\.
   + In the **Please provide the message template that you plan to use to send messages to your customers** field, include the template that you will be using\.
**Important**  
Some of the fields on this form are labelled "optional\." However, you must provide *all* of the information listed above to begin the short code setup process\.

1. In the **Requests** section, do the following:
   + For the **Region**, choose the AWS Region that you plan to send messages from\.
**Note**  
The Region is required in the **Requests** section\. Even if you provided this information in the **Case details** section you must also include it here\.
   + For **Resource Type**, choose **Dedicated SMS Short Codes**\.
   + For **Limit**, choose the type of messages that you plan to send using your short code\.
   + For **New limit value**, enter the number of short codes that you want to purchase for the target country and use case\.
**Note**  
If you want to request a short code for a different country, or for a separate use case in the same country, open a separate case in the Support Center Console\. By creating separate cases, you ensure that all communications for a particular country or use case are restricted to a single AWS Support case, which reduces the potential for miscommunications\.

1. Under **Case description**, for **Use case description**, provide details about your use case\.

1. Under **Contact options**, for **Preferred contact language**, choose whether you want to receive communications for this case in **English** or **Japanese**\.

1. When you finish, choose **Submit**\.

AWS Support acknowledges your request within 24 hours of receipt\. If we're able to provide you with a short code, we provide you with a short code registration form as an attachment to your AWS Support case\. Complete the registration form in its entirety\. The information in this form is required in order to set up a short code with the mobile carriers\. For more information about completing this form, see [Obtaining a short code for sending text messages to US recipients](messaging-and-targeting/obtaining-a-short-code-for-sending-text-messages-to-us-recipients-part-1/) on the AWS Messaging and Targeting Blog\. This blog post covers the process of applying for US short codes, but the information it provides is also useful when applying for short codes in other countries\.

There is no Service Level Agreement for the time required to obtain a short code\. The amount of time required depends on whether or not your use case is compliant with the requirements of the carriers\. If the carriers do not think that your use case is compliant, they will reject your application and provide information about the reasons for the rejection\. If this happens, you will find this information in your AWS Support case\. You can address the issues with your application in your AWS Support case\. When you do, we send this updated information back to the carriers so that they can reconsider your application\.

The fees associated with using short codes begin immediately after we initiate your short code request with carriers\. You're responsible for paying these charges, even if the short code hasn't been completely provisioned yet\. In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. We might not be able to grant your request if your use case doesn't align with our policies\.

## Step 2: Update your SMS settings in the Amazon Pinpoint console<a name="channels-sms-awssupport-short-code-settings"></a>

After we notify you that your short code has been provisioned, complete the following steps\.

**Note**  
You can't complete this step until the short code request has been approved and the short code has been added to your AWS account\.

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