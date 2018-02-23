# Requesting Dedicated Long Codes for SMS Messaging with Amazon Pinpoint<a name="channels-sms-awssupport-long-code"></a>

A long code \(also referred to as a long virtual number, or LVN\) is a standard 10\-digit phone number\. Long codes are meant for low\-volume, person\-to\-person communication\. For example, in the United States and Canada, sending rates for long codes are restricted to 1 TPS\. Sending high\-volume traffic to a long code might prompt wireless carriers to block the messages by blacklisting the long code\. Long codes are useful for low\-volume use cases, or for testing your SMS program before you scale up and request a short code\. With Amazon Pinpoint, long codes are supported only for two\-way SMS\.

You can request up to 5 long codes for each country that you'll send SMS messages to\.

**Important**  
If you're new to SMS messaging with Amazon Pinpoint, request a monthly SMS spend threshold that meets the expected demands of your SMS use case\. By default, your monthly spend threshold is 1\.00 USD\. You can request to increase your spend threshold in the same support case that includes your request for a long code\. Or, you can submit a separate case\. For more information, see [Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

After receiving your request, AWS registers your long code in the targeted countries on your behalf\. Typically, AWS Support processes your case within 2 business days\. Depending on the complexity of your case, AWS Support might require an additional 3–5 days to ensure that your request can be processed\.

To request a dedicated long code, complete the following steps\.

## Step 1: Open an Amazon Pinpoint SMS Case<a name="channels-sms-awssupport-long-code-open"></a>

Open a case with AWS Support by completing the following steps\.

1. Sign in to the AWS Management Console, and go to the [AWS Support Center](https://console.aws.amazon.com/support/home#/)\.

1. Choose **Create case**\.

1. For **Regarding**, choose **Service Limit Increase**\.

1. For **Limit Type**, choose **Pinpoint SMS**\.

## Step 2: Specify Your Request<a name="channels-sms-awssupport-long-code-request"></a>

Tell AWS Support that you're requesting a dedicated long code by completing the following steps\.

1. For **Resource Type**, choose **Dedicated SMS Long Codes**\.

1. For **Limit**, choose the type of message that you'll send with your long code:

   + **One\-time Passwords/Two\-Factor Authentication** – Messages that provide passwords to authenticate with your website or application\.

   + **Promotional/Marketing** – Noncritical messages that promote your business or service, such as special offers or announcements\.

   + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or transaction alerts\. Transactional messages must not contain promotional content\.

1. For **New limit value**, specify the number of long codes that you're requesting\. Typically, this value is **1**\. You can request up to 5 long codes for each country in your request\.

1. \(Optional\) If you want to include multiple requests in this support case, choose **Add another request**\. Then, specify the type of request\.

   If you include multiple requests, provide the required information for each\. For the required information, see the other sections in [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

## Step 3: Describe Your SMS Use Case<a name="channels-sms-awssupport-long-code-usecase"></a>

Describe how you'll use your dedicated long code by completing the following steps\.

1. For **Link to site or app which will be sending SMS**, identify the website or application where your audience members will opt in to receive your SMS messages\.

1. For **Type of messages**, choose the type of message that you'll send using your long code: **Transactional**, **Promotional**, or **One Time Passwords**\.

1. For **Targeted Countries**, specify the countries that you're requesting a long code for\. For more information, see [Supported Countries and Regions](channels-sms-countries.md)\.

   If your list of countries exceeds the character limit for this text box, you can instead specify your countries in the **Use Case Description** box\.

1. For **Use Case Description**, provide the following details:

   + The AWS Region where you'll use Amazon Pinpoint to send SMS messages with your long code\.

   + Because long codes are supported only for two\-way SMS, confirm that you require your long code for two\-way SMS purposes\. 

1. When you finish, choose **Submit**\.

## Step 4: Update Your SMS Settings in the Amazon Pinpoint Console<a name="channels-sms-awssupport-long-code-settings"></a>

After AWS notifies you that your long code is registered in the targeted countries, complete the following steps\.

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose **Account settings**\.

1. Under **Number settings**, choose the long code that AWS assigned to your account\. The console shows the **Number settings** page for your long code\. Under **Keywords**, the console provides:

   + The keywords HELP and STOP, and their default response messages\. You can edit the response messages, but you can't edit the keywords\.

   + The default registered keyword and its default response message\. You can edit both of these values\.

1. In the table that contains the keyword or response that you want to edit, choose **Edit**, and make your changes\.

1. \(Optional\) If you want to specify additional keyword responses, or if you want to process inbound messages outside of Amazon Pinpoint, configure two\-way SMS settings\. For more information, see [Two\-Way SMS Settings](settings-account.md#settings-account-sms-number-2way)\.

1. When you finish making your changes, choose **Save**\.

## Next Steps<a name="channels-sms-awssupport-long-code-next"></a>

You've registered a long code and updated your settings in the Amazon Pinpoint console\. Now you can use Amazon Pinpoint to send SMS messages with your long code as the origination number\.

To engage an audience segment with an SMS campaign, see [Engage Your Audience with Messaging Campaigns](welcome.md#welcome-campaigns)\.

To send an SMS message directly to a limited audience without creating a campaign, see [Direct Messages with Amazon Pinpoint](messages.md)\.