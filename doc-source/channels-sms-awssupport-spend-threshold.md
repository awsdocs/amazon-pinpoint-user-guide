# Requesting increases to your monthly SMS spending quota for Amazon Pinpoint<a name="channels-sms-awssupport-spend-threshold"></a>

Your spending quota determines how much money you can spend sending SMS messages through Amazon Pinpoint each month\. When Amazon Pinpoint determines that sending an SMS message would incur a cost that exceeds your spending quota for the current month, it stops publishing SMS messages within minutes\.

**Important**  
Because Amazon Pinpoint is a distributed system, it stops sending SMS messages within minutes of the spending quota being exceeded\. During this period, if you continue to send SMS messages, you might incur costs that exceed your quota\.

We set the spending quota for all new accounts at $1\.00 \(USD\) per month\. This quota is intended to let you test the message\-sending capabilities of Amazon Pinpoint\. This quota also helps to reduce the risk of sending large campaigns before you're actually ready to use Amazon Pinpoint for your production workloads\. Finally, this quota is necessary to prevent malicious users from abusing Amazon Pinpoint\.

You can request an increase to the SMS spending quota for your account by opening a quota increase case in the AWS Support Center\. Note that spending limits are region\-specific as they vary by region\. Because of this you must specify the regions where you require an increase\.

## Step 1: Open an Amazon Pinpoint SMS case<a name="channels-sms-awssupport-spend-threshold-open"></a>

You can request an increase to your monthly spending quota by opening a quota increase case in the AWS Support Center\.

**Note**  
Some of the fields on the request form are marked as "optional\." However, AWS Support requires all of the information that's mentioned in the following steps in order to process your request\. If you don't provide all of the required information, you may experience delays in processing your request\.

**To request a spending quota increase**

1. Sign in to the AWS Management Console at [https://console\.aws\.amazon\.com/](https://console.aws.amazon.com/)\.

1. On the **Support** menu, choose **Support Center**\.

1. On the **Your support cases** pane, choose **Create case**\.

1. Choose the **Looking for service limit increases?** link\.

1. Choose **Service limit increase**, then complete the following:
   + For **Limit type**, choose **Pinpoint SMS**\.
   + \(Optional\) For **Provide a link to the site or app which will be sending SMS messages**, provide information about the website, application, or service that will send SMS messages\.
   + \(Optional\) For **What type of messages do you plan to send**, choose the type of message that you plan to send using your long code:
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
   + For **Resource Type**, choose** General Limits**\.
   + For **Limit**, choose **Account Spend Threshold Increase**\.

1. For New limit value, enter the maximum amount \(in USD\) that you can spend on SMS each calendar month\.

1. Under **Case description**, for **Use case description**, provide the following details:
   + The website or app of the company or service that's sending SMS messages\.
   + The service that's provided by your website or app, and how your SMS messages contribute to that service\.
   + How users sign up to voluntarily receive your SMS messages on your website, app, or other location\.

   If your requested spending quota \(the value you specified for **New quota value**\) exceeds $10,000 \(USD\), provide the following additional details for each country that you're messaging:
   + Whether you're using a sender ID or short code\. If you're using a sender ID, provide:
     + The sender ID\.
     + Whether the sender ID is registered with wireless carriers in the country\.
   + The maximum expected transactions\-per\-second \(TPS\) for your messaging\.
   + The average message size\.
   + The template for the messages that you send to the country\.
   + \(Optional\) Character encoding needs, if any\.

1. \(Optional\) If you want to submit any further requests, choose **Add another request**\. If you include multiple requests, provide the required information for each\. For the required information, see the other sections within [Requesting support for SMS messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

1. Under **Contact options**, for **Preferred contact language**, choose whether you want to receive communications for this case in **English** or **Japanese**\.

1. When you finish, choose **Submit**\.

The AWS Support team provides an initial response to your request within 24 hours\.

In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. If we’re able to do so, we'll grant your request within this 24\-hour period\. However, if we need to obtain additional information from you, it might take longer to resolve your request\.

We might not be able to grant your request if your use case doesn’t align with our policies\.

## Step 2: Update your SMS settings on the Amazon Pinpoint console<a name="channels-sms-awssupport-spend-threshold-settings"></a>

After we notify you that your monthly spending quota has been increased, you have to adjust the spending quota for your account on the Amazon Pinpoint console\.

**To adjust your spending quota on the console**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project that uses the SMS channel\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. In the **SMS and voice** section, choose **Edit**\.

1. Under **Account\-level settings**, for **Account spending limit**, enter the maximum amount, in US Dollars, that you want to spend on SMS messages each calendar month\. You can specify a value that's less than or equal to the total monthly spending quota provided by AWS Support\. By setting a lower value, you can control your monthly spending while still retaining the capacity to scale up if necessary\.

1. Choose **Save changes**\.