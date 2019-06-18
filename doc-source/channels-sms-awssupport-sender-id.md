# Requesting Sender IDs for SMS Messaging with Amazon Pinpoint<a name="channels-sms-awssupport-sender-id"></a>

A sender ID is a custom name that's displayed as the message sender on the receiving device\. For example, you can use your business brand to make the message source easier to recognize\.

Support for sender IDs varies by country or region\. For example, messages delivered to U\.S\. phone numbers don't display the sender ID\. For the countries and regions that support sender IDs, see [Supported Regions and Countries](https://docs.aws.amazon.com/sns/latest/dg/sms_supported-countries.html)\.

**Important**  
If you're new to SMS messaging with Amazon Pinpoint, request a monthly SMS spend threshold that meets the expected demands of your SMS use case\. By default, your monthly spend threshold is $1\.00 \(USD\)\. You can request to increase your spend threshold in the same support case that includes your request for a sender ID\. Or, if you prefer, you can open a separate case\. For more information, see [Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

When we receive your request for a sender ID, we respond within 24 business hours\. It typically takes 2–4 weeks to provision a sender ID, but in some countries and regions, it might take longer\. When we respond to your request, we provide an estimate of the amount of time it will take to obtain your sender ID\.

## Step 1: Open an Amazon Pinpoint SMS Case<a name="channels-sms-awssupport-sender-id-open"></a>

You can request a sender ID by creating a new case in the AWS Support Center\.

**To request a sender ID**

1. Sign in to the AWS Management Console, and go to the [AWS Support Center](https://console.aws.amazon.com/support/home#/)\.

1. Choose **Create case**\.

1. Under **Create case**, choose **Service limit increase**\.

1. Under **Case classification**, do the following:

   1. For **Limit Type**, choose **Pinpoint SMS**\.

   1. For **Link to site or app which will be sending SMS**, identify the website or application where your audience members opt in to receive your SMS messages\.

   1. For **Type of messages**, choose the type of message that you plan to send using your sender ID:
      + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or transaction alerts\. Transactional messages must not contain promotional content\.
      + **Promotional** – Noncritical messages that promote your business or service, such as special offers or announcements\.
      + **One Time Password** – Messages that provide passwords to authenticate with your website or application\.

   1. For **Targeted Countries**, specify the countries where you want to register a sender ID\. Support for sender IDs and sender ID registration requirements vary by country\. For more information, see [Supported Countries and Regions](channels-sms-countries.md)\.

      If your list of countries exceeds the character limit for this text box, you can instead specify the countries in the **Use Case Description** box\.

1. Under **Requests**, do the following:

   1. For **Resource Type**, choose **General Limits**\.

   1. For **Limit**, choose **SenderID Registration**\.

   1. For **New limit value**, type the number of sender IDs that you're requesting\. Typically, this value is **1**\.

After we receive your request, we provide an initial response within 24 hours\. We might contact you to request additional information\.

If we're able to provide you with a Sender ID, we send you an estimate of the amount of time that's required to provision it\. In many countries, we can provide you with a Sender ID within 2–4 weeks\. However, in some countries and regions, it can take several weeks to obtain a Sender ID\.

In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. We might not be able to grant your request if your use case doesn’t align with our policies\.

## Step 2: Update Your SMS Settings in the Amazon Pinpoint Console<a name="channels-sms-awssupport-sender-id-settings"></a>

When we complete the process of obtaining your sender ID, we respond to your case\. When you receive this notification, complete the steps in this section to configure Amazon Pinpoint to use your sender ID\.

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project that uses the SMS channel\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. Next to **SMS settings**, choose **Edit**\.

1. Under **Account\-level settings**, for **Default sender ID**, type your sender ID\.

1. Choose **Save changes**\.

## Next Steps<a name="channels-sms-awssupport-sender-id-next"></a>

You've registered a sender ID and updated your settings in the Amazon Pinpoint console\. Now you can use Amazon Pinpoint to send SMS messages with your sender ID\. SMS recipients in supported countries will see your sender ID as the message sender on their devices\. 

To engage an audience segment with an SMS campaign, see [Amazon Pinpoint Campaigns](campaigns.md)\.

To send an SMS message directly to a limited audience without creating a campaign, see [Send Test Messages with Amazon Pinpoint](messages.md)\.