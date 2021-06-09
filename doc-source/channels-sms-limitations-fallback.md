# Message fallback<a name="channels-sms-limitations-fallback"></a>

When sending a message using the Amazon Pinpoint API, three optional parameters can be passed in the request: `originationNumber`, `registeredKeyword`, and `senderID`\. If Amazon Pinpoint encounters an `originationNumber` error – for example, an invalid character – and the error is retriable, Amazon Pinpoint uses a fallback process for choosing a valid number for the request\. Fallback checks for a valid number in the order below\. At any point during this process Amazon Pinpoint will choose the first valid number it finds as the originating number\.

1. Origination number\. Any other valid origination numbers are checked\.

1. Keyword\. Registered keywords are scanned and matched against any dedicated number\. 

1. Sender ID\. Any other valid sender IDs are checked\.

**Note**  
If send a message with an `originationNumber` that does not exist in your account, there is no fallback process, and an exception message returned instead\.

If none of the previous parameters are passed in the request, Amazon Pinpoint looks at your account and checks for a valid number in this order:

1. Dedicated numbers\. Any dedicated numbers associated with y our account are checked in this order: short code, 10DLC, long code/toll\-free number\. Domestic numbers are checked before international numbers\. If you have both transactional and promotional long codes in your account, Amazon Pinpoint chooses a transational number by default\.

1. Default sender IDs

1. Shared routes\. 
**Note**  
Amazon Pinpoint will make a best effort to deliver messages in countries where an origination identity is not required\.