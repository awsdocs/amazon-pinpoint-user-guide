# Choosing the right type of origination identity for your use case<a name="channels-sms-originating-identities-choosing"></a>

An *origination identity* is the name or phone number that your recipients see on their devices when you send them an SMS message\. There are several types of origination identities, including long codes \(standard phone numbers that typically have 10 or more digits\), short codes \(phone numbers that contain between four and seven digits\), and Sender IDs \(names that contain 6–11 alphanumeric characters\)\. Each of these types of origination identities has unique benefits and drawbacks\. This section is intended to help you identify the right type of origination identity for your use case\.

**Topics**
+ [General considerations](#channels-sms-originating-identities-choosing-general)
+ [Choosing an origination identity for one\-way messaging use cases](#channels-sms-originating-identities-choosing-oneway)
+ [Choosing an origination identity for two\-way messaging use cases](#channels-sms-originating-identities-choosing-twoway)

## General considerations<a name="channels-sms-originating-identities-choosing-general"></a>

There are several guidelines to consider when you're deciding what type of origination identity to use:
+ Sender IDs are a great option for one\-way use cases\. However, they're not available in all countries\.
+ Short codes are a great option for two\-way use cases\. If you have to choose between using a short code or a long code, you should choose the short code\.
+ In some countries \(such as India and Saudi Arabia\), long codes can be used to receive incoming messages, but can't be used to send outgoing messages\. You can use these inbound\-only long codes to provide your recipients with a way to opt out of messages that you send using a Sender ID\.
+ In some countries, we maintain a pool of shared origination identities\. If you send messages to recipients in a particular country, but you don't have a dedicated origination identity in that country, we make an effort to deliver your message using one of these shared identities\. Shared identities are unavailable in some countries, including the United States and China\.
+ The mobile industry changes rapidly\. In many countries, there is a trend toward increased regulation of commercial SMS messages\. Carriers may, with little or no warning, decide to disallow messages sent from shared origination identities\. If this happens, we will attempt to tell you about these changes with as much advance warning as possible\. However, carriers generally provide us with little advance notice of these changes\. For these reasons, dedicated origination identities are always preferred to shared ones\.

## Choosing an origination identity for one\-way messaging use cases<a name="channels-sms-originating-identities-choosing-oneway"></a>

A *one\-way messaging* use case is a use case that only involves sending outgoing SMS messages to your recipients\. This section provides information about choosing the right type of origination identity for your one\-way messaging use case\. If your use case requires two\-way messaging—that is, the ability to both send outgoing messages and receive incoming messages—answer the questions in [Choosing an origination identity for two\-way messaging use cases](#channels-sms-originating-identities-choosing-twoway) instead\.

One\-way messaging use cases can use short codes, long codes, toll\-free numbers, or alphanumeric Sender IDs as their origination identity\. The right kind of origination identity to use depends on your specific needs, and on the countries that your recipients are located in\.

Answer the following questions to determine the right type of origination identity for your needs\. If you have recipients in multiple countries, answer these questions for each country that your recipients are located in\.

1. Are you planning to send messages to recipients in the United States?
   + If you answered **Yes**, proceed to [question 2](#one-way-q2)\. 
   + If you answered **No**, proceed to [question 3](#one-way-q3)\.

1. Which of the following throughput rates best fits your use case? Your throughput rate is the number of message parts that you can send each second\.
   + **1–3 message parts per second**: Use a toll\-free number\. You can also use 10DLC numbers or short codes\. These number types provide plenty of room for growth, but also cost more and take longer to obtain than a toll\-free number\.

     For more information about requesting a toll\-free number, see [Requesting a number](settings-sms-request-number.md)\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.
   + **10–75 message parts per second**: Use a 10DLC number\. You can also use a short code, which would provide additional room for growth, but would also cost more\.

     For more information about setting up 10DLC, see [10DLC](settings-sms-10dlc.md)\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.
   + **100 message parts per second or more**: Use a short code\. When you create your request in the AWS Support Center Console, specify the throughput rate that you want your short code to support\. US short codes support 100 message parts per second by default, but the throughput rate can be increased beyond that rate for an additional monthly fee\.

     For more information about requesting a short code, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.

1. Is it important for all of your messages to come from the same origination identity?
   + If you answered **Yes**, proceed to [question 4](#one-way-q4)\.
   + If you answered **No**, proceed to [question 6](#one-way-q6)\.

1. Are Sender IDs supported in the country that you plan to send messages to? For a list of countries that support Sender IDs, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.
   + If you answered **Yes**, proceed to [question 5](#one-way-q5)\.
   + If you answered **No**, proceed to [question 7](#one-way-q7)\.

1. Does the country that you plan to send messages to require pre\-registration of Sender IDs? For a list of countries that require Sender ID registration, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.
   + If you answered **Yes**, complete the Sender ID process for the destination country\. When the registration process is complete, you can use your Sender ID to send messages\. 

     If you want to determine what kind of origination identity to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.
   + If you answered **No**, you can specify your Sender ID when you send your messages\. 

     If you want to determine what kind of origination identity to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.

1. Are you planning to send messages to recipients in India?
   + If you answered **Yes**, you can start sending immediately\. However, the messages that you send are charged at the International Long\-Distance Operator \(ILDO\) rate, which costs several times more than messages sent using a registered Sender ID\. If costs are an important factor, you should consider [registering your company and use case in India](channels-sms-senderid-india.md)\. When you complete this registration process, you can send messages at the less\-expensive local rate\.

     If you want to determine what kind of origination identity to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.
   + If you answered **No**, you can start sending without obtaining an origination identity\. Your messages are sent using an origination identity that is shared with other Amazon Pinpoint users\. The capabilities of the mobile networks in the destination country determine what identity is shown to recipients when they receive a message from you\. In countries that support unregistered Sender IDs, your messages are sent using a generic Sender ID \(such as "NOTICE"\)\. In countries that don't support Sender IDs, your messages are sent from a random long code or short code\.

     If you want to determine what kind of origination identity to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.

1. Are dedicated short codes available in the country that you plan to send messages to? For a list of countries that support dedicated short codes, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.
   + If you answered **Yes**, you should use a **short code**\.
   + If you answered **No**, proceed to [question 8](#one-way-q8)\.

1. Are dedicated long codes available in the country that you plan to send messages to? For a list of countries that support dedicated long codes, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.
   + If you answered **Yes**, you can use a dedicated long code\. However, if any other type of dedicated identity is available in that country \(such as Sender IDs or short codes\), you should use the other identity type instead\. Carriers are more likely to block messages that are sent using long codes if other origination identity types are also available\.

     For more information about requesting dedicated SMS long codes, see [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\.

     If you want to determine what kind of origination identity to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.
   + If you answered **No**, you can start sending without obtaining an origination ID\. Your messages are sent using an origination identity that is shared with other Amazon Pinpoint users\. The capabilities of the mobile networks in the destination country determine what identity is shown to recipients when they receive a message from you\. In countries that support unregistered Sender IDs, your messages are sent using a generic Sender ID \(such as "NOTICE"\)\. In countries that don't support Sender IDs, your messages are sent from a random long code or short code\. 

     If you want to determine what kind of origination identity to use for another country, return to [question 1](#one-way-q1)\. Otherwise, **stop here**\.

## Choosing an origination identity for two\-way messaging use cases<a name="channels-sms-originating-identities-choosing-twoway"></a>

A *two\-way messaging* use case is a use case that involves both sending outgoing SMS messages to your customers and receiving incoming SMS messages from them\. This section provides information about choosing the right type of origination identity for your two\-way messaging use case\. If your use case requires one\-way messaging—that is, only the ability to send outgoing messages—answer the questions in [Choosing an origination identity for one\-way messaging use cases](#channels-sms-originating-identities-choosing-oneway) instead\.

If you plan to receive incoming SMS messages, you must have a dedicated phone number\. There are different types of dedicated phone numbers depending on the country where your customers are located\.

Answer the following questions to determine the right type of origination identity for your needs\. If you have recipients in multiple countries, answer these questions for each country that your recipients are located in\.

1. Is two\-way messaging supported in the country that you plan to send messages to? For a full list of countries that support two\-way messaging, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.
   + If you answered **Yes**, proceed to [question 2](#two-way-q2)\.
   + If you answered **No**, your two\-way messaging use case isn't supported, but you can still send one\-way messages\. To find an origination ID for sending one\-way messages, see [Choosing an origination identity for one\-way messaging use cases](#channels-sms-originating-identities-choosing-oneway)\.

1. Are you planning to send messages to recipients in the United States?
   + If you answered **Yes**, proceed to [question 3](#two-way-q3)\.
   + If you answered **No**, proceed to [question 4](#two-way-q3)\.

1. Which of the following throughput rates best fits your requirements? Your throughput rate is the number of message parts that you can send each second\.
   + **1–3 message parts per second**: Use a toll\-free number\. You can also use 10DLC numbers or short codes\. These number types will provide plenty of room for growth, but will also cost more and take longer to obtain\.

     For more information about requesting a toll\-free number, see [Requesting a number](settings-sms-request-number.md)\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#two-way-q1)\. Otherwise, **stop here**\.
   + **10–75 message parts per second**: Use a 10DLC number\. A short code will also work for your use case, and will provide additional room for growth, but it will also cost more\.

     For more information about setting up 10DLC, see [10DLC](settings-sms-10dlc.md)\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#two-way-q1)\. Otherwise, **stop here**\.
   + **100 message parts per second or more**: Use a short code\. When you create your request in the AWS Support Center Console, specify the throughput rate that you want your short code to support\. US short codes support 100 message parts per second by default, but the throughput rate can be increased beyond that rate for an additional monthly fee\.

     For more information about requesting a short code, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#two-way-q1)\. Otherwise, **stop here**\.

1. Are dedicated short codes available in the country that you plan to send messages to? For a list of countries where short codes are available, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.
   + If you answered **Yes**, use a dedicated short code\. For more information about requesting a short code, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#two-way-q1)\. Otherwise, **stop here**\.
   + If you answered **No**, use a dedicated long code\. For more information about requesting dedicated SMS long codes, see [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\.
**Note**  
If both dedicated short codes and dedicated long codes are available in the destination country, you should use a dedicated short code\. Mobile carriers are more likely to block or limit the messages that are sent from long codes if short codes are also available\.

     If you want to determine what kind of origination number to use for another country, return to [question 1](#two-way-q1)\. Otherwise, **stop here**\.