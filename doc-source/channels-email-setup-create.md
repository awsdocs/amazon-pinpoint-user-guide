# Creating an Amazon Pinpoint Project with Email Support<a name="channels-email-setup-create"></a>

You can create a new project with email support by using AWS Mobile Hub\. In the Mobile Hub console, create a project, and add the **Messaging & Analytics** feature\. Then, enable the email channel as part of that feature\. After you create a project in Mobile Hub, the project becomes available in Amazon Pinpoint\.

You can also enable the email channel for an existing Amazon Pinpoint project by using the **Settings** page in the Amazon Pinpoint console\. For more information, see [Updating Email Settings](channels-email-manage-update.md)\.

**To create a project with email support**

1. Sign in to the AWS Management Console and open the Mobile Hub console at [https://console.aws.amazon.com/mobilehub](https://console.aws.amazon.com/mobilehub)\.

1. If you have other Mobile Hub projects, choose **Create new mobile project**\. If this is your first project, skip this step because you are taken directly to the page for creating a new project\.

1. Enter a project name\. The name you enter will be the name of your project in the Amazon Pinpoint console\. 

1. For the region, keep **US East \(Virginia\)**\. 

1. Choose **Create project**\. Mobile Hub creates the project and shows the **Pick and configure features for your project** page\.

1. Choose **Messaging & Analytics**\.

1. On the **Messaging & Analytics** page, for **What engagement features do you want to enable?**, choose **Messaging**\.

1. For **What Messaging Channels do you want to enable?**, choose **Email**\.

1. For **Do you want to enable email messaging?**, choose **Enable**\.

1. To verify your email address or domain, choose the **Amazon Pinpoint console** link\. You are directed to the **Settings** page in the Amazon Pinpoint console, where you complete the following steps:

   1. Choose the email identity that you want to use: **Email address** or **Email domain**\.

   1. Provide your email address or domain, and choose **Verify**\. Then, follow the instructions displayed by the console\.

      If you verify an email address, Amazon Pinpoint sends a verification email to the address that you provide\. Follow the instructions in the email to complete the verification process\.

      If you verify an email domain, the console displays a TXT record that you must add to the domain's DNS settings\. For more information, see [Domain Verification TXT Records](channels-email-setup-txt-record.md)\.

      For more information on verifying an email address or domain, see [Email Address or Domain Verification](channels-email-manage-verify.md)\.

   1. When you finish, choose **Save**\.

1. In the Mobile Hub console, for **What engagement features do you want to enable?**, choose **Analytics**, and choose **Enable**\. With analytics enabled, Amazon Pinpoint provides metrics about your email campaign activity\.