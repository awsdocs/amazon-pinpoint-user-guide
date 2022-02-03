# Associating an existing long code with a 10DLC campaign<a name="settings-sms-10dlc-associate-long-code"></a>

If you have an existing long code, you can associate that long code with one of your current 10DLC campaigns by opening a ticket with AWS Support\. The long code that you associate with the 10DLC campaign can only be used with that campaign, and you can't use it for any other 10DLC campaign\. While your long code is being associated with your 10DLC campaign, you can still use it, but the mobile carriers will treat it as an unregistered long code\. Keep in mind that unregistered long codes typically have worse deliverability rates than 10DLC phone numbers that have completed the registration process\.

Before you open the request, make a note of the long codes that you want to associate with your 10DLC campaigns, and the campaign ID of the campaign that you want each long code to be associated with\.

**Important**  
Before you can associate any long codes with a campaign, you must register a 10DLC campaign\. For more information, see [Registering a 10DLC campaign](settings-sms-10dlc-register-campaign.md)\. 

**To associate a long code with a 10DLC campaign**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **SMS and voice**, choose **Phone numbers**\.

1. Choose the long code that you want to associate with a 10DLC campaign, and then choose **Assign to 10DLC campaign**\. The AWS Support Center opens in a new tab\.

1. Under **Create case**, choose **Service limit increase**\.

1. In the **Case details** section, for **Limit type**, choose **Pinpoint**\.

1. In the **Requests** section, do the following:
   + For **Region**, choose the AWS Region where your long code exists\.
   + For **Limit**, choose **10DLC \- Associate existing US long code to 10DLC campaign**\.
   + For **New limit value**, enter any value\. The value that you enter in this field isn't important\.

1. In the **Case description** section, for **Use case description**, list the 10DLC campaign ID and the long codes that you want to associate with that campaign\. You can include multiple long codes in the request, but only one campaign ID\.

1. Under **Contact options**, for **Preferred contact language**, choose the language that you prefer to use when communicating with AWS Support\.

1. For **Contact method**, choose your preferred method of communicating with AWS Support\.

1. Choose **Submit**\.