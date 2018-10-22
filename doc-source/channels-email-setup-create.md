# Creating an Amazon Pinpoint Project with Email Support<a name="channels-email-setup-create"></a>

To send email messages with Amazon Pinpoint, you must create an Amazon Pinpoint project, and then enable the email channel in that project\. There are two ways to create an Amazon Pinpoint project: by using the Amazon Pinpoint console, or by using the Amazon Pinpoint API\. This section shows you how to create a project by using the console\.

**Topics**
+ [Create a New Project by Using the Console](#channels-email-setup-create-console)

## Create a New Project by Using the Console<a name="channels-email-setup-create-console"></a>

The first step in setting up email in Amazon Pinpoint is to create a new project\. Next, you verify an email address identity\.

In Amazon Pinpoint, an *identity* is an email address or domain that you use to send email\. Before you can send email using Amazon Pinpoint, you must verify each identity that you plan to use as a "From", "Source", "Sender", or "Return\-Path" address to prove that you own it\. If your account is still in the Amazon Pinpoint sandbox, you also need to verify the identities that you plan to send emails to\.

**To create a new Amazon Pinpoint project and verify an email address**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose **Create a project**\.

1. For **Project name**, type a name, and then choose **Create**\.
**Note**  
The project name can contain up to 64 alphanumeric characters\. It can also include the following characters: comma \(,\), period \(\.\), at sign \(@\), underscore \(\_\), equals sign \(=\), and plus sign \(\+\)\.

1. Under **Messaging channels**, next to **Email**, choose **Configure**\.

1. For **Email address**, type the email address that you want to verify, and then choose **Verify**\. Amazon Pinpoint sends an email to the address you specified\. Open the email, and then click the link in the message to verify your email address\.