# SMS Best Practices<a name="channels-sms-best-practices"></a>

Mobile phone users tend to have a very low tolerance for unsolicited SMS messages\. Response rates for unsolicited SMS campaigns will almost always be low, and therefore the return on your investment will be poor\.

Additionally, mobile phone carriers continuously audit bulk SMS senders\. They throttle or block messages from numbers that they determine to be sending unsolicited messages\. 

Sending unsolicited content is also a violation of the [AWS Acceptable Use Policy](https://aws.amazon.com/aup/#No_E-Mail_or_Other_Message_Abuse)\. The Amazon Pinpoint team routinely audits SMS campaigns, and might throttle or block your ability to send messages if it appears that you're sending unsolicited messages\.

Finally, in many countries, regions, and jurisdictions, there are severe penalties for sending unsolicited SMS messages\. For example, in the United States, the [Telephone Consumer Protection Act](https://transition.fcc.gov/cgb/policy/TCPA-Rules.pdf) states that consumers are entitled to $500–$1,500 in damages \(paid by the sender\) for each unsolicited message that they receive\.

This section describes several best practices that might help you improve your customer engagement and avoid costly penalties\. However, you should always familiarize yourself with the customs and regulations in all of the jurisdictions where your customers are located before sending SMS messages through Amazon Pinpoint\.


+ [Obtain Permission](#channels-sms-best-practices-obtain-permission)
+ [Audit Your Customer Lists](#channels-sms-best-practices-audit-lists)
+ [Respond Appropriately](#channels-sms-best-practices-respond-appropriately)
+ [Adjust Your Sending Based on Engagement](#channels-sms-best-practices-adjust-engagement)
+ [Send at Appropriate Times](#channels-sms-best-practices-appropriate-times)
+ [Avoid Cross\-Channel Fatigue](#channels-sms-best-practices-cross-channel-fatigue)
+ [Maintain Independent Lists](#channels-sms-best-practices-independent-lists)
+ [Use Dedicated Short Codes](#channels-sms-best-practices-dedicated-short-codes)

## Obtain Permission<a name="channels-sms-best-practices-obtain-permission"></a>

Don't send messages to customers who haven't asked to receive them\. 

If customers can sign up to receive your messages by using an online form, add a CAPTCHA to the form to prevent automated scripts from subscribing people without their knowledge\.

When you receive an SMS opt\-in request, send the customer a message that asks them to confirm that they want to receive messages from you\. Don't send that customer any additional messages until they confirm their subscription\. A subscription confirmation message might resemble the following example:

```
Text YES to join Example Corp. alerts. 2 msgs/month. Msg & data rates may apply. 
Reply HELP for help, STOP to cancel.
```

Maintain records that include the date, time, and source of each opt\-in request and confirmation\. This might be useful if a carrier or regulatory agency requests it, and can also help you perform routine audits of your customer list\.

Finally, note that transactional SMS messages, such as order confirmations or one\-time passwords, typically don't require explicit consent as long as you tell your customers that you're going to send them these messages\. However, you should never send marketing messages to customers who only provided you with permission to send them transactional messages\.

## Audit Your Customer Lists<a name="channels-sms-best-practices-audit-lists"></a>

If you send recurring SMS campaigns, audit your customer lists on a regular basis\. Auditing your customer lists ensures that the only customers who receive your messages are those who are interested in receiving them\. 

When you audit your list, send each opted\-in customer a message that reminds them that they're subscribed, and provides them with information about unsubscribing\. A reminder message might resemble the following example:

```
You're subscribed to Example Corp. alerts. Msg & data rates may apply. 
Reply HELP for help, STOP to unsubscribe.
```

## Respond Appropriately<a name="channels-sms-best-practices-respond-appropriately"></a>

When a recipient replies to your messages, make sure that you respond with useful information\. For example, when a customer responds to one of your messages with the keyword "HELP", send them information about the program that they're subscribed to, the number of messages you'll send each month, and the ways that they can contact you for more information\. A HELP response might resemble the following example:

```
HELP: Example Corp. alerts: email help@example.com or call XXX-555-0199. 2 msgs/month. 
Msg & data rates may apply. Reply STOP to cancel.
```

When a customer replies with the keyword "STOP", let them know that they won't receive any further messages\. A STOP response might resemble the following example:

```
STOP: You're unsubscribed from Example Corp. alerts. No more messages will be sent. 
Reply HELP, email help@example.com, or call XXX-555-0199 for more info.
```

## Adjust Your Sending Based on Engagement<a name="channels-sms-best-practices-adjust-engagement"></a>

Your customers' priorities can change over time\. If customers no longer find your messages to be useful, they might opt out of your messages entirely, or even report your messages as unsolicited\. For these reasons, it's important that you adjust your sending practices based on customer engagement\.

For customers who rarely engage with your messages, you should adjust the frequency of your messages\. For example, if you send weekly messages to engaged customers, you could create a separate monthly digest for customers who are less engaged\. 

Finally, remove customers who are completely unengaged from your customer lists\. This step prevents customers from becoming frustrated with your messages\. It also saves you money and helps protect your reputation as a sender\.

## Send at Appropriate Times<a name="channels-sms-best-practices-appropriate-times"></a>

Only send messages during normal daytime business hours\. If you send messages at dinner time or in the middle of the night, there's a good chance that your customers will unsubscribe from your lists in order to avoid being disturbed\. Furthermore, it doesn't make sense to send SMS messages when your customers can't respond to them immediately\. 

## Avoid Cross\-Channel Fatigue<a name="channels-sms-best-practices-cross-channel-fatigue"></a>

In your campaigns, if you use multiple communication channels \(such as email, SMS, and push messages\), don't send the same message in every channel\. When you send the same message at the same time in more than one channel, your customers will probably perceive your sending behavior to be annoying rather than helpful\.

## Maintain Independent Lists<a name="channels-sms-best-practices-independent-lists"></a>

When customers opt in to a topic, make sure that they only receive messages about that topic\. Don't send your customers messages from topics that they haven't opted into\.

## Use Dedicated Short Codes<a name="channels-sms-best-practices-dedicated-short-codes"></a>

If you use short codes, maintain a separate short code for each brand and each type of message\. For example, if your company has two brands, use a separate short code for each one\. Similarly, if you send both transactional and promotional messages, use a separate short code for each type of message\. To learn more about requesting short codes, see [Requesting Dedicated Short Codes for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.