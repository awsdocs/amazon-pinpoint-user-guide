# Registering a 10DLC campaign<a name="settings-register-campaign-10dlc"></a>

A 10DLC campaign indicates how you'll be using the 10DLC number you're requesting\. Before you can create and register a 10DLC campaign, your company must first be registered\. For information on registering a company, see [Registering a company](settings-register-company.md)\.

On this page, you first provide the details about the company you're creating the 10DLC campaign for and then provide the use case details of the campaign itself\. The information on this page is then provided to The Campaign Registry for approval\.

## Step 1: Choose the company associated with the 10DLC campaign<a name="register-campaign-10dlc"></a>

In this section, you'll choose the company you're creating the 10DLC campaign for and provide additional details\.

**Important**  
Carefully verify that all of the information that you enter is correct\. Errors in the registration process could result in reduced throughput for your 10DLC phone numbers\.

**To create a 10DLC campaign**
**Note**  
For each campaign you're registering, there is a carrier registration fee that won't be charged until your campaign is approved\. 

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, and then under **SMS and voice**, choose **10DLC campaigns**\.

1. On the **Create a 10DLC campaign** page, the **Fees** section displays the one\-time carrier 10DLC campaign registration fee, separate from any monthly or AWS fees, in addition to the monthly 10DLC campaign fee\. This fee charged is per campaign\.

1. For **Company name**, choose the company that you're creating this campaign for\. If you haven't already registered the company, you must do that first\. 

1. Enter a **10DLC campaign name**\.

1. For **Vertical**, choose the vertical market that most closely resembles your market\.

1.  In **Help message**, enter the message that your customers receive if they respond with a HELP keyword\.

1. In **Stop message**, enter the message a customer receives from you if they respond with the STOP keyword\.

## Step 2: Add the use case details<a name="register-campaign-usecase"></a>

After you've provided the company information, you'll next supply the 10DLC campaign details\. 

**To provide use case details**

1. For **Use case**, choose a use case that most closely resembles your campaign from the preset list of use cases\. The monthly fee for each use case appears next to the use case name\.

1. Enter at least one **Sample SMS message**\. This is the sample message you plan to send to your customers\. This message must be the exact message you'll be sending\. 

1. If your use case supports multiple scenarios, enter up to four additional sample messages\.

1. The **Campaign and content attributes** section defines the characteristics of your 10DLC campaign\. These are a series of **Yes** or **No** options indicating particular features of the campaign\. Some attributes are mandatory, so you can't change the default value\. These values appear grayed out\.
**Important**  
Make sure that the attributes you choose are applicable to your campaign\. In some cases, choosing an attribute that is not applicable to your campaign can negatively affect your throughput per second \(TPS\)\.
   + **Subscriber opt\-in** – Subscribers can opt in to receive messages about this campaign\.
   + **Subscriber opt\-out** – Subscribers can opt out of receiving messages about this campaign\.
   + **Subscriber help** – Subscribers can contact the message sender after sending the HELP keyword\.
   + **Number pooling** – This 10DLC campaign uses more than 50 phone numbers\. 
   + **Direct lending or loan arrangement ** – The campaign includes information about direct lending or other loan arrangements\.
   + **Embedded link ** – The 10DLC campaign includes an embedded link\. URL shorteners, such as Tinyurl or Bitly, are not allowed\.
   + **Embedded phone number** – The campaign includes an embedded phone number that is not a customer support number\. 
   + **Affiliate marketing** – The 10DLC campaign includes information from affiliate marketing\.
   + **Age\-gated content** – The 10DLC campaign includes age\-gated content as defined by carrier and Cellular Telecommunications and Internet Association \(CTIA\) guidelines\.

1. Choose **Create**\. The SMS and voice page opens\. A message appears indicating that your campaign was submitted and is under review\. You can see the status of your request on the **10DLC campaigns** tab\. You can check the status of your registration on the **10DLC** tab, which will be one of the following:
   + **Active** – Your 10DLC campaign was approved\. You can request a 10DLC and assign that number to your campaign\. See [Requesting a number](settings-request-number.md)\.
   + **Pending** – Approval for your 10DLC campaign has not yet been received by one or more carriers\. In some cases, approval might take one week or more\. If the status changes to any other status, the Amazon Pinpoint console reflects that change\. We don't notify you of status changes\.
   + **Rejected** – Your 10DLC campaign was rejected by one or more carriers\. To get more information, submit a support request that includes the campaign ID of the rejected campaign\. Amazon Pinpoint doesn't include rejection reasons on the console, and we don't notify you if your campaign is rejected\.
   + **Suspended** – One or more carriers suspended your 10DLC campaign\. To get more information, submit a support request that includes the campaign ID of the suspended campaign\. Amazon Pinpoint doesn't include suspension reasons on the console, and we don't notify you if your campaign is suspended\.

1. If your 10DLC is approved, you can request a 10DLC number to associate with that campaign\. For information about requesting a 10DLC number, see [Requesting a number](settings-request-number.md)\.
**Note**  
In some cases, for instance if you've been previously registered with the Campaign Registry, you might be automatically approved\. 