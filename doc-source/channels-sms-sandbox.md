# About the Amazon Pinpoint SMS sandbox<a name="channels-sms-sandbox"></a>

New Amazon Pinpoint accounts are placed into an SMS sandbox\. The sandbox protects both AWS customers and SMS recipients from fraud and abuse\. The sandbox also creates a safe environment for test, development, and QA accounts\.

While your account is in the sandbox, you can use all of the SMS sending methods that Amazon Pinpoint offers, such as sending messages using campaigns or journeys, or by using the `SendMessages` API\. However, the following restrictions are in place while your account is in the sandbox:
+ You have a monthly SMS spending limit of $1\.00 \(USD\)\. 
+ You can only send SMS messages to verified destination phone numbers\. You can add up to 10 verified numbers\.
+ The rules and restrictions for sending SMS messages to each destination country apply\. For example, if you want to send a message to a recipient in the United States, you must first purchase a US number\.
+ To verify that you own a phone number, we send a verification code to that number\. While the standard per\-message SMS fees typically apply, we waive the fee for the first five verification codes per phone number\. For more information about SMS pricing, see the [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/) page\.
**Note**  
Message and data rates apply for messages that you receive\. We send one message per verification request\.
+ You can delete a destination phone number\. However, you must wait 24 hours after adding a phone number before you can delete it\.
+ You can only send SMS messages to verified destination numbers\.

You can remove these restrictions by requesting production access\. For more information, see [Moving from the Amazon Pinpoint SMS sandbox to production](channels-sms-awssupport-sandbox.md)\.

## Adding destination numbers to your Amazon Pinpoint sandbox account<a name="channels-sms-destination-number-add"></a>

To use the SMS sandbox, you must provide at least one destination phone number that you verify for testing purposes\. You can add up to 10 verified destination numbers\. These numbers are only used in the SMS sandbox\.

**To add destination numbers**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Overview**\.

1. In the **Destination phone numbers** section, choose **Add phone number**\.

1. On the **Add phone number** window, for **Phone number**, enter the phone number to add, and then choose **Send verification code**\.

   Amazon Pinpoint sends a randomly generated six\-digit code to the destination number\.
**Note**  
Amazon Pinpoint sends the verification code using one of the phone numbers in your account\. If you are attempting to verify a US\-based phone number, note that you must have a dedicated phone number in your account\. For more information about purchasing phone numbers, see [Requesting a number](settings-sms-request-number.md)\.

1. In the **Verification code** field, enter the six\-digit code, and then choose **Submit verification code**\.

   If you don't receive the code after 15 minutes, choose **Resend verification code**\. You can attempt to resend a code up to five times within 24 hours\.

## Verifying destination numbers<a name="channels-sms-verify-number"></a>

You can verify any destination number that has not yet been verified\. You can verify up to one number at a time\.

**To verify a destination number**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Overview**\.

1. In the **Destination phone numbers**, choose a number that has a verification status of **Unverified**\. 

1. Choose **Verify phone number**\.

1. On the **Verify destination phone number** window, choose **Send verification code**\.

1. In the **Verification code** field, enter the code that you received, and then choose **Verify destination phone number**\.

   If you don't receive the code after 15 minutes, choose **Resend verification code**\. You can attempt to resend a code up to five times within 24 hours\.

## Deleting destination numbers<a name="channels-sms-verify-number"></a>

You can delete verified and unverified phone numbers\. You must wait at least 24 hours after adding a number before you can delete it\.

**To delete destination numbers**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, **SMS and voice**, choose **Destination phone numbers**\.

1. Choose one or more destination numbers to delete\. 

1. Choose **Delete phone number\(s\)**\.

1. Choose **Delete**\. 