# Test SMS sending with the Amazon Pinpoint SMS simulator<a name="channels-sms-simulator"></a>

Amazon Pinpoint includes an SMS simulator, which you can use to send text messages and receive realistic event records\. The SMS simulator is a helpful way to view actual SMS event records\. It's also useful for testing applications that use Amazon Pinpoint to send SMS messages\. Messages sent to these destination phone numbers are designed to stay within Amazon Pinpoint, so they are not sent over the carrier network\.

When you send a message to an SMS simulator phone number, you pay the standard outbound SMS messaging rate\. The price that you pay differs depending on the destination country—in this case, the country that the simulated phone number is based in\. For more information about SMS pricing, see [Amazon Pinpoint pricing](https://aws.amazon.com/pinpoint/pricing/#SMS_text_messages)\.

You can send messages to the SMS simulator phone numbers even if your account is in the [SMS sandbox](channels-sms-sandbox.md)\. However, messages that you send to the simulator are counted toward your [monthly spending quota](channels-sms-awssupport-spend-threshold.md)\. 

**Topics**
+ [Prerequisites](#channels-sms-simulator-prereqs)
+ [SMS simulator phone numbers](#channels-sms-simulator-numbers)
+ [Using the simulator](#channels-sms-simulator-using)

## Prerequisites<a name="channels-sms-simulator-prereqs"></a>

All Amazon Pinpoint customers can send messages to the SMS simulator phone numbers—you don't have to take any special steps to enable it\. However, if you want to receive event records when you send SMS messages, you must first enable event streaming\. For more information, see Event streaming\. To view examples of SMS simulator event records, see [SMS events](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams-data-sms.html) in the *Amazon Pinpoint Developer Guide*\.

## SMS simulator phone numbers<a name="channels-sms-simulator-numbers"></a>

The SMS simulator is available in several countries\. For each country, there are phone numbers that generate message success events, and numbers that generate message failure events\. The following table contains SMS simulator phone numbers for all of the countries in which the simulator is available\.


****  

| Country | Event type | Phone number | 
| --- | --- | --- | 
| Australia | Success | \+61455944038 | 
| Australia | Failure | \+61455944039 | 
| Austria | Success | \+43676800442031 | 
| Austria | Failure | \+43676800442032 | 
| Belgium | Success | \+32460213922 | 
| Belgium | Failure | \+32460213923 | 
| Chile | Success | \+56229140630 | 
| Chile | Failure | \+56229140631 | 
| Czech Republic | Success | \+420790542286 | 
| Czech Republic | Failure | \+420790542287 | 
| Denmark | Success | \+4525919410 | 
| Denmark | Failure | \+4525919215 | 
| Estonia | Success | \+37282720792 | 
| Estonia | Failure | \+37282720793 | 
| Finland | Success | \+3584573979110 | 
| Finland | Failure | \+3584573979111 | 
| France | Success | \+33755512501 | 
| France | Failure | \+33755512502 | 
| Hong Kong | Success | \+85257048426 | 
| Hong Kong | Failure | \+85257048854 | 
| Hungary | Success | \+36707178770 | 
| Hungary | Failure | \+36707178772 | 
| Italy | Success | \+394390009172 | 
| Italy | Failure | \+394390009174 | 
| Jersey | Success | \+447937404990 | 
| Jersey | Failure | \+447937404992 | 
| Luxembourg | Success | \+352691385880 | 
| Luxembourg | Failure | \+352691385882 | 
| Netherlands | Success | \+3197008100148 | 
| Netherlands | Failure | \+3197008100150 | 
| Norway | Success | \+4759449384 | 
| Norway | Failure | \+4759449387 | 
| Poland | Success | \+48732141440 | 
| Poland | Failure | \+48732141442 | 
| Portugal | Success | \+351927946948 | 
| Portugal | Failure | \+351927946950 | 
| Romania | Success | \+40783900330 | 
| Romania | Failure | \+40783900332 | 
| Spain | Success | \+34683783440 | 
| Spain | Failure | \+34683783442 | 
| Sweden | Success | \+46790645100 | 
| Sweden | Failure | \+46790645102 | 
| Switzerland | Success | \+41798075872 | 
| Switzerland | Failure | \+41798075874 | 
| Taiwan | Success | \+886903444630 | 
| Taiwan | Failure | \+886903444632 | 
| United Kingdom | Success | \+447860019066 | 
| United Kingdom | Failure | \+447860019067 | 
| United States | Success | \+14254147755 | 
| United States | Failure | \+14254147167 | 

## Using the simulator<a name="channels-sms-simulator-using"></a>

The way that you use the SMS simulator depends on how you use Amazon Pinpoint\. If you use the campaign and journey features of Amazon Pinpoint, then you can import a test segment that contains the test numbers\. You can use the following data to create an imported segment that contains all of the SMS simulator phone numbers\.

```
ChannelType,Address,Location.Country,Attributes.SimulatorType
SMS,+43676800442031,AT,Success
SMS,+43676800442032,AT,Failure
SMS,+61455944038,AU,Success
SMS,+61455944039,AU,Failure
SMS,+32460213922,BE,Success
SMS,+32460213923,BE,Failure
SMS,+41798075872,CH,Success
SMS,+41798075874,CH,Failure
SMS,+56229140630,CL,Success
SMS,+56229140631,CL,Failure
SMS,+420790542286,CZ,Success
SMS,+420790542287,CZ,Failure
SMS,+4525919410,DK,Success
SMS,+4525919215,DK,Failure
SMS,+37282720792,EE,Success
SMS,+37282720793,EE,Failure
SMS,+34683783440,ES,Success
SMS,+34683783442,ES,Failure
SMS,+3584573979110,FI,Success
SMS,+3584573979111,FI,Failure
SMS,+33755512501,FR,Success
SMS,+33755512502,FR,Failure
SMS,+447860019066,GB,Success
SMS,+447860019067,GB,Failure
SMS,+85257048426,HK,Success
SMS,+85257048854,HK,Failure
SMS,+36707178770,HU,Success
SMS,+36707178772,HU,Failure
SMS,+394390009172,IT,Success
SMS,+394390009174,IT,Failure
SMS,+447937404990,JE,Success
SMS,+447937404992,JE,Failure
SMS,+352691385880,LU,Success
SMS,+352691385882,LU,Failure
SMS,+3197008100148,NL,Success
SMS,+3197008100150,NL,Failure
SMS,+4759449384,NO,Success
SMS,+4759449387,NO,Failure
SMS,+48732141440,PL,Success
SMS,+48732141442,PL,Failure
SMS,+351927946948,PT,Success
SMS,+351927946950,PT,Failure
SMS,+40783900330,RO,Success
SMS,+40783900332,RO,Failure
SMS,+46790645100,SE,Success
SMS,+46790645102,SE,Failure
SMS,+886903444630,TW,Success
SMS,+886903444632,TW,Failure
SMS,+14254147755,US,Success
SMS,+14254147167,US,Failure
```

If you use the [SendMessages](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-messages.html#SendMessages) API to send SMS messages from your applications, specify one of the SMS simulator phone numbers as the `DestinationNumber` in your call to the `SendMessages` API\. For more information about using the SendMessages API to send messages programmatically, see [Send SMS messages](https://docs.aws.amazon.com/pinpoint/latest/developerguide/send-messages-sms.html) in the *Amazon Pinpoint Developer Guide*\.