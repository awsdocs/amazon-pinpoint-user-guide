# Updating Email Settings<a name="channels-email-manage-update"></a>

Use the Amazon Pinpoint console to update the email settings for your project\. You can enable the email channel for an existing project, or you can update your email address or domain\.

To set up a new project with email support, see [Creating an Amazon Pinpoint Project with Email Support](channels-email-setup-create.md)\.

**To update your email settings**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project for which you want to update email settings\.

1. In the navigation menu, choose **Settings**\.

1. On the **Settings** page, choose **Channels**, and then choose **Email**\.

1. If you haven't already, choose **Enable email channel**\.

1. Choose the email identity that you want to add or update: **Email address** or **Email domain**\.

1. Provide your email address or domain, and choose **Verify**\. Then, follow the instructions displayed by the console\.

   If you verify an email address, Amazon Pinpoint sends a verification email to the address that you provide\. Follow the instructions in the email to complete the verification process\.

   If you verify an email domain, the console displays a TXT record that you must add to the domain's DNS settings\. For more information, see [Domain Verification TXT Records](channels-email-setup-txt-record.md)\.

   For more information on verifying an email address or domain, see [Email Address or Domain Verification](channels-email-manage-verify.md)\.

1. When you finish, choose **Save**\.