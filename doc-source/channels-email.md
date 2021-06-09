# Amazon Pinpoint email channel<a name="channels-email"></a>

To engage your user segment with email campaigns and messages, enable the email channel in Amazon Pinpoint\.

When you initially enable the email channel, your AWS account has access only to the email sandbox\. With sandbox access, you can send 200 emails per 24\-hour period at a maximum rate of one email per second\. In addition, you can send email only to addresses that you verify\. To increase these sending quotas and to send email to unverified email addresses, [request production access for email](channels-email-setup-production-access.md)\.

You can [monitor your email activity](channels-email-monitor.md) by viewing analytics in the Amazon Pinpoint console or by streaming email events to Kinesis\.

As your email needs change, you can manage your email channel by [updating your email address or domain](channels-email-manage-update.md), [requesting an increase to your sending quotas](channels-email-manage-limits.md), or considering a move to Amazon Simple Email Service\.

## Choosing between Amazon Pinpoint and Amazon Simple Email Service \(SES\)<a name="sestransaction"></a>

If you send a large number of transactional emails, such as purchase confirmations or password reset messages, consider using Amazon SES\. Amazon SES has an API and an SMTP interface, both of which are well suited to sending email from your applications or services\. It also offers additional email features, including email receiving capabilities, configuration sets, and sending authorization capabilities\.

Amazon SES also includes an SMTP interface that you can integrate with your existing third\-party applications, including customer relationship management \(CRM\) services such as Salesforce\. For more information about sending email using Amazon SES, see the [Amazon Simple Email Service Developer Guide](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/Welcome.html) for more information\.