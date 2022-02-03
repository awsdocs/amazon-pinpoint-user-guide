# Message Parts per Second \(MPS\) limits<a name="channels-sms-limitations-mps"></a>

SMS messages are delivered in 140\-byte sections known as *message parts*\. Messages that are very long, or that contain many multi\-byte characters, are split into several message parts\. These messages are usually re\-assembled on the recipient's device, appearing as a single long message rather than several small ones\. For more information about SMS character limits, see [SMS character limits in Amazon Pinpoint](channels-sms-limitations-characters.md)\.

For this reason, SMS throughput limits are measured in *Message Parts per Second* \(MPS\)—that is, the maximum number of message parts that you can send in a second\. Your MPS limit depends on the destination country of your messages, as well as the type of phone number \(*origination number*\) that you use to send the message\. For example, if you use a United States short code to send messages to recipients in the US, you can send 100 MPS\. However, if you use a US toll\-free number to send to US recipients, you can only send 3 MPS\.

The following sections describe the MPS for various types of origination numbers and for various countries\.

## Short codes<a name="channels-sms-limitations-dedicated"></a>

The following table shows general MPS limits for dedicated short codes\. 


| Geographic area | MPS | 
| --- | --- | 
| United States \(US\) | 100 MPS | 
| Canada \(CA\) | 100 MPS | 
| All other countries and regions | Varies by country\. | 

## Long codes<a name="channels-sms-limitations-longcode"></a>

The following table shows general MPS limits for dedicated long codes\. 


| Geographic area | MPS | 
| --- | --- | 
| United States \(US\) \(10DLC\) | Varies\. Carrier\-dependent, based on the campaign type or brand level\. | 
| Canada \(CA\) | 1 MPS | 
| All other countries and regions | 10 MPS | 

## Toll\-free numbers<a name="channels-sms-limitations-tfn"></a>

Toll\-free numbers are currently only available in the United States\. US toll\-free numbers support 3 MPS\.

**Important**  
If your throughput requirements exceed 3 TPS, you should use a 10DLC number or a short code\. If you purchase multiple toll\-free numbers and attempt to distribute your throughput across them, the mobile carriers are likely to filter all of your messages from their networks\.

## Sender IDs<a name="channels-sms-limitations-senderid"></a>

The following table shows general MPS limits for sender IDs\. 


| Sender ID type | MPS | 
| --- | --- | 
| Customer\-defined using the Amazon Pinpoint API or from the Amazon Pinpoint console | 10 MPS | 
| Shared routes/customer\-owned number | 10 MPS | 