# Using Two\-Way SMS Messaging in Amazon Pinpoint<a name="channels-sms-two-way"></a>

Amazon Pinpoint includes support for *two\-way SMS*, which allows you to receive messages from your customers\. You can configure Amazon Pinpoint to automatically send responses to your customers based on the content of the messages they send you\.

**Note**  
Two\-way SMS is only available in certain countries and regions\. For more information about two\-way SMS support by country or region, see [Supported Countries and Regions](channels-sms-countries.md)\.

## Two\-Way SMS Use Cases<a name="channels-sms-two-way-use-cases"></a>

Businesses in a wide variety of industries can use two\-way SMS to keep their customers informed and engaged\.

For example, medical practices can send messages to their patients asking them to confirm their appointments\. Patients can respond, indicating whether they're able to keep their appointments\. Patients who respond that they can't keep their appointments are sent a list of available times, and can reply to the message to reschedule\. This use case can be applied to several other types of businesses, such as restaurants or salons\.

Another use case for two\-way SMS is the verification of certain real\-world actions\. For example, banks or credit card providers can send a verification message when they notice unusual charges on a customer's account\. The customer can respond to the message authorizing the charge\. When the provider receives the authorization, they can allow the transaction to proceed\.

## Configuring Two\-Way SMS in Amazon Pinpoint<a name="channels-sms-two-way-configure"></a>

You can set up two\-way SMS by using the Amazon Pinpoint console\. Complete the procedures in this section to enable and set up two\-way SMS messaging for your account\.

### Prerequisite<a name="channels-sms-two-way-configure-prerequisite"></a>

Before you can enable and set up two\-way SMS in Amazon Pinpoint, you have to request a dedicated number\. If you're testing your two\-way SMS program, you can request a long code\. However, the laws and regulations of some countries and regions might require you to use a short code when you send messages to your customers and receive messages from them\. 

For more information about requesting numbers, including dedicated short codes and long codes, see [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

### Setting Up Two\-Way SMS<a name="channels-sms-two-way-configure-enable"></a>

After you receive a dedicated number from AWS Support, you can enable and configure two\-way SMS\.

**To set up two\-way SMS**

1. On the **All projects** page, choose the project that you want to manage two\-way SMS settings for\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. Under **Number settings**, choose the phone number that you want to configure two\-way SMS for\.
**Note**  
You can enable two\-way SMS for a phone number only if the value in the **SMS** column is *Enabled*\.

1. Under **Two\-way SMS**, choose **Enable 2\-way SMS**\.

1. Under **Incoming messages destination**, specify the Amazon SNS topic that receives your SMS messages by choosing one of the following options:
   + **Create a new Amazon SNS topic** – Amazon Pinpoint creates a topic in your account\.
   + **Choose an existing Amazon SNS topic** – Specify the ARN of a topic in your account\.

1. Under **Two\-way SMS keywords**, you can add or edit keywords and response messages\. When your number receives an SMS message that contains one of these keywords, Amazon Pinpoint does the following:
   + Sends the message to your Amazon SNS topic\.
   + Responds with the keyword response message, if you specified one\.

   To add a keyword, choose **Add another keyword**\.

1. When you finish making changes, choose **Save**\.

## Example of a Two\-Way SMS Message Payload<a name="settings-account-sms-two-way-payload"></a>

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

The value for `originationNumber` is the number that the message was sent from \(that is, your customer's number\)\. The value for `destinationNumber` is the number that the message was sent to \(your short code or long code\)\.