# Message parts per second \(MPS\)<a name="channels-sms-limitations-mps"></a>

Message parts per second \(MPS\) is determined by the type of originating identifier used in the message\. Character encoding can also affect how many message parts your message is split into\. For more information on how character encoding affects message parts, see [SMS character limits in Amazon Pinpoint](channels-sms-limitations-characters.md)\. The following sections describe the MPS for each of the originating identifiers\.

## Short codes<a name="channels-sms-limitations-dedicated"></a>

The following table shows general MPS limits for dedicated short codes\. 


| 
| 
|  **Geographic area** |  **MPS** | 
| --- |--- |
| United States \(US\) | 100 MPS | 
| Canada \(CA\) | 100 MPS | 
| All other countries and regions | Varies by country\. | 

## Long codes<a name="channels-sms-limitations-longcode"></a>

The following table shows general MPS limits for dedicated long codes\. 


| 
| 
|  **Geographic area** |  **MPS** | 
| --- |--- |
| United States \(US\) \(10DLC\) | Varies\. Carrier\-dependent, based on the campaign type or brand level\. | 
| Canada \(CA\) | 1 MPS | 
| All other countries and regions | 10 MPS | 

## Toll\-free numbers<a name="channels-sms-limitations-tfn"></a>

The following table shows general MPS limits for toll\-free numbers\. 


| 
| 
|  **Geographic area** |  **MPS** | 
| --- |--- |
| United States \(US\) \(10DLC\) | 3 MPS | 
| Canada \(CA\) | N/A | 
| All other countries and regions | N/A | 

## Sender IDs<a name="channels-sms-limitations-senderid"></a>

The following table shows general MPS limits for sender IDs\. 


| 
| 
|  **Sender ID type** |  **MPS** | 
| --- |--- |
| Customer\-defined using the Amazon Pinpoint API or from the Amazon Pinpoint console | 10 MPS | 
| Shared routes/customer\-owned number | 10 MPS | 