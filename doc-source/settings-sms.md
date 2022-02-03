# SMS and voice settings<a name="settings-sms"></a>

Use the **SMS and voice** settings page to enable or disable the SMS channel for the current project\. You can also use this page to do the following:
+ Manage the default settings that apply to all SMS messages that you send from your AWS account\. These settings also apply to messages that you send using other AWS services such as Amazon SNS\.
+ View a list of the phone numbers that you can use to send SMS and voice messages\.
+ Request a long code, toll\-free number, or 10DLC phone number\.

## Number purchase types<a name="number-purchase-types"></a>

On the **SMS and voice** settings page, you can request the following types of numbers:
+ **10DLC** \(US only\) – A type of long code that's registered with mobile carriers specifically to support high\-volume Application\-to\-Person \(A2P\) SMS messaging using 10\-digit phone numbers\. To use 10DLC, you must first register your company and use case\. After you complete these registrations, you can associate phone numbers with your 10DLC campaign\. For more information about setting up 10DLC, see [10DLC](settings-sms-10dlc.md)\.
+ **Toll\-free** \(US only\) – A 10\-digit number that begins with one of the following prefixes: 800, 888, 877, 866, 855, 844, or 833\. Toll\-free numbers should only be used to send transactional messages, such as registration confirmation or one\-time passwords\. They can support up to three message parts per second\. Opt\-in and opt\-out messages are managed downstream from AWS\. For this reason, you can't change the messages that are shown when your recipients opt in to or out of receiving your messages\.
+ **Long code** – Phone numbers that use the number format of the country or region where your recipients are located\. For example, in the US and Canada, long codes contain 11 digits: the number 1 \(the country code\), a three\-digit area code, and a seven\-digit phone number\. You can purchase long codes for use with the voice channel on the **SMS and voice** settings page\.
+ **Short code **– A short phone number \(typically 5–6 digits\) for sending SMS messages\. Short codes typically support very high throughput rates\. For example, in the US and Canada, short codes support 100 message parts per second by default, and can support much higher rates for an additional charge\. These capabilities vary by country or region\. It typically takes several weeks to obtain a short code\. To obtain a short code, you must create an AWS Support case\. For more information about requesting a short code, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.

## US phone number capabilities<a name="10dlc-product-comparison"></a>

Amazon Pinpoint supports more types of phone numbers in the United States than in other countries\. The following table compares the capabilities of the types of phone numbers that you can use to send messages to recipients in the United States\.

**Note**  
Short codes and long codes are available in countries and regions other than the United States\. The capabilities of these number types vary by country\. For more information about requesting short codes, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md); for more information about requesting long codes, see [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\.  
Toll\-free and 10DLC phone numbers are only available in the United States\.


****  

| Number type | Number format | Channel support | Requires registration | Provisioning time | SMS throughput | 
| --- | --- | --- | --- | --- | --- | 
| Short code | 5–6 digits | SMS only | Yes | At least 10 weeks | 100 message parts per second by default | 
| Toll\-free | 10 digits | SMS, voice | No | Available immediately | 3 message parts per second | 
| 10DLC | 10 digits | SMS, voice | Yes | About 1 week | Varies based on company and campaign details | 
| Unregistered long code | 10 digits | Voice only | No | Available immediately | Not applicable—can be used for voice only | 

## SMS and voice sandboxes<a name="settings-sandbox"></a>

New accounts that use the Amazon Pinpoint SMS and voice messaging channels are placed in sandbox environments\. While your account is in the sandbox, you can access all of the message sending features of Amazon Pinpoint, but with restrictions\. You can request production access to remove these restrictions\. For more information, see [About the Amazon Pinpoint SMS sandbox](channels-sms-sandbox.md) and [Amazon Pinpoint voice sandbox](channels-voice-sandbox.md)\.