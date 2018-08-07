# Managing Email Sending Limits<a name="channels-email-manage-limits"></a>

To regulate the number of email messages that you can send and the rate at which you can send them, your AWS account has sending limits\. Sending limits benefit all Amazon Pinpoint users because they help to maintain the trusted relationship between Amazon Pinpoint and Internet service providers \(ISPs\)\. Sending limits help you gradually ramp up your sending activity\. They decrease the likelihood that ISPs will block your emails because of sudden, unexpected spikes in your email sending volume or rate\.

The following are Amazon Pinpoint sending limits:

**Sending Quota**  
The maximum number of emails that you can send in a 24\-hour period\. The sending quota reflects a rolling time period\. Every time you try to send an email, Amazon Pinpoint checks how many emails you sent in the previous 24 hours\. If the total number of emails that you have sent is less than your quota, your send request is accepted and your email is sent\. If you have already sent your full quota, your send request is rejected with a throttling exception\. For example, if your sending quota is 50,000, and you sent 15,000 emails in the previous 24 hours, then you can send another 35,000 emails right away\. If you have already sent 50,000 emails in the previous 24 hours, you cannot send more emails until some of the previous sending rolls out of its 24\-hour window\.

**Maximum Send Rate**  
The maximum number of emails that Amazon Pinpoint can accept from your account per second\. You can exceed this limit for short bursts, but not for a sustained period of time\.  
The rate at which Amazon Pinpoint accepts your messages might be less than the maximum send rate\.

When your account is in the Amazon Pinpoint sandbox, your sending quota is 200 messages per 24\-hour period and your maximum sending rate is one message per second\. To increase your sending limits, submit an Amazon Pinpoint Sending Limits Increase case\. For more information, see [Requesting Production Access for Email](channels-email-setup-production-access.md)\. After your account moves out of the sandbox and you start sending emails, you can increase your sending limits further by submitting another Amazon Pinpoint Sending Limits Increase case\. 

## Increasing Your Sending Limits<a name="channels-email-manage-limits-increase"></a>

When your account is out of the sandbox, your sending limits increase if you are sending high\-quality content and we detect that your utilization is approaching your current limits\. Often, the system automatically increases your quota before you need it, and no further action is needed\.

If your existing quota is not adequate for your needs and the system did not automatically increase your quota, you can open an Amazon Pinpoint Sending Limits Increase case in AWS Support Center\.

**Important**  
Plan ahead\. Be aware of your sending limits and try to stay within them\. If you anticipate needing a higher quota than the system allocated, open an Amazon Pinpoint Sending Limits Increase case well before the date that you need the higher quota\.
If you anticipate needing to send more than one million emails per day, you must open an Amazon Pinpoint Sending Limits Increase case\.

For Amazon Pinpoint to increase your quota, use the following guidelines: 
+ **Send high\-quality content** – Send content that recipients want and expect\. 
+ **Send real production content** – Send your actual production email\. This enables Amazon Pinpoint to accurately evaluate your sending patterns, and verify that you are sending high\-quality content\.
+ **Send near your current quota** – If your volume stays close to your quota without exceeding it, Amazon Pinpoint detects this usage pattern and can automatically increase your quota\.
+ **Have low bounce and complaint rates** – Try to minimize the numbers of bounces and complaints\. High numbers of bounces and complaints can adversely affect your sending limits\.
**Important**  
Test emails that you send to your own email addresses may adversely affect your bounce and complaint metrics, or appear as low\-quality content to our filters\. Whenever possible, use the Amazon Simple Email Service \(Amazon SES\) mailbox simulator to test your system\. Emails that are sent to the mailbox simulator do not count toward your sending metrics or your bounce and complaint rates\. For more information, see [Testing Amazon SES Email Sending](http://docs.aws.amazon.com/ses/latest/DeveloperGuide/mailbox-simulator.html)\.

### Opening a Sending Limits Increase Case<a name="channels-email-manage-limits-increase-case"></a>

To apply for higher sending limits for Amazon Pinpoint, open a case in AWS Support Center by using the following instructions\.

**To request a sending limit increase**

1. In your web browser, go to [AWS Support Center](https://console.aws.amazon.com/support/home#/)\. If you are not already signed in to the AWS Management Console, type your user name and password when prompted\.

1. Choose **Create Case**\.

1. Complete the sending limit increase request by providing the following information:
   + **Regarding** – Choose **Service Limit Increase**\.
   + For **Limit Type** – Choose **Pinpoint**\.
   + **Region** – Select the AWS Region for which you are requesting a sending limit increase\. Your sending limits are separate for each AWS Region\. For supported regions, see [AWS Regions and Endpoints](http://docs.aws.amazon.com/general/latest/gr/rande.html#pinpoint_region) in the *AWS General Reference*\.
   + **Limit** – Choose one of the following options:
     + Choose **Desired Daily Sending Quota** if you want to increase the number of messages you can send per day\.
     + Choose **Desired Maximum Send Rate** if you want to increase the number of messages you can send per second\.
   + **New limit value** – Enter the amount you are requesting\.
**Note**  
Only request the amount you think you'll need\. We cannot guarantee that you will receive the amount you request\. The larger your request, the more justification you need to provide to have your request granted\.
   + **Mail type** – Choose the option that best represents your use case\.
   + **Website URL** – Type the URL of your website\.
**Note**  
You are not required to provide a website URL\. However, providing a website URL helps us evaluate your request\.
   + **My email\-sending complies with the [AWS Service Terms](https://aws.amazon.com/service-terms/) and [AWS Acceptable Use Policy \(AUP\)](https://aws.amazon.com/aup/)** – Select **Yes** or **No**\.
   + **I only send to recipients who have specifically requested my mail** – Select **Yes** or **No**\.
   + **I have a process to handle bounces and complaints** – Select **Yes** or **No**\. 
   + **Use Case Description** – Describe how you plan to send email using Amazon Pinpoint in as much detail as possible\. For example, describe the type of emails you are sending and how email sending fits into your business\. The more information you provide that indicates that you send high\-quality messages to recipients who want and expect them, the more likely we are to approve your request\.
   + For **Support Language**, choose the language in which you want to communicate with the AWS Support team\.
   + For **Contact method**, choose **Web**\.

1. When you finish, choose **Submit**\.

### Checking the Status of Your Request<a name="channels-email-setup-check-request-status"></a>

After you submit your request, we review your case\. Allow one full business day for processing\.

**To check the status of your sending limit increase request**

1. In your web browser, go to [AWS Support Center](https://console.aws.amazon.com/support/home#/)\. If you are not already signed in to the AWS Management Console, type your user name and password when prompted\.

1. In the navigation panel on the left side of the screen, choose **Dashboard**\.

1. Under **Recent Cases**, choose your sending limit increase request case\.

1. Review the messages in the **Correspondence** section\. The messages in this section tell you if your request was accepted or rejected\. If your request was accepted, the message specifies your daily and per\-second sending limits\.

If your account is currently in the email sandbox, and if you are granted a sending limit increase, your account is automatically taken out of the sandbox\. After your account is out of the sandbox, you can send email to non\-verified addresses\. However, you must still verify your sending addresses and domains\.

Over time, we will gradually increase your sending limits\. If your needs exceed the gradual increase, you can open another Amazon Pinpoint Sending Limits Increase request\.