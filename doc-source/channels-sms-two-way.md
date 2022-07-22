# Configuring two\-way SMS messaging in Amazon Pinpoint<a name="channels-sms-two-way"></a>

Amazon Pinpoint includes support for two\-way SMS\. When you set up two\-way SMS, you can receive incoming messages from your customers\. Amazon Pinpoint can automatically send responses to your customers when they send you certain keywords\. You can also use two\-way messaging together with other AWS services, such as Lambda and Amazon Lex, to create interactive text messaging experiences\.

Two\-way SMS is only available in certain countries and regions\. For more information about two\-way SMS support by country or region, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.

## Two\-way SMS use cases<a name="channels-sms-two-way-use-cases"></a>

Businesses in a wide variety of industries can use two\-way SMS to keep their customers informed and engaged\.

For example, medical practices can send messages to their patients asking them to confirm their appointments\. Patients can respond, indicating whether they're able to keep their appointments\. Patients who respond that they can't keep their appointments are sent a list of available times, and can reply to the message to reschedule\. This use case can be applied to several other types of businesses, such as restaurants or salons\.

Another use case is the verification of certain real\-world actions\. For example, banks or credit card providers can send a verification message when they notice unusual charges on a customer's account\. The customer can respond to the message authorizing the charge\. When the provider receives the authorization, they can allow the transaction to proceed\.

A third use case for two\-way SMS is interactive customer support, either with a live agent, or with a bot\. For example, the AWS Messaging and Targeting Blog describes [a solution that uses Lambda and Amazon Lex to create an SMS chatbot](http://aws.amazon.com/blogs//messaging-and-targeting/create-an-sms-chatbox-with-amazon-pinpoint-and-lex/)\.

## Configuring two\-way SMS in Amazon Pinpoint<a name="channels-sms-two-way-configure"></a>

You can set up two\-way SMS by using the Amazon Pinpoint console\. Complete the procedure in this section to set up two\-way SMS messaging for a phone number\.

### Prerequisites<a name="channels-sms-two-way-configure-prerequisite"></a>

Before you can enable and set up two\-way SMS in Amazon Pinpoint, you have to request a dedicated number\. The type of dedicated number you use depends on the country that your recipients are located in\. For more information about the types of dedicated numbers that are available in each country, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.

If you plan to use an Amazon SNS topic that's encrypted using an AWS KMS key, you have to modify the key policy\. For more information, see [Special requirements for encrypted topics](#channels-sms-two-way-configure-enable-encrypted-topic)\.

### Enabling two\-way SMS<a name="channels-sms-two-way-configure-procedure"></a>

You can enable two\-way SMS messaging for individual phone numbers\. When one of your customers sends a message to your phone number, the message body is sent to an Amazon SNS topic\. The procedure for setting up two\-way messaging depends on whether you want to use a standard Amazon SNS topic or an encrypted one\. This section contains procedures for both scenarios\. You only need to complete one of these procedures\.

**To enable two\-way SMS**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. Under **Number settings**, choose the phone number that you want to configure two\-way SMS for\.
**Note**  
You can only enable two\-way SMS for a phone number if the value in the **SMS** column is *Enabled*\.

1. In the **Two\-way SMS** section, choose **Enable 2\-way SMS**\.

1. Under **Incoming messages destination**, specify the Amazon SNS topic that receives your SMS messages by choosing one of the following options:
   + **Create a new Amazon SNS topic** – If you choose this option, Amazon Pinpoint creates a topic in your account\. The topic is automatically created with all of the required permissions\.
   + **Choose an existing Amazon SNS topic** – If you choose this option, you must choose an existing Amazon SNS topic\. The access policy for the topic that you choose must include the following permission:

     ```
     {
       "Effect": "Allow",
       "Principal": {
         "Service": "sms-voice.amazonaws.com"
       },
       "Action": "sns:Publish",
       "Resource": "*"
     }
     ```
**Note**  
Amazon SNS FIFO topics are not supported\. If you choose a topic that is encrypted using an AWS KMS key, see [Special requirements for encrypted topics](#channels-sms-two-way-configure-enable-encrypted-topic) for additional requirements\.

1. \(Optional\) Under **Two\-way SMS keywords**, add keywords and response messages\. When your number receives an SMS message that contains one of these keywords, Amazon Pinpoint sends the message to your Amazon SNS topic, and replies with the response message that you specified\. Choose **Add another keyword** to add additional keywords\.

1. When you finish making changes, choose **Save**\.

### Special requirements for encrypted topics<a name="channels-sms-two-way-configure-enable-encrypted-topic"></a>

Although Amazon Pinpoint data is encrypted, you can use Amazon SNS topics that are encrypted using AWS KMS keys for an additional level of security\. This added security can be helpful if your application handles private or sensitive data\.

You need to perform some additional setup steps to use encrypted Amazon SNS topics with two\-way messaging\.

First, the key that you use must be *symmetric*\. Encrypted Amazon SNS topics don't support asymmetric AWS KMS keys\.

Second, the key policy must be modified to allow Amazon Pinpoint to use the key\. Add the following permissions to the existing key policy:

```
{
    "Effect": "Allow",
    "Principal": {
        "Service": "sms-voice.amazonaws.com"
    },
    "Action": [
        "kms:GenerateDataKey*",
        "kms:Decrypt"
    ],
    "Resource": "*"
}
```

For more information about editing key policies, see [Changing a key policy](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-modifying.html) in the *AWS Key Management Service Developer Guide*\.

For more information about encrypting Amazon SNS topics using AWS KMS keys, see [Enable compatibility between event sources from AWS services and encrypted topics](https://docs.aws.amazon.com/sns/latest/dg/sns-key-management.html#compatibility-with-aws-services) in the *Amazon Simple Notification Service Developer Guide*\.

## Example of a two\-way SMS message payload<a name="settings-account-sms-two-way-payload"></a>

When your number receives an SMS message, Amazon Pinpoint sends a JSON payload to an Amazon SNS topic that you designate\. The JSON payload contains the message and related data, as in the following example:

```
{
  "originationNumber":"+14255550182",
  "destinationNumber":"+12125550101",
  "messageKeyword":"JOIN",
  "messageBody":"EXAMPLE",
  "inboundMessageId":"cae173d2-66b9-564c-8309-21f858e9fb84",
  "previousPublishedMessageId":"wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY"
}
```

The incoming message payload contains the following information:


****  

| Property | Description | 
| --- | --- | 
| `originationNumber` | The phone number that sent the incoming message to you \(in other words, your customer's phone number\)\. | 
| `destinationNumber` | The phone number that the customer sent the message to \(your dedicated phone number\)\. | 
| `messageKeyword` | The registered keyword that's associated with your dedicated phone number\. | 
| `messageBody` | The message that the customer sent to you\. | 
| `inboundMessageId` | The unique identifier for the incoming message\. | 
| `previousPublishedMessageId` | The unique identifier of the message that the customer is responding to\. | 