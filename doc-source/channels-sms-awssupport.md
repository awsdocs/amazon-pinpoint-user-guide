# Requesting support for SMS messaging with Amazon Pinpoint<a name="channels-sms-awssupport"></a>

Certain SMS options with Amazon Pinpoint are unavailable until you contact AWS Support\. Open a case in the [AWS Support Center](https://console.aws.amazon.com/support/home#/) to request any of the following:
+ 

**An increase to your monthly SMS spending threshold**  
By default, the monthly spending threshold is $1\.00 \(USD\)\. Your spending threshold determines the volume of messages that you can send with Amazon Pinpoint\. Request a spending threshold that meets the expected monthly message volume for your SMS use case\.
+ 

**A dedicated short code**  
Your dedicated origination number is assigned to your AWS account, and it's available exclusively to you\. If you don't have a dedicated number, Amazon Pinpoint assigns a number to your messages\. This number is shared with other Amazon Pinpoint users, and it varies based upon destination and message type \(transactional or promotional\)\. By reserving a short code, you can send your messages with a persistent origination number\. This makes it easier for your audience to recognize that your organization is the source of your messages\. A dedicated short code is required if you want to enable two\-way SMS with Amazon Pinpoint\. 
+ 

**A dedicated sender ID**  
A *sender ID* is a custom ID that is shown as the sender on the recipient's device\. For example, you can use your business brand to make the message source easier to recognize\. Support for sender IDs varies by country or region\. For more information, see [Supported countries and regions \(SMS channel\)](channels-sms-countries.md)\.

When you create your case in the AWS Support Center, include all the information that's required for the type of request you're submitting\. Otherwise, AWS Support contacts you to obtain this information before proceeding\. By submitting a detailed case, you help ensure that your case is fulfilled without delays\. For the details that are required for specific types of SMS requests, see the following topics\.

The following number type doesn't require you to contact AWS Support\. You can request this type of number directly through the Amazon Pinpoint console\.
+ 

**A long code or 10DLC**  
A *long code* is a phone number up to 12 digits used for SMS and voice messaging\. that is shown as the sender on the recipient's device\. *10DLC* is a 10\-digit number used only in the U\.S\. for SMS and voice\. Before requesting a 10DLC however, you'll need to register your company and messaging campaign\. 

  Both number types can be requested through the Console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\. For more information, see [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\. 

  10DLC throughput supports up to 100 message parts per second, although the exact throughput you get is determined by a combination of The Campaign Registry and your carrier\. Amazon Pinpoint has no control over what throughput you will receive\.