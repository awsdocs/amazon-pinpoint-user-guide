# Amazon Pinpoint SMS channel<a name="channels-sms"></a>

You can use the SMS channel in Amazon Pinpoint to send SMS messages \(text messages\) to your customers' mobile devices\. Amazon Pinpoint can send SMS messages to recipients in [over 200 countries and regions](channels-sms-countries.md)\. In some countries and regions, you can also receive messages from your customers by using the two\-way SMS feature\. When you create a new Amazon Pinpoint account, your account is placed in an SMS sandbox\. This initially limits your monthly spending and who you can send messages to\. For more information, see [Amazon Pinpoint SMS sandbox](channels-sms-sandbox.md)\. 

To send text messages using Amazon Pinpoint, you must [enable the SMS channel in your project](channels-sms-setup.md)\. Depending on how you use Amazon Pinpoint to send SMS messages, you might also need to [initiate a request with AWS Support](channels-sms-awssupport.md) to enable or modify certain SMS options for your account\. For example, you can request to increase your SMS spending quota, to move from the sandbox to production, or you can request a short code to use when sending and receiving messages\. 

To receive text messages using Amazon Pinpoint, you should first obtain a dedicated [short code](channels-sms-awssupport-short-code.md) or [long code](channels-sms-awssupport-long-code.md)\. When you have a dedicated number, you can [enable two\-way SMS for it](channels-sms-two-way.md)\. Finally, you can [specify the messages that Amazon Pinpoint sends to customers when it receives incoming messages](settings-sms.md)\. 

In the [SMS and voice settings section](settings-sms.md) of the Amazon Pinpoint console, you can manage SMS channel settings for your use case and budget\. For example, you can set your monthly SMS spending quota, or change your default message type\.

**Note**  
When you configure SMS channel settings in Amazon Pinpoint, your changes apply to other AWS services that send SMS messages, such as Amazon SNS\.

**Topics**
+ [About the Amazon Pinpoint SMS sandbox](channels-sms-sandbox.md)
+ [Setting up the Amazon Pinpoint SMS channel](channels-sms-setup.md)
+ [Originating identities for SMS messages](channels-sms-originating-identities.md)
+ [SMS limits and restrictions in Amazon Pinpoint](channels-sms-limitations.md)
+ [Requesting support for SMS messaging with Amazon Pinpoint](channels-sms-awssupport.md)
+ [Monitoring SMS activity with Amazon Pinpoint](channels-sms-monitor.md)
+ [Managing the Amazon Pinpoint SMS channel](channels-sms-manage.md)
+ [Test SMS sending with the Amazon Pinpoint SMS simulator](channels-sms-simulator.md)
+ [Configuring two\-way SMS messaging in Amazon Pinpoint](channels-sms-two-way.md)
+ [Country capabilities and limitations for SMS with Amazon Pinpoint](channels-sms-country-capabilities.md)
+ [Managing Pools in Amazon Pinpoint](channels-sms-managing-pools.md)
+ [Best practices](channels-sms-best-practices.md)
+ [Understanding SMS billing and usage reports for Amazon Pinpoint](channel-sms-monitoring-bill.md)