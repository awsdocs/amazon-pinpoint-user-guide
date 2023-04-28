# Registering a 10DLC campaign<a name="settings-sms-10dlc-register-campaign"></a>

Amazon Pinpoint’s SMS vendors introduced new manual review processes on 10DLC \(10 Digit Long Code\) campaigns to address SMS spam concerns raised by US carriers\. Reviews are triggered when a number is associated to a 10DLC campaign\. Reviews take between 3–4 weeks to process\.

You can use short codes and toll\-free numbers to send SMS in the United States\. Toll\-free number reviews take 1 week\. For more information on US Toll\-Free numbers, see [US toll\-free number registration requirements and process](settings-sms-tfn-register.md)\.

Your campaign is approved when the 10DLC number\(s\) associated with the campaign show as active in the Amazon Pinpoint console\. If additional information is required to approve a 10DLC campaign, you will be notified through [AWS Health Dashboard](https://docs.aws.amazon.com/health/latest/ug/aws-health-dashboard-status.html)\.



When you register a 10DLC campaign, you provide a description of your use case, as well as the message templates that you plan to use\. Before you can create and register a 10DLC campaign, you must first register your company\. For information on registering your company, see [Registering a company or brand for use with 10DLC](settings-sms-10dlc-register-company.md)\.

**Note**  
After you register your company, Amazon Pinpoint shows one of two statuses for the registration: **Verified** or **Unverified**\. You can only complete the 10DLC campaign registration process if the status of your company registration is **Verified**\. This status allows you to create low\-volume mixed use campaigns\.  
If the status is **Unverified**, it usually means that some of the data that you provided when you registered your company was incorrect\. You won't be able to create any 10DLC campaigns while your company has this status\. You can modify your company registration to attempt to fix the issues with your company registration\. For more information about modifying 10DLC company registrations, see [Editing or deleting a registered company](settings-sms-10dlc-modify-company.md)\.

On this page, you first provide the details about the company you're creating the 10DLC campaign for and then provide the use case details of the campaign itself\. The information on this page is then provided to the Campaign Registry\(TCR\) for approval\.

In this section, you choose a company to associate with the 10DLC campaign, and provide some additional details\.

**To register a 10DLC campaign**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **SMS and voice**, choose **Phone numbers**\.

1. On the **10DLC campaigns** tab, choose **Create a 10DLC campaign**\.

1. On the **Create a 10DLC campaign** page, in the **Campaign info** section, do the following:

   1. For **Company name**, choose the company that you're creating this campaign for\. If you haven't already registered the company, you must do that first\. For more information about registering a company, see [Registering a company or brand for use with 10DLC](settings-sms-10dlc-register-company.md)\.

   1. For **10DLC campaign name**, enter a name for the campaign\. The name must be a minimum of 40 characters\.

   1. For **Vertical**, choose option that best represents your company\.

   1. For **Opt\-in workflow**, enter a description of how users consent to receive SMS messages\. The description has to be a minimum of 40 characters\. For example, by filling out an online form on your website\. If you have multiple opt\-in methods, they have to be listed as well\.

   1. For **Help message**, enter the message that your customers receive if they send the keyword "HELP" to your 10DLC phone number\. The message has to be a minimum of 20 characters\.

   1. For **Stop message**, enter the message that your customers receive if they send the keyword "STOP" to your 10DLC phone number\. The message has to be a minimum of 20 characters\.
**Tip**  
Your customers can reply to your messages with the word "HELP" to learn more about the messages that they're receiving from you\. They can also reply "STOP" to opt\-out of receiving messages from you\. The US mobile carriers require you to provide responses to both of these keywords\.  
The following is an example of a HELP response that complies with the requirements of the US mobile carriers:  
**ExampleCorp Account Alerts: For help call 1\-888\-555\-0142 or go to example\.com\. Msg&data rates may apply\. Text STOP to cancel\.**  
The following is an example of a compliant STOP response:  
**You are unsubscribed from ExampleCorp Account Alerts\. No more messages will be sent\. Reply HELP for help or call 1\-888\-555\-0142\.**  
Your responses to these keywords must contain 160 characters or fewer\.

1. In the **Campaign capabilities** section, do the following:
   + Select **SMS** to enable text messages for the 10DLC campaign\.
   + Select **Voice** to enable voice messages for the 10DLC campaign\.
**Note**  
When you select to enable voice messages, it lengthens the amount of time to review your registration\.

1. In the **Message type** section, select either **Transactional** or **Promotional** message type\.
   + **Transactional** – Select this option if your use case is for time\-sensitive content, such as alerts and one\-time passwords\.
   + **Promotional** – Select this option if your use case is for marketing\-related content\.

1. In the **Campaign use case** section, do the following:

   1. For **Use case type**, if you have a charity\-related use case, choose **Special**\. Otherwise, choose **Standard**\.

   1. For **Use case**, choose a use case that most closely resembles your campaign from the preset list of use cases\. The monthly fee for each use case appears next to the use case name\.

**Standard**
      + **2FA** – Any authentication, verification, or one\-time passcode\.
      + **Account Notifications** – Standard notifications for account holders, relating to and being about an account\.
      + **Customer care** – All customer interaction, including account management and customer support\.
      + **Delivery notifications** – Information about the status of the delivery of a product or service\.
      + **Fraud alert messaging** – Messaging regarding potential fraudulent activity on an account\.
      + **Higher education** – Campaigns created on behalf of Colleges or Universities\. It also includes School Districts and education institutions that fall outside of any "free to the consumer" messaging model\.
      + **Marketing** – Any communication with marketing and/or promotional content\.
      + **Mixed** – Mixed messaging reserved for specific consumer service industry\.
      + **Public service announcement** – An informational message that is meant to raise the audience's awareness about an important issue\.
      + **Polling and voting** – Requests for surveys and voting for non political arenas\.
      + **Security alert** – A notification that the security of a system, either software or hardware, has been compromised in some way and there is an action the end users need to take\.
      + **Low Volume** – Small throughput, any combination of use\-cases\. Examples include: test, demo accounts\.

**Special**
      + Communications from a non\-religious registered [501\(c\)\(3\) charity](https://en.wikipedia.org/wiki/501(c)(3)_organization) aimed at providing help and raising money for those in need\.
**Note**  
The monthly charge for registering the 10DLC campaign is shown next to each use case type\. Most 10DLC campaign types have the same monthly charge\. The charge for registering Low\-Volume Mixed use cases is lower than for other use case types\. However, Low\-Volume Mixed campaigns support lower throughput rates than other campaign types\.

   1. Enter at least one **Sample SMS message**\. This is the sample message that you plan to send to your customers\. Each sample message has to be a minimum of 20 characters\. If you plan to use multiple message templates for this 10DLC campaign, include them as well\.
**Important**  
Don't use placeholder text for your sample messages\. The example messages that you provide should reflect the actual messages that you plan to send as accurately as possible\.

1. The **Campaign and content attributes** section contains a series of **Yes** or **No** questions related to the particular features of the campaign\. Some attributes are mandatory, so you can't change the default value\.

   Make sure that the attributes you choose are accurate for your campaign\.

   Indicate whether each of the following applies to the campaign that you're registering:
   + **Subscriber opt\-in** – Subscribers can opt in to receive messages about this campaign\.
   + **Subscriber opt\-out** – Subscribers can opt out of receiving messages about this campaign\.
   + **Subscriber help** – Subscribers can contact the message sender after sending the HELP keyword\.
   + **Number pooling** – This 10DLC campaign uses more than 50 phone numbers\. 
   + **Direct lending or loan arrangement ** – The campaign includes information about direct lending or other loan arrangements\.
   + **Embedded link ** – The 10DLC campaign includes an embedded link\. Links from common URL shorteners, such as TinyUrl or Bit\.ly, are not allowed\. However, you can use URL shorteners that offer custom domains\.
   + **Embedded phone number** – The campaign includes a phone number that isn't a customer support number\. 
   + **Affiliate marketing** – The 10DLC campaign includes information from affiliate marketing\.
   + **Age\-gated content** – The 10DLC campaign includes age\-gated content as defined by carrier and Cellular Telecommunications and Internet Association \(CTIA\) guidelines\.

1. Choose **Create**\.

**Note**  
Your 10DLC campaign status is set to **Pending** as it is reviewed\. After the review is successfully completed, your 10DLC campaign status is **Requires number**\. You must associate the 10DLC campaign with a 10DLC number\. For more information, see [Requesting a number](settings-sms-request-number.md)\.  
After you've associated a number, your 10DLC campaign goes back to a status of **Pending** for final review with third party registration partners\.<a name="settings-sms-10dlc-view"></a>

After you submit the registration details for your campaign, the SMS and voice page opens\. A message appears indicating that your campaign was submitted and is under review\. You can see the status of your request on the **10DLC campaigns** tab\. You can check the status of your registration on the **10DLC** tab, which will be one of the following:
+ **Active** – Your 10DLC campaign was approved\. You can request additional 10DLC phone numbers to associate with your 10DLC campaign as needed\. For more information, see [Requesting a number](settings-sms-request-number.md)\.
+ **Requires Number** – Your 10DLC campaign successfully passed an initial review and now requires to be associated with a 10DLC phone number\. After you associate the number, the 10DLC campaign goes into a final review with third party registration partners before being set to **Active**\.
+ **Requires Update** – Your 10DLC campaign review has been rejected\. You must address the rejection feedback before resubmitting for review and approval\. For more information, see [10DLC campaign registration rejection reasons](#settings-sms-10dlc-register-campaign-rejection-reason)\.
+ **Pending** – Your 10DLC campaign hasn't been approved yet\. In some cases, approval might take one week or more\. If the status changes, the Amazon Pinpoint console reflects that change\. We don't notify you of status changes\.
+ **Rejected** – Your 10DLC campaign was rejected\. To get more information on why your 10DLC campaign was rejected and how to fix it, see [10DLC campaign registration rejection reasons](#settings-sms-10dlc-register-campaign-rejection-reason)\. If you need more assistance, submit a support request that includes the campaign ID of the rejected campaign\.
+ **Suspended** – One or more carriers suspended your 10DLC campaign\. To get more information, submit a support request that includes the campaign ID of the suspended campaign\. Amazon Pinpoint doesn't include suspension reasons on the console, and we don't notify you if your campaign is suspended\.

If your 10DLC campaign is approved, you can request a 10DLC phone number to associate with that campaign\. For information about requesting a 10DLC number, see [Requesting a number](settings-sms-request-number.md)\.

## 10DLC campaign registration rejection reasons<a name="settings-sms-10dlc-register-campaign-rejection-reason"></a>

If your 10DLC campaign was rejected, use the following table to determine why it was rejected and what you can do to fix your 10DLC campaign registration\. After you determine why the campaign was rejected, you can modify the existing campaign to address that issue and resubmit\. For more information, see [Editing a 10DLC campaign](settings-sms-10dlc-modify-campaign.md#settings-sms-10dlc-modify-campaign-edit)\.


**Reason for rejection**  

| Amazon Pinpoint rejection short description | Amazon Pinpoint rejection long description | 
| --- | --- | 
| Campaign Attributes don't match the website, sample message content, or both\. | The campaign attributes do not align or match with the company website, sample message content, or both\. Update the registration to align the campaign attributes with the company website, sample message content, or both\. Campaign attributes can include company vertical, subscriber opt\-in/\-out, help responses, and age\-gated content\.  Campaigns are not automatically resubmitted when you resubmit your company registration\. If you make any changes to your company information, then you must resubmit the company information\. If you make any campaign changes, you must resubmit the campaign registration\.  | 
| Use case and message samples are inconsistent\. | There are inconsistencies between the use case and messages samples provided in the campaign\. Update the registration to align the use case and message samples\. | 
| Company and message samples are inconsistent or missing message samples\. | There are inconsistencies between the company website and message samples provided in the campaign, or the campaign was missing message samples\. Update your company and campaign registration information so that the website and message samples align\.  Campaigns are not automatically resubmitted when you resubmit your company registration\. If you make any changes to your company information, then you must resubmit the company information\. If you make any campaign changes, you must resubmit the campaign registration\.  | 
| Use case, message samples, or both are considered restricted or disallowed by mobile operators; prohibited content: cannabis\. | The use case, message samples provided, or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited content: cannabis\. | 
| Use case, message samples, or both are considered restricted or disallowed by mobile operators; prohibited content: guns/ammo\. | The use case, message samples provided, or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited content: guns/ammo\. | 
| Use case, message samples, or both are considered restricted or disallowed by mobile operators; prohibited content: SHAFT\. | The use case, message samples provided, or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited content: SHAFT\. | 
| Use case, message samples, or both are considered restricted or disallowed by mobile operators; prohibited content: gambling\. | The use case, message samples provided, or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited content: gambling\. | 
| Use case, message samples, or both are considered restricted or disallowed by mobile operators; prohibited content: hate\. | The use case, message samples provided, or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited content: hate\. | 
| Use case, message samples, or both are considered restricted or disallowed by mobile operators; prohibited content: alcohol with failure to age gate\. | The use case, message samples provided, or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited content: alcohol with failure to age gate\. | 
| Use case, message samples, or both are considered restricted or disallowed by mobile operators; prohibited content: tobacco/vape with failure to age gate\. | The use case, message samples provided, or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited content:tobacco/vape with failure to age gate\. | 
| Use case, message samples or both are considered restricted or disallowed by mobile operators; prohibited use case: lead generation/affiliate marketing; other\. | The use case, message samples provided or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited use case: lead generation/affiliate marketing; other\. | 
| Use case, message samples or both are considered restricted or disallowed by mobile operators; prohibited use case: lead generation/affiliate marketing; high risk financial\. | The use case, message samples provided or both are considered restricted content under US Telecom regulations\. If you believe that your content is falsely considered restricted, you may attempt to update your sample messages and use case, and resubmit the registration\. Prohibited use case: lead generation/affiliate marketing; high risk financial\. | 
| ISV/Reseller\. Company information and service information/message samples mismatch\. | The company and campaign information do not match and is identified as an independent software vendor \(ISV\) or reseller\. Register the company information that matches the service and end user\. Create a new campaign that has service information aligned with company information\. | 
| Campaign appears to be Direct Lending Arrangement but appropriate Content Attribute was not selected\. | The company and campaign details submitted appear to be direct lending arrangement\. Edit your campaign and mark "Yes" for Direct Lending Arrangement attribute and resubmit\. | 
| Unofficial email domain for what appears to be large company that would have an official domain\. | The email domain provided does not appear to be official given the company information submitted with the registration\. Update the registration with an official email address that matches domain of the company and resubmit\.  Campaigns are not automatically resubmitted when you resubmit your company registration\. If you make any changes to your company information, then you must resubmit the company information\. If you make any campaign changes, you must resubmit the campaign registration\.  | 
| Opt\-in process not compliant or opt\-in isn't explicit\. | The opt\-in workflow that you have provided is either insufficient, non\-compliant, or not explicit for end users to receive specific SMS messages\. A compliant opt\-in process will clearly specify how your recipient is able to provide their explicit consent to receive SMS messages\. Some common rejection reasons: missing explicit language around SMS opt\-in consent, mismatch between provided company name and message samples, receiving a text message can't be required to sign up for service, or SMS opt\-in consent can't be included in the Terms of Service\. | 
| Website not provided or not working\. | The company information did not include a website or the website was inaccessible\. Update your company information with an accessible website and resubmit both your company and campaign for review\.  Campaigns are not automatically resubmitted when you resubmit your company registration\. If you make any changes to your company information, then you must resubmit the company information\. If you make any campaign changes you must resubmit the campaign registration\.  | 

## Using 10DLC campaigns in multiple AWS Regions<a name="settings-sms-10dlc-register-campaign-regions"></a>

When you register a company, that company is available in your AWS account in all AWS Regions\. However, the same isn't true for 10DLC campaigns\. A 10DLC campaign can be viewed in all AWS Regions, but after you associate a 10DLC number to the campaign, the campaign is then locked to send from the AWS Regions that the 10DLC number was purchased in\.

If you plan to use 10DLC in more than one AWS Region, you must register separate 10DLC campaigns in each of those AWS Regions\. This step is necessary to comply with carrier requirements\. You're charged for each campaign that you register, even if the use case is exactly the same\.

Registering multiple campaigns has the added benefit of increasing your throughput rates for messages that you send to recipients who use AT&T as their mobile carrier\. AT&T provides 10DLC throughput rates for each campaign\. Comparatively, T\-Mobile handles 10DLC throughput based on a daily message allocation for each company, regardless of the number of campaigns\.