# Requesting sender IDs for SMS messaging with Amazon Pinpoint<a name="channels-sms-awssupport-sender-id"></a>

In SMS messaging, a *sender ID* is a name that appears as the message sender on recipients' devices\. Sender IDs are a useful way to identify yourself to the recipients of your messages\.

Support for sender IDs varies by country\. For example, carriers in the United States don't support sender IDs at all, but carriers in India require senders to use sender IDs\. For a complete list of countries that support sender IDs, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.

**Important**  
Some countries require you to register sender IDs before you use them to send messages\. Depending on the country, this registration process might take several weeks\. The countries that require pre\-registered sender IDs are indicated in the table on the [Supported Countries](channels-sms-countries.md) page\.

If you're sending messages to recipients in a country where sender IDs are supported, and that country doesn't require you to register your sender ID, you don't have to perform any additional steps\. You can start sending messages that include sender ID values immediately\.

You only need to complete the procedures on this page if you plan to send messages to a country where registration of sender IDs is required\.

**Note**  
If you plan to send messages to recipients in a country where sender IDs are allowed but not required, you don't need to open a case in the Support Center\. You can start sending messages that use sender IDs immediately\. 

## Step 1: Open an Amazon Pinpoint SMS case<a name="channels-sms-awssupport-sender-id-open"></a>

If you plan to send messages to recipients a country where sender IDs are required, you can request a sender ID by creating a new case in the AWS Support Center\.

**Important**  
If you need to register a sender ID in India, complete the procedures in [Special requirements for India](channels-sms-senderid-india.md) *before* you open a case in Support Center\.
If you need to register a sender ID in Singapore, complete the procedures in [Special requirements for Singapore](channels-sms-senderid-singapore.md)\.

**To request a sender ID**

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
   + For **Resource Type**, choose** Sender ID Registration**\.
   + For **Limit**, choose the type of messages that you plan to send\.
   + For **New limit value**, enter the number of sender IDs that you're requesting\. Typically, this value is **1**\.

1. Under **Case description**, for **Use case description**, provide the following information:
   + The sender ID that you want to register\.
   + The template that you plan to use for your SMS messages\.
   + The number of messages that you plan to send to each recipient per month\.
   + Information about how your customers opt in to receiving messages from you\.
   + The name of your company or organization\.
   + The address that's associated with your company or organization\.
   + The country where your company or organization is based\.
   + A phone number for your company or organization\.
   + The URL of the website for your company or organization\.

1. \(Optional\) If you want to submit any further requests, choose **Add another request**\. For the required information, see the other sections within [Requesting support for SMS messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

1. Under **Contact options**, for **Preferred contact language**, choose whether you want to receive communications for this case in **English** or **Japanese**\.

1. When you finish, choose **Submit**\.

After we receive your request, we provide an initial response within 24 hours\. We might contact you to request additional information\.

If we're able to provide you with a Sender ID, we send you an estimate of the amount of time that's required to provision it\. In many countries, we can provide you with a Sender ID within 2–4 weeks\. However, in some countries, it can take several weeks to obtain a Sender ID\.

In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. We might not be able to grant your request if your use case doesn't align with our policies\.

## Step 2: Update your SMS settings in the Amazon Pinpoint console<a name="channels-sms-awssupport-sender-id-settings"></a>

When we complete the process of obtaining your sender ID, we respond to your case\. When you receive this notification, complete the steps in this section to configure Amazon Pinpoint to use your sender ID\.

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project that uses the SMS channel\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. Next to **SMS settings**, choose **Edit**\.

1. Under **Account\-level settings**, for **Default sender ID**, type your sender ID\.

1. Choose **Save changes**\.