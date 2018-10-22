# Updating Email Settings<a name="channels-email-manage-update"></a>

You can use the Amazon Pinpoint console to update the email settings for your project\. For example, you can change the verified identity associated with the project, or verify a new identity\.

**To update your email settings**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project for which you want to update email settings\.

1. In the navigation pane, under **Settings**, choose **Email**\.

1. Next to **Channel settings**, choose **Edit**\.

1. Choose the email identity that you want to add or update: **Email address** or **Domain**\.

1. Choose whether you want to use an existing identity, or verify a new identity\.

1. Provide your email address or domain, and choose **Verify**\. Then, follow the instructions shown on the console\.

   If you verify an email address, Amazon Pinpoint sends a verification email to the address that you provide\. Follow the instructions in the email to complete the verification process\.

   If you verify an email domain, the console displays a TXT record that you have to add to the DNS settings for your domain\.

   For more information about verifying an email address or domain, see [Verifying Email Identities](channels-email-manage-verify.md)\.

1. When you finish, choose **Save**\.