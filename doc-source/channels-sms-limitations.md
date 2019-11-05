# SMS Limits and Restrictions in Amazon Pinpoint<a name="channels-sms-limitations"></a>

The SMS protocol is subject to several restrictions and limitations\. For example, there are technical limitations that limit the length of each SMS message\. There are also restrictions on the type of content that you can send using SMS\. This topic discusses several of these limitations\. 

When you send SMS messages using Amazon Pinpoint, you should consider these limits and restrictions\. For best results, you should also implement the techniques discussed in [SMS Best Practices](channels-sms-best-practices.md)\.

## Character Limits<a name="channels-sms-limitations-characters"></a>

A single SMS message can contain up to 140 bytes of information\. The number of characters you can include in a single SMS message depends on the type of characters the message contains\. 

If your message only uses [characters in the GSM 03\.38 character set](#channels-sms-limitations-characters-gsm-alphabet), also known as the GSM 7\-bit alphabet, it can contain up to 160 characters\. If your message contains characters outside the GSM 03\.38 character set, it can have up to 70 characters\. When you send an SMS message, Amazon Pinpoint automatically determines the most efficient encoding to use\.

When a message contains more than the maximum number of characters, Amazon Pinpoint automatically splits the message\. When Amazon Pinpoint splits a message into multiple messages, each message contains some additional information about the part of the message that came before it\. When the recipient's device receives messages separated in this way, it uses this additional information to join the incoming messages into one message\. As a result of adding this data, when a long message is split into several messages, the maximum number of characters in each message is reduced to 153 \(for messages that only contain GSM 03\.38 characters\) or 67 \(for messages that contain other characters\)\.

### GSM 03\.38 Character Set<a name="channels-sms-limitations-characters-gsm-alphabet"></a>

The following table lists all of the characters that are present in the GSM 03\.38 character set\. If you send a message that only includes the characters shown in the following table, then the message can contain up to 160 characters\.


| GSM 03\.38 Standard Characters | 
| --- | 
| A | B | C | D | E | F | G | H | I | J | K | L | M | 
| N | O | P | Q | R | S | T | U | V | W | X | Y | Z | 
| a | b | c | d | e | f | g | h | i | j | k | l | m | 
| n | o | p | q | r | s | t | u | v | w | x | y | z | 
| à | Å | å | Ä | ä | Ç | É | é | è | ì | Ñ | ñ | ò | 
| Ø | ø | Ö | ö | ù | Ü | ü | Æ | æ | ß | 0 | 1 | 2 | 
| 3 | 4 | 5 | 6 | 7 | 8 | 9 | & | \* | @ | : | , | ¤ | 
| $ | = | \! | > | \# | \- | ¡ | ¿ | \( | < | % | \. | \+ | 
| £ | ? | " | \) | § | ; | ' | / | \_ | ¥ | Δ | Φ | Γ | 
| Λ | Ω | Π | Ψ | Σ | Θ | Ξ |  |  |  |  |  |  | 

The GSM 03\.38 character set includes several symbols in addition to those shown in the preceding table\. However, each of these characters is counted as two characters because it also includes an invisible escape character:
+ ^
+ \{
+ \}
+ \\
+ \[
+ \]
+ \~
+ \|
+ €

Finally, the GSM 03\.38 character set also includes the following non\-printed characters:
+ A space character\.
+ A line feed control, which signifies the end of one line of text and the beginning of another\.
+ A carriage return control, which moves to the beginning of a line of text \(usually following a line feed character\)\.
+ An escape control, which is automatically added to the characters in the preceding list\.

## Restrictions for Specific Countries or Regions<a name="channels-sms-limitations-country-specific"></a>

Amazon Pinpoint is currently unable to send SMS messages to a small number of countries, including Cuba, Iran, North Korea, Syria, and Sudan\. For a complete list of countries and regions that you can send SMS messages to, see [Supported Countries and Regions \(SMS Channel\)](channels-sms-countries.md)\.

Most countries and regions place restrictions on the type of content that you can send using SMS\. These restrictions vary, but the following types of content are restricted in most countries or regions:
+ Pornographic content
+ Content that is profane or hateful
+ Content that depicts or endorses violence
+ Content that endorses illegal drugs

In many countries and regions, if a customer receives restricted content and complains to a mobile carrier or regulatory agency, the sender might be subject to fines and penalties\. Governments of a few countries and regions actively filter all incoming messages to remove content that they deem offensive or inappropriate\. Always familiarize yourself with the laws and regulations about sending commercial SMS messages for the countries and regions where your customers are located\.

## Originating Numbers<a name="channels-sms-limitations-originating-numbers"></a>

In Amazon Pinpoint, an *originating number* or *originating ID* is the phone number or sender ID that appears on customers' devices when they receive messages from you\. You can use Amazon Pinpoint to send SMS messages from the following types of originating IDs: short codes, long codes, and sender IDs\. The appropriate type of originating ID to use depends on the rules related to sending commercial SMS messages in the countries and regions where your customers are located\. For more information about originating IDs, see [Originating Identities for SMS Messages](channels-sms-originating-identities.md)\.

Each country or region has different rules related to the originating number or ID that commercial senders use when sending SMS messages\. For example, in the United States and Canada, application\-to\-person \(A2P\) messages must be sent using a short code\. In India, A2P messages must be sent using a six\-digit sender ID that's preregistered with mobile carriers\.