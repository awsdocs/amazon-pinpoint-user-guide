# Setting up the Amazon Pinpoint SMS Channel<a name="channels-sms-setup"></a>

To send SMS messages with Amazon Pinpoint, you need an Amazon Pinpoint project in which the SMS channel is enabled\.

You can also enable the SMS channel for an existing project by using the **SMS and voice** settings page on the Amazon Pinpoint console\. For more information, see [Managing the Amazon Pinpoint SMS Channel](channels-sms-manage.md)\.

## Creating a New Project by Using the Amazon Pinpoint Console<a name="channels-sms-setup-mobilehub"></a>

The first step in setting up email in Amazon Pinpoint is to create a new project\. Next, you verify an email address identity\.

In Amazon Pinpoint, an *identity* is an email address or domain that you use to send email\. Before you can send email using Amazon Pinpoint, you must verify each identity that you plan to use as a "From", "Source", "Sender", or "Return\-Path" address to prove that you own it\. If your account is still in the Amazon Pinpoint sandbox, you also need to verify the identities that you plan to send emails to\.

**To create a new Amazon Pinpoint project and verify an email address**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose **Create a project**\.

1. For **Project name**, enter a name, and then choose **Create**\.
**Note**  
The project name can contain up to 64 alphanumeric characters\. It can also include the following characters: comma \(,\), period \(\.\), at sign \(@\), underscore \(\_\), equals sign \(=\), and plus sign \(\+\)\.

1. Under **Project features**, in the **SMS and voice** section, choose **Configure**\.

1. Choose **Enable the SMS channel for this project**\.

1. Under **Account\-level settings**, you can optionally change the following settings:
   + **Default message type** – The category of messages that you plan to send\. Choose **Transactional** for time\-sensitive content, such as alerts and one\-time passwords, or choose **Promotional** for marketing\-related content\.
   + **Account spending limit** – The maximum amount of money, in US Dollars, that you want to spend sending SMS messages per calendar month\. If your monthly spending exceeds this limit, Amazon Pinpoint and other AWS services stop sending SMS messages from your account\.
   + **Default sender ID** – The identity that appears on recipients' devices when they receive messages\. Support for sender ID capabilities varies by country or region\.
**Important**  
These settings apply to your entire AWS account\. When you change these settings, they apply to all other Amazon Pinpoint projects in your account, and to other AWS services that you use to send SMS messages, such as Amazon SNS\.

1. When you finish, choose **Save changes**\.

## Next Steps<a name="channels-sms-setup-next"></a>

You've created a project that's enabled for SMS messaging\. Now you can use Amazon Pinpoint to send SMS messages\. 

Some SMS options, such as dedicated origination numbers or sender IDs, are unavailable until you contact AWS Support\. For more information, see [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

To engage an audience segment with an SMS campaign, see [Amazon Pinpoint Campaigns](campaigns.md)\.

To send an SMS message directly to a limited audience without creating a campaign, see [Send Test Messages with Amazon Pinpoint](messages.md)\.