# Amazon Pinpoint SMS sandbox<a name="channels-sms-sandbox"></a>

To help protect customers from fraud and abuse, we place your account in a sandbox environment when you first create it\. The sandbox creates a safe environment for testing and development accounts\. A notification banner appears in the Amazon Pinpoint console while you're in the sandbox environment\. In the sandbox, you have full access to Amazon Pinpoint SMS sending methods, with the following restrictions: 
+ You have a monthly limit of $1\.00 \(USD\)\. 
+ You can send SMS to verified destination phone numbers only\. You must provide at least one verified phone number\. You can add up to 10\. 
+ Per\-country restrictions apply\. For example, if you want to send to a US destination, you must first purchase a US number\.
+ To verify that you own a phone number, we send a verification code to that number\. While the standard per\-message SMS fees typically apply, we waive the fee for up to five verification codes per phone number\. For more information about SMS pricing, see the [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/) page\.
+ Before you can delete a verified destination phone number, you must wait 24 hours after adding it\. Unverified numbers can be deleted at any time\.
+ When you're sending a test message, or using campaigns and journeys, you can only send messages to your verified destination numbers\. 

When you've done sufficient testing in the sandbox and are confident in your messaging, you can remove these restrictions by requesting production access\. For more information, see [Moving from the Amazon Pinpoint SMS sandbox to production](channels-sms-awssupport-sandbox.md)\.

## Adding destination numbers to your Amazon Pinpoint sandbox account<a name="channels-sms-destination-number-add"></a>

To use the SMS sandbox, you must provide at least one destination phone number that you verify for testing purposes\. You can add up to 10 verified destination numbers\. These numbers are only used in the SMS sandbox\. 

**To add destination numbers**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, **SMS and voice**, choose **Destination phone numbers**\.

   Add up to 10 phone numbers\. A counter displays the phone number count, verification status, and verification date\.

1. Choose **Add phone number**\. 

1. In the **Phone number** field, enter the phone number to add, and then choose **Send verification code**\. 

   A randomly generated six\-digit code is sent to the destination number\. The receiver must reply with the verification code within 15 minutes, before it expires\. The number displayed on the recipient's device is selected from one of the numbers in your account\. Number selection occurs in the following order: short code, 10DLC, long code, toll\-free number\. If you have multiple types of numbers —for example, if you have multiple long codes—Amazon Pinpoint randomly selects a long code to use\.

1. In the **Verification code** field, enter the received code, and then choose **Submit verification code**\.

   If 15 minutes pass and you do not receive the code, choose **Resend verification code**\. You can attempt to resend a code up to five times within 24 hours\.

Your **Destination phone numbers** are updated to include the newly added **Phone number**, its **Verification status**, and the **Verification date**\. Any phone numbers that are not yet verified appear with an **Unverified** status and no verification date\.

## Verifying destination numbers<a name="channels-sms-verify-number"></a>

You can verify any destination number that has not yet been verified\. You can verify up to one number at a time\.

**To verify a destination number**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, **SMS and voice**, choose **Destination phone numbers**\.

1. Choose a number with an **Unverified** status\. 

1. Choose **Verify phone number**\.

1. For **Verify *206\-555\-0100***, choose **Send verification code**\.

1. Enter the received code in the **Verification code** field, and then choose **Verify *206\-555\-0100***\.

   If 15 minutes pass and you do not receive the code, choose **Resend verification code**\. You can attempt to resend a code up to five times within 24 hours\.

## Deleting destination numbers from your Amazon Pinpoint sandbox account<a name="channels-sms-verify-number"></a>

You can delete verified and unverified phone numbers\. Unverified numbers can be deleted at any time\. For verified numbers, you must wait 24 hours after adding them before you can delete them\.

**To delete destination numbers**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, **SMS and voice**, choose **Destination phone numbers**\.

1. Choose one or more destination numbers to delete\. 

1. Choose **Delete phone number\(s\)**\.

1. Choose **Delete**\. 