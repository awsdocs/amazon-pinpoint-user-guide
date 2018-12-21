# Verifying Email Identities<a name="channels-email-manage-verify"></a>

In Amazon Pinpoint, an *identity* is an email address or domain that you use to send email\. Before you can send email by using Amazon Pinpoint, you must verify each identity that you plan to use as a "From", "Source", "Sender", or "Return\-Path" address to prove that you own it\. If your account is still in the Amazon Pinpoint sandbox, you also need to verify the identities that you plan to send email to\.

Before you verify an identity, you have to create a project and enable the email channel for the project\. For more information, see [Creating an Amazon Pinpoint Project with Email Support](channels-email-setup-create.md)\.

**Topics**
+ [Verifying an Email Address](#channels-email-manage-verify-email-address)
+ [Verifying a Domain](#channels-email-manage-verify-domain)

## Verifying an Email Address<a name="channels-email-manage-verify-email-address"></a>

If you've already created a project for sending email, you may have already verified an email address\. You can verify a different email address by using the Amazon Pinpoint console\.

**To verify an email address**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that you want to verify an identity for\. 

1. In the navigation pane, under **Settings**, choose **Email**\.

1. On the **Identities** tab, choose **Edit**\.

1. Select **Enable the email channel for this project**\.

1. Under **Identity type**, choose **Email address**, and then choose **Verify a new email address**\.

1. For **Email address**, enter the email address that you want to verify\.
**Note**  
The email address that you enter must be one that you can access and is able to receive email\.

1. Choose **Verify email address**\.

1. Choose **Save**\.

1. Check the inbox of the address that you entered and look for a message from *no\-reply\-aws@amazon\.com*\. Open the message and click the link to verify the email address\.

When you verify an email address, consider the following:
+ Amazon Pinpoint has endpoints in multiple AWS Regions and the verification status of an email address is separate for each Region\. If you want to send email from the same identity in more than one Region, you must verify that identity in each Region\.
+ The *local part* of the email address \(the part that comes before the @ sign\) is case sensitive\. For example, if you verify *user@example\.com*, you can't send email from *USER@example\.com* unless you verify that address too\.
+ Domain names are case insensitive\. For example, if you verify *user@example\.com*, you can also send email from *user@EXAMPLE\.com*\.
+ You can verify up to 10,000 identities \(domains and email addresses, in any combination\) in each AWS Region\.
+ You can apply labels to verified email addresses by adding a plus sign \(\+\) followed by a string of text after the local part of the address and before the @ sign\. For example, to add *label1* to the address *user@example\.com*, use the modified address *user\+label1@example\.com*\. You can use as many labels as you want for each verified address\. You can also use labels in the From and Return\-Path fields to implement Variable Envelope Return Path \(VERP\)\. 
**Note**  
When you verify an unlabeled address, you are verifying all addresses that could be formed by adding a label to the address\. However, if you verify a labeled address, you can't use other labels with that address\.

## Verifying a Domain<a name="channels-email-manage-verify-domain"></a>

When you verify a domain, you verify all the email addresses that are associated with that domain\. Therefore, you don't need to verify email addresses from that domain individually\. For example, if you verify the *example\.com* domain, you can send email from *carlos@example\.com*, *jane@example\.com*, and any other address in the *example\.com* domain\.

Before you can use Amazon Pinpoint to send email from a domain, you have to verify the domain to confirm that you own it and to prevent others from using it\.

**Note**  
To complete the verification process, you have to modify the DNS settings for the domain\. For more information about changing the DNS settings for your domain, see the documentation for your DNS or web hosting provider\.

**To verify a domain**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that you want to verify an identity for\. 

1. In the navigation pane, under **Settings**, choose **Email**\.

1. On the **Identities** tab, choose **Edit**\.

1. Under **Identity type**, choose **Domain**, and then choose **Verify a new domain**\.

1. For **Domain**, enter the domain that you want to verify\.

1. For **Default sender address**, enter the email address that you want to use when you send email from this domain\.

1. Choose **Verify domain**\.

1. Make a note of the name/host and record values under **DNS records for domain verification**\. Or, to download and save the values in a \.csv file, choose **Download record set**\.

1. Open the DNS configuration page for your email domain, and then add a new TXT record\. In the new TXT record, paste the name/host and record values that you received in the previous step\.
**Note**  
If your DNS provider doesn't allow DNS record names to contain underscores, you can omit *\_amazonses* from the **Name/host** value\.  
Some DNS providers automatically add the domain name to the end of each DNS record name\. To avoid duplication of the domain name, add a period to the end of the domain name in the DNS record\. This step indicates to the provider that the domain name is fully qualified\.

   Amazon Pinpoint automatically detects the TXT record within 72 hours\.

When you verify a domain, consider the following:
+ You can send email from any subdomain of the verified domain without verifying the subdomain specifically\. For example, if you verify *example\.com*, you don't need to verify *a\.example\.com* or *a\.b\.example\.com*\. 
+ As specified in [RFC 1034](https://tools.ietf.org/html/rfc1034), each DNS label can have up to 63 characters\. In addition, the whole domain name must not exceed a total length of 255 characters\.
+ You can verify up to 10,000 identities \(domains and email addresses, in any combination\) in each AWS Region\.