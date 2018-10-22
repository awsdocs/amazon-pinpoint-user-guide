# Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint<a name="channels-sms-awssupport-spend-threshold"></a>

Your monthly spend threshold sets how much you can spend each calendar month on SMS messaging when you use Amazon Pinpoint\. When Amazon Pinpoint determines that sending an SMS message would incur a cost that exceeds your spend threshold for that month, it stops publishing SMS messages within minutes\.

**Important**  
Because Amazon Pinpoint is a distributed system, it stops sending SMS messages within a time interval of minutes of the spend limit being exceeded\. During that interval, if you continue to send SMS messages, you might incur costs that exceed your limit\.

By default, the spend threshold is $1\.00 \(USD\)\. For information about SMS pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/)\.

Typically, AWS Support processes your case within 2 business days\. Depending on the spend limit you request and the complexity of your case, AWS Support might require an additional 3–5 days to ensure that your request can be processed\.

To request a spend threshold increase, complete the following steps\.

## Step 1: Open an Amazon Pinpoint SMS Case<a name="channels-sms-awssupport-spend-threshold-open"></a>

Open a case with AWS Support by completing the following steps\.

1. Sign in to the AWS Management Console, and go to the [AWS Support Center](https://console.aws.amazon.com/support/home#/)\.

1. Choose **Create case**\.

1. For **Regarding**, choose **Service Limit Increase**\.

1. For **Limit Type**, choose **Pinpoint SMS**\.

## Step 2: Specify Your Request<a name="channels-sms-awssupport-spend-threshold-request"></a>

Tell AWS Support that you're requesting a spend threshold increase by completing the following steps\.

1. For **Resource Type**, choose **General Limits**\.

1. For **Limit**, choose **Account Spend Threshold Increase**\.

1. For **New limit value**, type the maximum amount in USD that you'll spend on SMS messages each calendar month\.

1. \(Optional\) If you want to include multiple requests in this support case, choose **Add another request**\. Then, specify the type of request\.

   If you include multiple requests, provide the required information for each\. For the required information, see the other sections within [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

## Step 3: Describe Your SMS Use Case<a name="channels-sms-awssupport-spend-threshold-usecase"></a>

Describe how you use SMS messaging by completing the following steps\.

1. For **Link to site or app which will be sending SMS**, identify the website or application where your audience members will opt in to receive your SMS messages\.

1. For **Type of messages**, choose the type of SMS message that you send:
   + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or transaction alerts\. Transactional messages must not contain promotional content\.
   + **Promotional** – Noncritical messages that promote your business or service, such as special offers or announcements\.
   + **One Time Passwords** – Messages that provide passwords to authenticate with your website or application\.

1. For **Targeted Countries**, specify the countries that you send SMS messages to\. For more information, see [Supported Countries and Regions](channels-sms-countries.md)\.

   If your list of countries exceeds the character limit for this text box, you can instead specify your countries in the **Use Case Description** box\.

1. For **Use Case Description**, provide the following details:
   + The website or app of the company or service that's sending SMS messages\.
   + The service that's provided by your website or app, and how your SMS messages contribute to that service\.
   + How users sign up to voluntarily receive your SMS messages on your website, app, or other location\.

   If your requested spend threshold \(the value you specified for **New limit value**\) exceeds 10,000 USD, provide the following additional details for each country that you're messaging:
   + Whether you're using a sender ID or short code\. If you're using a sender ID, provide:
     + The sender ID\.
     + Whether the sender ID is registered with wireless carriers in the country\.
   + The maximum expected transactions\-per\-second \(TPS\) for your messaging\.
   + The average message size\.
   + The template for the messages that you send to the country\.
   + \(Optional\) Character encoding needs, if any\.

1. When you finish, choose **Submit**\. 

## Step 4: Update Your SMS Settings in the Amazon Pinpoint Console<a name="channels-sms-awssupport-spend-threshold-settings"></a>

After AWS notifies you that your monthly spend threshold is increased, complete the following steps\.

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose a project that uses the SMS channel\.

1. In the navigation pane, under **Settings**, choose **SMS**\.

1. Next to **General**, choose **Edit**\.

1. Under **Account\-level settings**, for **Account spend limit**, type the maximum amount, in US Dollars, that you want to spend on SMS messages each calendar month\. You can specify a value that's less than or equal to the total monthly spending limit provided by AWS Support\. By setting a lower value, you can control spending while retaining the capacity to scale up as needed\.

1. Choose **Save changes**\.