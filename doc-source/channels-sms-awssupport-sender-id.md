# Requesting Sender IDs for SMS Messaging with Amazon Pinpoint<a name="channels-sms-awssupport-sender-id"></a>

A sender ID is a custom name that's displayed as the message sender on the receiving device\. For example, you can use your business brand to make the message source easier to recognize\.

Support for sender IDs varies by country or region\. For example, messages delivered to U\.S\. phone numbers don't display the sender ID\. For the countries and regions that support sender IDs, see [Supported Regions and Countries](https://docs.aws.amazon.com/sns/latest/dg/sms_supported-countries.html)\.

**Important**  
If you're new to SMS messaging with Amazon Pinpoint, request a monthly SMS spend threshold that meets the expected demands of your SMS use case\. By default, your monthly spend threshold is 1\.00 USD\. You can request to increase your spend threshold in the same support case that includes your request for a sender ID\. Or, you can use a separate case\. For more information, see [Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

To request a sender ID, complete the following steps\.

## Step 1: Open an Amazon Pinpoint SMS Case<a name="channels-sms-awssupport-sender-id-open"></a>

Open a case with AWS Support by completing the following steps\.

1. Sign in to the AWS Management Console, and go to the [AWS Support Center](https://console.aws.amazon.com/support/home#/)\.

1. Choose **Create case**\.

1. For **Regarding**, choose **Service Limit Increase**\.

1. For **Limit Type**, choose **Pinpoint SMS**\.

## Step 2: Specify Your Request<a name="channels-sms-awssupport-sender-id-request"></a>

Tell AWS Support that you're requesting a sender ID by completing the following steps\.

1. For **Resource Type**, choose **General Limits**\.

1. For **Limit**, choose **SenderID Registration**\.

1. For **New limit value**, type the number of sender IDs that you're requesting\. Typically, this value is **1**\.

1. \(Optional\) If you want to include multiple requests in this support case, choose **Add another request**\. Then, specify the type of request\.

   If you include multiple requests, provide the required information for each\. For the required information, see the other sections in [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

## Step 3: Describe Your SMS Use Case<a name="channels-sms-awssupport-sender-id-usecase"></a>

Describe how you'll use your sender ID by completing the following steps\.

1. For **Link to site or app which will be sending SMS**, identify the website or application where your audience members will opt in to receive your SMS messages\.

1. For **Type of messages**, choose the type of message that you'll send using your sender ID:

   + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or transaction alerts\. Transactional messages must not contain promotional content\.

   + **Promotional** – Noncritical messages that promote your business or service, such as special offers or announcements\.

   + **One Time Passwords** – Messages that provide passwords to authenticate with your website or application\.

1. For **Targeted Countries**, specify the countries where you want to register a sender ID\. Support for sender IDs and sender ID registration requirements vary by country\. For more information, see [Supported Countries and Regions](channels-sms-countries.md)\.

   If your list of countries exceeds the character limit for this text box, you can instead specify the countries in the **Use Case Description** box\.

1. For **Use Case Description**, provide the following details:

   + The name of your organization \(or the organization associated with the sender ID\)\.

   + The sender ID to register\. Typically, the sender ID can contain up to 11 alphanumeric characters, including at least one letter and no spaces\. These requirements can vary depending on the country you're messaging\.

   + How your sender ID relates to the name of your organization, if that relationship isn't clear\. For example, if your sender ID is an acronym that includes your organization name when expanded, provide the expanded form\.

   + The template for the messages that you'll send with the sender ID\.

1. When you finish, choose **Submit**\.

## Step 4: Update Your SMS Settings in the Amazon Pinpoint Console<a name="channels-sms-awssupport-sender-id-settings"></a>

After AWS notifies you that your sender ID is registered in the targeted countries, complete the following steps\.

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose **Account settings**\.

1. Under **General**, for **Default sender ID**, type your sender ID\.

1. Choose **Save**\.

## Next Steps<a name="channels-sms-awssupport-sender-id-next"></a>

You've registered a sender ID and updated your settings in the Amazon Pinpoint console\. Now you can use Amazon Pinpoint to send SMS messages with your sender ID\. SMS recipients in supported countries will see your sender ID as the message sender on their devices\. 

To engage an audience segment with an SMS campaign, see [Engage Your Audience with Messaging Campaigns](welcome.md#welcome-campaigns)\.

To send an SMS message directly to a limited audience without creating a campaign, see [Direct Messages with Amazon Pinpoint](messages.md)\.