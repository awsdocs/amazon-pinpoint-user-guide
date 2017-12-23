# Amazon Pinpoint Email Channel<a name="channels-email"></a>

To engage your user segment with an email campaign, enable the email channel in Amazon Pinpoint\.

You can create an Amazon Pinpoint project with email support by creating a project in AWS Mobile Hub and adding the **Messaging & Analytics** feature\. You can also enable the email channel in an existing project by using the **Settings** page in the Amazon Pinpoint console\. Before you send email with Amazon Pinpoint, you must verify that you own the *from* address or the email domain\.

When you first enable the email channel, your AWS account has access only to the email sandbox\. With sandbox access, you can send 200 emails per 24\-hour period at a maximum rate of one email per second\. You can only send emails to addresses you verify\. To increase your sending limits and to send email to unverified email addresses, see [Requesting Production Access for Email](channels-email-setup-production-access.md)\.

You can monitor your email activity by viewing analytics in the Amazon Pinpoint console or by streaming email events to Kinesis\.

As your email needs change, you can manage your email channel by updating your email address or domain, or requesting a sending limits increase\.


+ [Setting up the Amazon Pinpoint Email Channel](channels-email-setup.md)
+ [Monitoring Email Activity with Amazon Pinpoint](channels-email-monitor.md)
+ [Managing the Amazon Pinpoint Email Channel](channels-email-manage.md)