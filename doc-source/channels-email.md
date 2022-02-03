# Amazon Pinpoint email channel<a name="channels-email"></a>

Use the Email channel in Amazon Pinpoint to send email messages to your end users\.

If you haven't used Amazon Pinpoint to send email, your account is in the [email sandbox](channels-email-setup-production-access.md) by default\. When your account is in the email sandbox, you can only send email to addresses that you verify\. Additionally, you can only send 200 emails in a 24\-hour period, at a maximum throughput rate of one message per second\. You can request to have your account removed from the sandbox by [requesting production access for email](channels-email-manage-limits.md#channels-email-manage-limits-increase-case)\.

You can [monitor your email activity](channels-email-monitor.md) by viewing analytics in the Amazon Pinpoint console or by streaming email events to Kinesis\.

As your email needs change, you can manage the email channel by [updating your email address or domain](channels-email-manage-update.md), or [requesting an increase to your sending quotas](channels-email-manage-limits.md)\.

## Choosing between Amazon Pinpoint and Amazon Simple Email Service \(Amazon SES\)<a name="channels-email-sescomparison"></a>

AWS also offers an email\-only service called Amazon SES\. Both Amazon SES and Amazon Pinpoint use the same highly scalable email infrastructure\. The two services offer different features and are intended for different audiences and use cases\.

Amazon SES has an API and an SMTP interface, both of which are well suited to sending email from your applications or services\. You can also use the Amazon SES SMTP interface to integrate with existing third\-party applications, such as Customer Relationship Management \(CRM\) applications\. Amazon SES also offers email features not included in Amazon Pinpoint, including email receiving capabilities, dedicated IP pools, and cross\-account sending authorization capabilities\.

Amazon Pinpoint is well\-suited to users who want to send orchestrated communications, including scheduled campaigns and multi\-step customer journeys\. Amazon Pinpoint also includes features not included with Amazon SES, such as audience segmentation, campaign and journey analytics, and a web\-based console that is accessible to less technical users\. 

For more information about sending email using Amazon SES, see the [Amazon Simple Email Service Developer Guide](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/)\.

**Topics**
+ [Choosing between Amazon Pinpoint and Amazon Simple Email Service \(Amazon SES\)](#channels-email-sescomparison)
+ [Amazon Pinpoint email sandbox](channels-email-setup-production-access.md)
+ [Setting up the Amazon Pinpoint email channel](channels-email-setup.md)
+ [Monitoring email activity with Amazon Pinpoint](channels-email-monitor.md)
+ [Managing the Amazon Pinpoint email channel](channels-email-manage.md)
+ [Sending email in Amazon Pinpoint](channels-email-send.md)
+ [Using dedicated IP addresses with Amazon Pinpoint](channels-email-dedicated-ips.md)
+ [The Amazon Pinpoint deliverability dashboard](channels-email-deliverability-dashboard.md)
+ [Best practices](channels-email-best-practices.md)