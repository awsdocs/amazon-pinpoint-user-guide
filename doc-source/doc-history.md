# Document History for Amazon Pinpoint<a name="doc-history"></a>

The following table describes the documentation for this release of Amazon Pinpoint\.
+ **Latest documentation update: **January 10, 2019


| Change | Description | Date | 
| --- | --- | --- | 
| General settings | Added information about using the Amazon Pinpoint console to [delete a project](settings-general.md#settings-general-delete-project)\. | January 10, 2019 | 
| Regional availability | Amazon Pinpoint is now available in the US West \(Oregon\) and EU \(Frankfurt\) AWS Regions\. | December 21, 2018 | 
| Deliverability dashboard | Amazon Pinpoint now includes a [deliverability dashboard](channels-email-deliverability-dashboard.md), which you can use to identify issues that could impact the delivery of emails that you send by using Amazon Pinpoint\. | December 3, 2018 | 
| Event triggers | You can now configure campaigns to be sent when specific events occur\. For example, if a customer adds an item to their cart but doesn't purchase it, you can send them an email\. To learn more about configuring campaigns to be sent when specific events occur, see [Step 4: Choose When to Send the Campaign](campaigns-schedule.md)\. | November 19, 2018 | 
| Voice channel | You can use the new Amazon Pinpoint voice channel to create voice messages and deliver them to your customers over the phone\. Currently, you can only send voice messages by using the Amazon Pinpoint SMS and Voice API\. For more information, see [Amazon Pinpoint Voice Channel](channels-voice.md)\. | November 15, 2018 | 
| Transactional email | You can now use Amazon Pinpoint to send email directly to individual recipients, without having to create segments or campaigns first\. For more information about sending transactional email, see [Sending Email in Amazon Pinpoint](channels-mobile-send.md)\. For more information about setting up the email channel, see [Email Settings](settings-email.md)\. | November 5, 2018 | 
| EU \(Ireland\) availability | Amazon Pinpoint is now available in the EU \(Ireland\) AWS Region\. | October 25, 2018 | 
| New console design | The Amazon Pinpoint console has been completely redesigned to make it easier to use\. We've also streamlined the project creation process so that you can create projects directly in the Amazon Pinpoint console, rather than having to create them in AWS Mobile Hub\. | October 4, 2018 | 
| Advanced segmentation | Added the ability to [create dynamic segments](segments-building.md) that include advanced logic and comparisons\. | October 4, 2018 | 
| Monitoring with CloudWatch | You can now use Amazon CloudWatch to monitor and analyze metrics related to your Amazon Pinpoint account\. | October 4, 2018 | 
| Email tutorial | Added a [tutorial](tutorials-send-an-email.md) that includes complete procedures for setting up a campaign and sending an email\. | June 19, 2018 | 
| Analytics chart references | The Analytics section now includes several new and updated reports\. We've added [documentation](analytics-charts.md) that gives you additional information about each metric\. | June 12, 2018 | 
| Testing campaigns | You can now [test your messages](campaigns-message.md#campaigns-message-test) by sending them to a segment or to a list of individual recipients\. | May 7, 2018 | 
| Define segments by importing user IDs | Define a segment by [importing a file that contains a list of user IDs](segments-importing.md)\. When you send a message to the segment, the potential destinations include each endpoint that's associated with each user ID in the file\. | May 7, 2018 | 
| Phone number verification for SMS | Use the Amazon Pinpoint API to [verify a phone number](channels-sms-verify.md) to determine whether it is a valid destination for SMS messages\. | April 23, 2018 | 
| Self\-managed opt\-outs and dashboard exports | You can configure your SMS account settings so that you can [manage SMS opt\-outs outside of Amazon Pinpoint](settings-sms.md#settings-account-sms-self-managed-opt-out)\. You can also [export Amazon Pinpoint dashboards](analytics-charts.md#analytics-exporting) for further analysis\. | March 28, 2018 | 
| Email project creation and identity verification | Added information about [creating email projects](channels-email-setup-create.md) and [verifying identities used to send email](channels-email-manage-verify.md)\. | March 21, 2018 | 
| SMS best practices | Added [a best practices guide](channels-sms-best-practices.md) that contains tips and information related to SMS campaigns\. | February 23, 2018 | 
| Requesting support for SMS use cases | Contact AWS Support to [request support for your SMS use case](channels-sms-awssupport.md) if you want to increase your spending limit, reserve an origination number, or reserve a sender ID\. | February 21, 2018 | 
| Segment import documentation | Amazon Pinpoint can now create an IAM role for you automatically\. | February 6, 2018 | 
| Two\-way SMS support by country | Updated the [table of Supported Countries and Regions for the SMS channel](channels-sms-countries.md) to list the countries and regions that support 2\-way SMS\. | February 5, 2018 | 
| Time to Live value for mobile push | In the Amazon Pinpoint console, you can specify a Time to Live \(TTL\) value when you [write a mobile push message](campaigns-message.md#campaigns-message-mobile) for a campaign\. | December 22, 2017 | 
| Removal of Amazon S3 export documentation | The ability to export Amazon Pinpoint event data directly to Amazon S3 has been deprecated\. Instead, you can use Amazon Kinesis Data Firehose to send event data to Amazon S3, Amazon Redshift, and other AWS services\. For more information, see [Streaming App and Campaign Events with Amazon Pinpoint](analytics-streaming.md)\. | December 18, 2017 | 
| Segment import documentation | [Importing Segments](segments-importing.md) includes updated information about how to create endpoint files, the attributes you can use within these files, and how to create an IAM role for importing\. | October 26, 2017 | 
| APNs token authentication and APNs sandbox support | The [APNs channel settings](channels-mobile-manage.md#channels-mobile-manage-apns) accept a \.p8 signing key so that Amazon Pinpoint can construct authentication tokens for your push notifications\.Use the APNs channel to send notifications to production and sandbox environments\. | September 27, 2017 | 
| ADM and Baidu mobile push | [Enable mobile push channels](channels-mobile-manage.md) for Amazon Device Message and Baidu Cloud Push in your projects\. | September 27, 2017 | 
| User analytics with Amazon Cognito user pools | To enable [analytics about users and authentication](analytics-usage.md), use Amazon Cognito user pools to manage user sign\-in\. | September 26, 2017 | 
| Account settings | Use the [SMS settings](settings-sms.md) page in the console to manage account\-level SMS settings that take effect for all of your projects\. | September 11, 2017 | 
| Users analytics | [Users charts](analytics-usage.md) in the Amazon Pinpoint console provide metrics about app usage and user authentication\. | August 31, 2017 | 
| Direct email messages | You can [send email messages directly](messages-email.md), to a limited audience, without creating a campaign or engaging a segment\. | July 05, 2017 | 
| New channels: email and SMS | In addition to the [mobile push](channels-mobile.md) channel, you can enable [email](channels-email.md) and [SMS](channels-sms.md) channels as part of your Amazon Pinpoint projects\. With these channels enabled, you can send emails or text messages with your campaigns\. | June 08, 2017 | 
| Direct messaging | You can [send push notifications and text messages directly](messages.md), to a limited audience, without creating a campaign or engaging a segment\. | June 08, 2017 | 
| Revenue charts | You can view [revenue charts](analytics-revenue.md) in the Amazon Pinpoint console to see the revenue that is generated by your app and the number of items purchased by users\. | March 31, 2017 | 
| Event streams | You can configure Amazon Pinpoint to [send your app and campaign events to an Kinesis stream](analytics-streaming.md)\. | March 24, 2017 | 
| Amazon Pinpoint general availability | This release introduces Amazon Pinpoint\. | December 1, 2016 | 