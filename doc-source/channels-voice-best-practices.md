# Best practices for the voice channel<a name="channels-voice-best-practices"></a>

This section contains several best practices related to sending voice messages using Amazon Pinpoint\. These practices can help ensure the satisfaction of your recipients, and can protect you from unexpected charges\.

**Topics**
+ [Comply with laws and regulations](#channels-voice-best-practices-understand-laws)
+ [Send at appropriate times](#channels-voice-best-practices-appropriate-times)
+ [Avoid cross\-channel fatigue](#channels-voice-best-practices-cross-channel-fatigue)
+ [Protect yourself against voice fraud](#channels-voice-best-practices-fraud-protection)

## Comply with laws and regulations<a name="channels-voice-best-practices-understand-laws"></a>

You can face significant fines and penalties if you violate the laws and regulations of the places where your customers reside\. For this reason, it's vital to understand the laws related to automated voice calls in each country where you do business\. As a sender, these laws may apply to you even if you don't reside in one of these countries\. You are responsible for complying with all applicable laws\. Note that some national subdivisions have stricter rules than their parent countries\. For example, several US states have rules that are more strict than the US Federal laws concerning voice calls\. This information is not intended to be legal advice\. Consult an attorney in each country or region where your customers are located to obtain legal advice\.

## Send at appropriate times<a name="channels-voice-best-practices-appropriate-times"></a>

Only send messages during normal daytime business hours in each recipient's time zone\. If you send messages at dinner time or in the middle of the night, there's a good chance that your customers will unsubscribe from your lists in order to avoid being disturbed again in the future\. Additionally, many countries and regions restrict the days and times at which people can receive automated messages\. Although regulations vary by country, it's a good idea to not send messages before 9 AM or after 8 PM\. Many countries also prohibit sending messages on Sundays and national holidays\. This information is not intended to be legal advice\. Consult an attorney in each country or region where your customers are located to obtain legal advice\.

## Avoid cross\-channel fatigue<a name="channels-voice-best-practices-cross-channel-fatigue"></a>

If you use multiple communication channels \(such as voice, email, SMS, and push messages\), don't send the same message across multiple channels unless there's a good reason for doing so\. If you send the same message at the same time in more than one channel, your customers are likely to perceive this behavior as annoying rather than helpful\.

## Protect yourself against voice fraud<a name="channels-voice-best-practices-fraud-protection"></a>

Because voice calls can be expensive, it's important to secure your AWS account against unauthorized access, and to monitor the destinations of the messages that you send\.

**Carefully manage IAM roles, policies, and users**  
In general, the IAM policies of your users should grant *least privilege*—that is, only the permissions that are required to do a task, and nothing more\. You can restrict these permissions so that only a small number of IAM users have them\. For more information, see [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)in the *IAM User Guide*\.  
Additionally, you should change the passwords and access keys for your IAM users regularly\. The process of changing passwords and access keys is known as *credential rotation*\. For more information, see [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#rotate-credentials)

**Know which country you're sending to**  
The per\-minute price that you pay for sending voice messages depends on the recipient's country\. The country code of the recipient's phone number isn't always the best way to tell which country they're in\. For example, many senders realize that the United States and Canada both use the same country code \(\+1\)\. However, they might not realize that 23 other countries and territories \(mainly in the Pacific and Caribbean\) also use this country code\. Sending voice messages to some of these countries can be significantly more expensive than for others\. For example, sending messages to recipients in the US and Canada costs $0\.013 per minute, but sending to Jamaica costs $0\.564 per minute[1](#channels-voice-best-practices-fraud-protection-note-1)\. Phone numbers in all three of these countries begin with \+1 followed by 10 digits, so to the untrained eye they can be difficult to distinguish\.  
You can use the [Amazon Pinpoint phone number validation service](https://docs.aws.amazon.com/pinpoint/latest/developerguide/validate-phone-numbers.html) to verify the country of each phone number that you send messages to\.

**Limit your sending to specific countries**  
If you only plan to send messages to recipients in specific countries, configure your message\-sending applications to only send messages to those countries\.

**Limit the number of messages that you send to a single number**  
Configure your applications so that they can only send a certain number of voice messages to the same recipient each day\.

 

1 Prices quoted are accurate as of December, 2021\. Per\-minute rates are subject to change\. For current pricing, see [Amazon Pinpoint Pricing](http://aws.amazon.com/pinpoint/pricing/#Voice_messages)\.