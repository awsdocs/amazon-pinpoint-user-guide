# Understanding SMS billing and usage reports for Amazon Pinpoint<a name="channel-sms-monitoring-bill"></a>

The [Amazon Pinpoint SMS channel](channels-sms.md) generates a usage type that contains five fields in the following format: `Region code–MessagingType–ISO–RouteType–OriginationID–MessageCount/Fee`\. For example, SMS messages sent from the Asia Pacific \(Tokyo\) Region to Canada would appear as **APN1–OutboundSMS–CA–Standard–Senderid–MessageCount**\.

The following table displays the possible values and descriptions for the fields in the usage type\. For more information about SMS pricing, see [Amazon Pinpoint Pricing](http://aws.amazon.com/pinpoint/pricing/)\.


****  

| Field | Options | Description | 
| --- | --- | --- | 
| Region code |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/channel-sms-monitoring-bill.html) |  The AWS Region prefix that indicates where the SMS message was sent from\.  | 
| MessagingType | OutboundSMS | This field lists the message type being sent\. For Outbound SMS, it reads OutboundSMS\. | 
| ISO | See [Supported countries and regions \(SMS channel\)](channels-sms-countries.md) for the list of ISO country codes supported by Amazon Pinpoint\. | The two–digit ISO country code that the message was sent to\. | 
| RouteType | Standard | The route type that the message was sent through\. Currently, all messages are sent through the Standard route type\. | 
| OrginationID | TollFree, 10DLC, Shortcode, Longcode, Senderid, Sharedroute | This field specifies the origination identity that was used to send the message\. See [Originating identities for SMS messages](channels-sms-originating-identities.md) for more information about supported origination identities\. | 
| MessageCount/Fee | MessageCount, MessageFees, CarrierFeeCount, CarrierFees | This field displays either the number of messages sent or the cost associated with sending those messages\. [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/channel-sms-monitoring-bill.html)  | 

Messages sent through Amazon Pinpoint for Outbound SMS generate 2 – 4 usage types per combination of ISO country and origination identity\. View the following examples to better understand how the usage types appear on your bill\.

## Example 1: Sending messages to the United Kingdom<a name="channel-sms-monitoring-bill-example1"></a>

Suppose you sent 10 messages to the United Kingdom \(ISO code GB\) using a short code from USE1\. Then you can expect the following two usage types in your bill:

```
  1. USE1-OutboundSMS-GB-Standard-Shortcode-MessageCount
  2. USE1-OutboundSMS-GB-Standard-Shortcode-MessageFee
```

## Example 2: Sending messages to the United States<a name="channel-sms-monitoring-bill-example2"></a>

Suppose you sent 10 messages to the United States \(ISO code US\) using a 10DLC number from CAN1\. Then you can expect the following four usage types in your bill:

```
  1. CAN1-OutboundSMS-US-Standard-10DLC-MessageCount
  2. CAN1-OutboundSMS-US-Standard-10DLC-MessageFee
  3. CAN1-OutboundSMS-US-Standard-10DLC-CarrierFeeCount
  4. CAN1-OutboundSMS-US-Standard-10DLC-CarrierFees
```