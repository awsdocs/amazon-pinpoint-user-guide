# Managing the Amazon Pinpoint Voice Channel<a name="channels-voice-manage"></a>

You can use the Amazon Pinpoint console to change some of the settings and limits that apply to the voice channel\. For example, you can request production access for your account, or lease dedicated phone numbers for sending voice messages\.

**Topics**
+ [Requesting Production Access](#channels-voice-manage-sandbox)
+ [Requesting Phone Numbers for the Voice Channel](#channels-voice-manage-request-phone-numbers)
+ [Relinquishing Dedicated Phone Numbers](#channels-voice-manage-remove-phone-numbers)

## Requesting Production Access<a name="channels-voice-manage-sandbox"></a>

When you first start using the voice channel, your account is in the *sandbox*\. While your account is in the sandbox, certain limits apply to your account\. For more information about these limits, see [Voice Limits](https://docs.aws.amazon.com/pinpoint/latest/developerguide/limits.html#limits-voice) in the *Amazon Pinpoint Developer Guide*\.

To remove these limits from your account, you can request to have your account removed from the sandbox\. When your account is removed from the sandbox, it has *production access*\.

**To request production access**

1. [Create a new case in Support Center](https://console.aws.amazon.com/support/v1#/case/create)\.

1. Choose **Create case**\.

1. For **Regarding**, choose **Service Limit Increase**\.

1. For **Limit Type**, choose **Pinpoint Voice**\.

1. For **Region**, choose the AWS Region that you use to send voice messages\.

1. For **Limit**, choose **Production Access**\.

1. For **New limit value**, type the maximum amount in USD that you want to spend on voice messages each calendar month\.

1. For **Use Case Description**, provide the following details:
   + The website or app of the company or service that will send voice messages\.
   + The service that's provided by your website or app, and how your voice messages contribute to that service\.
   + Information about how users sign up to voluntarily receive your voice messages\.

1. When you finish, choose **Submit**\. 

The AWS Support team provides an initial response to your request within 24 hours\.

In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. If we’re able to do so, we'll grant your request within this 24\-hour period\. However, if we need to obtain additional information from you, it might take longer to resolve your request\.

We might not be able to grant your request if your use case doesn’t align with our policies\.

## Requesting Phone Numbers for the Voice Channel<a name="channels-voice-manage-request-phone-numbers"></a>

You can use the Amazon Pinpoint console to request phone numbers to use for making voice calls\. These phone numbers are *dedicated*—that is, they're reserved for use only by your Amazon Pinpoint account\. You can request local phone numbers that are based in a variety of countries or regions\.

**To request a phone number for sending voice messages**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project\.

1. Under **Settings**, choose **SMS and voice**\. 

1. In the **Number settings** section, choose **Request long codes**\.

1. For **Target country or region**, choose the country or region that the long code should be based in\. The long code that you receive uses the local number format for the country or region you selected\.
**Note**  
Currently, you can only lease long codes for a limited number of countries and regions by using the Amazon Pinpoint console\. To obtain a long code for a country that isn't listed in the **Target country or region** list, open a new **Account and Billing Support** case in the [AWS Support Center](https://console.aws.amazon.com/support/v1#/case/create)\.

1. For **Quantity**, choose the number of phone numbers that you want to lease\.

1. For **Default call type**, choose the option that best describes the type of messages that you plan to use this number to send\.

1. \(Optional\) To add phone numbers for an additional country or region, choose **Request additional numbers**\. Repeat steps 5 through 7 for each additional country or region\.

1. When you finish, note the price shown next to **Subtotal**\. We charge you this amount each month\. If you agree to this monthly charge, choose **Submit** to request the phone numbers\.

## Relinquishing Dedicated Phone Numbers<a name="channels-voice-manage-remove-phone-numbers"></a>

If you don't need a dedicated phone number anymore, you can end your lease on that number by relinquishing it\. When you relinquish a dedicated phone number, we stop charging you for it in your bill for the next calendar month\.

**Important**  
If you relinquish a dedicated phone number, you might not be able to obtain the same phone number again in the future\.

**To relinquish a phone number**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose a project\.

1. Under **Settings**, choose **SMS and voice**\. 

1. Choose the number that you want to relinquish, as shown in the following image\. Choose **Remove long code**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-voice-manage-remove-phone-numbers.png)

1. On the **Remove number confirmation** window, confirm that you want to remove the phone number, and then choose **Confirm**\.