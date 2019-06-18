# Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint<a name="channels-sms-awssupport-spend-threshold"></a>

Your spending limit determines how much money you can spend sending SMS messages through Amazon Pinpoint each month\. When Amazon Pinpoint determines that sending an SMS message would incur a cost that exceeds your spending limit for the current month, it stops publishing SMS messages within minutes\.

**Important**  
Because Amazon Pinpoint is a distributed system, it stops sending SMS messages within minutes of the spending limit being exceeded\. During this period, if you continue to send SMS messages, you might incur costs that exceed your limit\.

We set the spending limit for all new accounts at $1\.00 \(USD\) per month\. This limit is intended to let you test the message\-sending capabilities of Amazon Pinpoint\. This limit also helps to reduce the risk of sending large campaigns before you're actually ready to use Amazon Pinpoint for your production workloads\. Finally, this limit is necessary to prevent malicious users from abusing Amazon Pinpoint\.

AWS Support typically processes your case within 2 business days\. Depending on the spending limit that you request and the complexity of your case, AWS Support might require an additional 3–5 days to ensure that your request can be processed\.

## Step 1: Open an Amazon Pinpoint SMS Case<a name="channels-sms-awssupport-spend-threshold-open"></a>

You can request an increase to your monthly spending limit by opening a Service Limit Increase case in the AWS Support Center\.

**Note**  
Some of the fields on the request form are marked as "optional\." However, AWS Support requires all of the information that's mentioned in the following steps in order to process your request\. If you don't provide all of the required information, you may experience delays in processing your request\.

**To request a spending limit increase**

1. Log in to your AWS account, and then go to the [AWS Support Center](https://console.aws.amazon.com/support/home#/)\.

1. Choose **Create case**\.

1. Under **Create case**, choose **Service limit increase**\.

1. In the **Case classification** section, do the following:

   1. For **Limit type**, choose **Pinpoint SMS**\.

   1. For **Link to site or app which will be sending SMS**, enter the URL of the website for your service or application\.

   1. For **Type of messages**, choose the type of SMS messages that you plan to send:
      + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or account alerts\. Transactional messages can't contain promotional or marketing content\.
      + **Promotional** – Noncritical messages that promote your business or service, such as special offers or announcements\.
      + **One Time Passwords** – Messages that provide passwords that your customers use to authenticate with your website or application\.

   1. For **Targeted Countries**, specify the countries that you send SMS messages to\. For more information, see [Supported Countries and Regions](channels-sms-countries.md)\.

      If your list of countries exceeds the character limit for this text box, you can instead specify your countries in the **Use Case Description** box\.

1. In the **Requests** section, do the following:

   1. For **Resource Type**, choose **General Limits**\.

   1. For **Limit**, choose **Account Spend Threshold Increase**\.

   1. For **New limit value**, type the maximum amount \(in USD\) that you'll spend on SMS messages each calendar month\.

   1. \(Optional\) If you want to include more than one request in this support case, choose **Add another request**\. Then, specify the type of request\.

      If you include multiple requests, provide the required information for each\. For the required information, see the other sections within [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

1. In the **Case description** section, for **Use case description**, provide the following details:
   + The website or app of the company or service that's sending SMS messages\.
   + The service that's provided by your website or app, and how your SMS messages contribute to that service\.
   + How users sign up to voluntarily receive your SMS messages on your website, app, or other location\.

   If your requested spend threshold \(the value you specified for **New limit value**\) exceeds $10,000 \(USD\), provide the following additional details for each country that you're messaging:
   + Whether you're using a sender ID or short code\. If you're using a sender ID, provide:
     + The sender ID\.
     + Whether the sender ID is registered with wireless carriers in the country\.
   + The maximum expected transactions\-per\-second \(TPS\) for your messaging\.
   + The average message size\.
   + The template for the messages that you send to the country\.
   + \(Optional\) Character encoding needs, if any\.

1. When you finish, choose **Submit**\. 

The AWS Support team provides an initial response to your request within 24 hours\.

In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. If we’re able to do so, we'll grant your request within this 24\-hour period\. However, if we need to obtain additional information from you, it might take longer to resolve your request\.

We might not be able to grant your request if your use case doesn’t align with our policies\.

## Step 2: Update Your SMS Settings in the Amazon Pinpoint Console<a name="channels-sms-awssupport-spend-threshold-settings"></a>

After we notify you that your monthly spend threshold has been increased, you have to adjust the spending limit for your account in the Amazon Pinpoint console\.

**To adjust your spending limit in the console**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project that uses the SMS channel\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. In the **SMS and voice** section, choose **Edit**\.

1. Under **Account\-level settings**, for **Account spending limit**, type the maximum amount, in US Dollars, that you want to spend on SMS messages each calendar month\. You can specify a value that's less than or equal to the total monthly spending limit provided by AWS Support\. By setting a lower value, you can control your monthly spending while still retaining the capacity to scale up if necessary\.

1. Choose **Save changes**\.