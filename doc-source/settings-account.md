# Managing Account Settings in Amazon Pinpoint<a name="settings-account"></a>

Use the **Account settings** page in the Amazon Pinpoint console to manage account\-level SMS settings that take effect for all of your Amazon Pinpoint projects\. The settings include SMS spending limits, your default sender ID, automated keyword responses, and two\-way SMS options\.

Many of the SMS settings on this page are unavailable until you contact AWS Support\. For example, you must submit a case with AWS Support if you want to increase your spend limit, reserve a dedicated origination number, or reserve a custom sender ID\. For more information, see [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

Because these settings apply to your AWS account, some settings also take effect for Amazon SNS, an AWS service that you can also use to send SMS messages\.

To manage your account settings, sign in to the AWS Management Console, and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\. Then, on the **Projects** page, choose **Account settings**\.

Under **SMS**, configure your general SMS settings, and configure the number settings for your short codes and long codes\.

## General SMS Settings<a name="settings-account-sms-general"></a>

Specify your general SMS preferences, such as your default message type and your monthly spending limit\.

**To configure general SMS settings**

1. Under **General**, for **Default message type**, select the type of SMS message that you will usually send:

   + **Promotional** – Noncritical messages, such as marketing messages\. Amazon Pinpoint optimizes the message delivery for lowest cost\.

   + **Transactional** – Critical messages that support customer transactions, such as one\-time passcodes for multi\-factor authentication\. Amazon Pinpoint optimizes the message delivery for highest reliability\.

   You can override this setting when you send a message\.

   For pricing information for promotional and transactional messages, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/#Messages_sent)\.

1. For **Account spending limit**, type the maximum amount, in USD, that you want to spend on SMS messages each calendar month\. When Amazon Pinpoint determines that sending an SMS message would incur a cost that exceeds your spend limit for that month, Amazon Pinpoint stops publishing SMS messages within minutes\.
**Important**  
Because Amazon Pinpoint is a distributed system, it stops sending SMS messages within a time interval of minutes of the spend limit being exceeded\. During that interval, if you continue to send SMS messages, you might incur costs that exceed your limit\.

   By default, the spend limit is 1\.00 USD\. To request a limit increase, see [Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

1. For **Default sender ID**, type a custom ID that contains up to 11 alphanumeric characters, including at least one letter and no spaces\. The sender ID is displayed as the message sender on the receiving device\. For example, you can use your business brand to make the message source easier to recognize\.

   Support for sender IDs varies by country and/or region\. For more information, see [Supported Countries and Regions](channels-sms-countries.md)\.

   To request a dedicated sender ID, see [Requesting Sender IDs for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport-sender-id.md)\.

   You can override this setting when you send a message\.

1. Choose **Save**\.

## Number Settings<a name="settings-account-sms-number"></a>

Manage settings for the dedicated *short codes* and *long codes* that you have requested from AWS Support and that are assigned to your account\.

A short code is a 5 or 6 digit number that is meant for high\-volume SMS messaging\. To request a dedicated short code, see [Requesting Dedicated Short Codes for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.

A long code is a standard 10 digit phone number that is meant for low\-volume, person\-to\-person communication\. To request a dedicated long code, see [Requesting Dedicated Long Codes for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\.

After you receive one or more dedicated short codes or long codes from AWS, those numbers are provided under **Number settings**, where you can manage settings for keywords and two\-way SMS\.

### Keyword Settings<a name="settings-account-sms-number-keyword"></a>

A *keyword* is a specific word or phrase that your audience can text to your number to elicit a response, such as an informational message or a special offer\. When your number receives a message that begins with a keyword, Amazon Pinpoint responds with a customizable message\.

For short codes, the console shows the keywords and responses that you initially define when you request a short code from AWS Support\. AWS Support registers your keywords and responses with the wireless carriers when provisioning your short code\.

For long codes, the console shows the default keywords and responses\.

**Important**  
Your keywords and response messages must comply with guidelines set by wireless carriers and wireless industry groups\. Otherwise, following an audit, such groups might take action against your short code or long code\. This action can include blacklisting your number and blocking your messages\.

#### Default Keywords<a name="settings-account-sms-number-keyword-default"></a>

The following keywords are required by wireless carriers in the US for short codes, and they are expected by AWS for all long codes and short codes:

HELP  
Used to obtain customer support\. The response message must include customer support contact information, as in the following example:  
*"For assistance with your account, call 1 \(NNN\) 555\-0199"*

STOP  
Used to opt out of receiving messages from your number\. In addition to STOP, your audience can use any supported opt\-out keyword, such as CANCEL or OPTOUT\. For all opt\-out keywords, see [SMS Opt Out](channels-sms-manage.md#channels-sms-manage-optout)\. After your number receives an opt\-out keyword, Amazon Pinpoint stops sending SMS messages from your account to the individual who opted out\.  
The response message must confirm that messages are no longer sent to the individual who opted out, as in the following example:  
*"You are now opted out and will no longer receive messages\."*

#### Registered Keyword<a name="settings-account-sms-number-keyword-registered"></a>

A required custom keyword that is specific to your SMS use case\. For example, your audience might text the keyword DISCOUNT to your short code, and the response message could include a promotional code\.

#### Managing Keyword Settings<a name="settings-account-sms-number-keyword-managing"></a>

Use the Amazon Pinpoint console to customize the keyword responses for your number\.

1. On the **Account settings** page, under **Number settings**, choose the short code or long code for which you want to manage keyword responses\.

   The **Number settings** page displays\. Under **Keywords**, the console provides:

   + The default keywords HELP and STOP\. You can edit the response messages, but you cannot edit the keywords\.

   + Your registered keyword\. If you want to change your registered keyword, you must first open a case with AWS Support and request to update your keyword with the wireless carriers\. Then, you must edit the keyword in the Amazon Pinpoint console to match\. You can also edit the response message, but the intent of the message must remain consistent with the message that you provide to AWS Support\.

1. In the table that contains the keyword you want to edit, choose **Edit**, and edit the keyword and response message as needed\.

1. When you finish making your changes, choose **Save**\.

### Two\-Way SMS Settings<a name="settings-account-sms-number-2way"></a>

Define keywords for messages that you want to receive and process outside of Amazon Pinpoint\. When your number receives an SMS message that begins with one of these keywords, Amazon Pinpoint sends the message and related data to an Amazon SNS topic in your account\. You can use Amazon SNS to publish the message to topic subscribers or to AWS services for further processing\.

**To manage two\-way SMS settings**

1. On the **Account settings** page, under **Number settings**, choose the short code or long code for which you want to manage two\-way SMS settings\.

1. If you haven't already, choose **Enable 2\-way SMS**\.

1. Under **Keywords**, you can add or edit keywords and response messages\. When your number receives an SMS message that begins with one of these keywords, Amazon Pinpoint does the following:

   + Sends the message to your Amazon SNS topic\.

   + Responds with the keyword response message, if specified\.

1. Under **Amazon SNS topic**, specify the topic that receives your SMS messages with one of the following options:

   + **Automatically create a topic** – Amazon Pinpoint creates a topic in your account\. 

   + **Choose a topic from your account** – Specify the ARN of a topic in your account\.

1. Choose **Save**\.

   If you created an Amazon SNS topic, you can see the topic by going to the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v2/home](https://console.aws.amazon.com/sns/v2/home)\.

## Example Two\-Way SMS Message Payload<a name="settings-account-sms-2way-payload"></a>

When your number receives an SMS message that begins with a keyword that you define for two\-way SMS, Amazon Pinpoint sends a JSON payload to an Amazon SNS topic that you designate\. The JSON payload contains the message and related data, as in the following example:

```
{
  "originationNumber": "+1XXX5550100",
  "messageBody": "offers",
  "inboundMessageId": "cae173d2-66b9-564c-8309-21f858e9fb84",
  "messageKeyword": "offers",
  "destinationNumber": "+1XXX5550199"
}
```

The value for `originationNumber` is the number from which the message was sent \(your customer's number\)\. The value for `destinationNumber` is the number to which the message was sent \(your short code or long code\)\.