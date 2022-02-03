# Creating an Amazon Pinpoint project with email support<a name="channels-email-setup-create"></a>

To send email with Amazon Pinpoint, you start by creating an Amazon Pinpoint project\. When you create a project, you can enable the email channel for it, and then choose the email identity that you want to use as the sender address\. If you haven't already verified an identity to use with Amazon Pinpoint, you can verify an email address when you create the project\.

In Amazon Pinpoint, an *identity* is an email address or domain that you use to send email\. Before you can send email using Amazon Pinpoint, you must verify each identity that you plan to use as a From, Source, Sender, or Return\-Path address to prove that you own the identity\. For more information about verifying identities, see [Verifying email identities](channels-email-manage-verify.md)\.

**Note**  
If your account is still in the Amazon Pinpoint email sandbox, you also need to verify the identities that you plan to send email to\. For more information about the email sandbox, see [Increasing your sending quotas](channels-email-manage-limits.md#channels-email-manage-limits-increase)\.

**Topics**
+ [Creating an email project when you haven't yet verified an identity](#channels-email-setup-create-not-verified)
+ [Creating an email project when you've already verified an identity](#channels-email-setup-create-already-verified)

## Creating an email project when you haven't yet verified an identity<a name="channels-email-setup-create-not-verified"></a>

If you haven't used Amazon Pinpoint to send email in the past, you probably haven't verified any identities\. The procedure in this section describes the process of creating a project and verifying a single email address at the same time\.

If you've already verified an identity, or if you want to verify an entire domain instead of a single address, use the procedures in [Verifying a domain](channels-email-manage-verify.md#channels-email-manage-verify-domain) instead\.

**To create a new email project and verify an email address**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose **Create a project**\.

1. For **Project name**, enter a name, and then choose **Create**\.
**Note**  
The project name can contain up to 64 alphanumeric characters\. It can also include the following characters: comma \(,\), period \(\.\), at sign \(@\), underscore \(\_\), equals sign \(=\), and plus sign \(\+\)\.

1. On the **Configure features** page, under **Email**, choose **Configure**\.

1. On the **Set up email** page, for **Email address**, enter the email address that you want to use to send email from this project\. Amazon Pinpoint sends an email to the address that you entered\. Open the email, and then click the link in the message to verify the email address\.

## Creating an email project when you've already verified an identity<a name="channels-email-setup-create-already-verified"></a>

If you've already verified an email identity, you can use that identity with your new project\.

**To create a new email project and choose an existing identity**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose **Create a project**\.

1. For **Project name**, enter a name, and then choose **Create**\.
**Note**  
The project name can contain up to 64 alphanumeric characters\. It can also include the following characters: comma \(,\), period \(\.\), at sign \(@\), underscore \(\_\), equals sign \(=\), and plus sign \(\+\)\.

1. On the **Configure features** page, choose **Skip this step**\.

1. In the navigation pane, under **Settings**, choose **Email**\.

1. Next to **Identity details**, choose **Edit**\.

1. Choose **Enable the email channel for this project**\.

1. For **Identity type**, choose either **Email address** or **Domain**, depending on the type of verified identity that you want to use\.

1. Choose **Use an existing email address** if you chose **Email address** in the preceding step, or choose **Use an existing domain** if you chose **Domain**\.

1. From the list, choose the verified email address or domain that you want to use\.

1. If you're setting up a domain, specify the **Default sender address** for that domain\.

1. \(Optional\) For **Friendly sender name**, enter the name that you want to appear in your recipients' email clients\.

1. When you finish, choose **Save**\.