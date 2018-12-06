# Verifying Email Identities<a name="channels-email-manage-verify"></a>

In Amazon Pinpoint, an *identity* is an email address or domain that you use to send email\. Before you can send email using Amazon Pinpoint, you must verify each identity that you plan to use as a "From", "Source", "Sender", or "Return\-Path" address to prove that you own it\. If your account is still in the Amazon Pinpoint sandbox, you also need to verify the identities that you plan to send emails to\.

Before you verify an identity, you first have to create a project\. For information about creating projects, see [Creating an Amazon Pinpoint Project with Email Support](channels-email-setup-create.md)\.

**Topics**
+ [Verifying an Email Address](#channels-email-manage-verify-email-address)
+ [Verifying a Domain](#channels-email-manage-verify-domain)

## Verifying an Email Address<a name="channels-email-manage-verify-email-address"></a>

If you've already created a project for sending email, you may have already verified an email address\. You can verify a different email address by using the Amazon Pinpoint console\.

**To verify an email address**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project that you want to verify the identity in\. 

1. In the navigation pane, under **Settings**, choose **Email**\.

1. Next to **Channel settings**, choose **Edit**\.

1. Under **Identity Type**, choose **Email address**, and then choose **New email address verification**\.

1. For **Email address**, type the email address that you want to verify, and then choose **Verify Email**\.
**Note**  
The email address you specify must be one that you have access to, and that is able to receive email\.

1. Check the inbox of the address that you specified for a message from *no\-reply\-aws@amazon\.com*\. Open the message, and then click the link to verify your email address\.

When you verify email addresses, consider the following:
+ Amazon Pinpoint has endpoints in multiple AWS Regions, and the verification status of the email address is separate for each region\. If you want to send email from the same identity in more than one region, you must verify that identity in each region\.
+ The *local part* of the email address \(the part that comes before the @ sign\) is case sensitive\. If you verify *user@example\.com*, you can't send from *USER@example\.com* unless you verify that address as well\.
+ Domain names are case insensitive\. If you verify *user@example\.com*, you can also send from *user@EXAMPLE\.com*\.
+ You can verify up to 10,000 identities \(domains and email addresses, in any combination\) in each AWS Region\.
+ You can apply labels to verified email addresses by adding a plus sign \(\+\) and a string of text after the local part of the address, and before the @ sign\. For example, to add *label1* to the address *user@example\.com*, use the modified address *user\+label1@example\.com*\.

  You can use as many labels as you want to on each verified address\. You can use labels in the From and Return\-Path fields to implement Variable Envelope Return Path \(VERP\)\. 
**Note**  
When you verify an unlabeled address, you are verifying all addresses that could be formed by adding a label to the address\. However, if you verify a labeled address, you can't use other labels with that address\.

## Verifying a Domain<a name="channels-email-manage-verify-domain"></a>

When you verify a domain, you verify all of the email addresses that are associated with that domain\. Therefore, you don't need to verify email addresses from that domain individually\. For example, if you verify the domain *example\.com*, you can send email from *carlos@example\.com*, *john@example\.com*, and any other address in the *example\.com* domain\.

Before you can use Amazon Pinpoint to send emails from a domain, you have to verify the domain to confirm that you own it, and to prevent others from using it\.

**Note**  
In order to complete the verification process, you have to modify the DNS settings for the domain\. For more information about changing the DNS settings for your domain, see the documentation for your DNS or web hosting provider\.

**To verify a domain**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project that you want to verify the identity in\. 

1. In the navigation pane, under **Settings**, choose **Email**\.

1. Next to **Channel settings**, choose **Edit**\.

1. Under **Identity Type**, choose **Domain**, and then choose **New domain verification**\.

1. For **Domain**, enter the domain that you want to verify\.

1. For **Default FROM address**, enter the email address that should be used to send email on this domain\.

1. Choose **Verify domain**\.

1. Make a note of the record values under **TXT record for domain's DNS settings**\.

1. Open the DNS configuration page for your email domain, and then add a new TXT record\. In the new TXT record, paste the **Name** and **Value** that you received in the previous step\.
**Note**  
If your DNS provider doesn't allow DNS record names to contain underscores, you can omit *\_amazonses* from the **Name**\.  
Some DNS providers automatically add the domain name to the end of each DNS record name\. To avoid duplication of the domain name, add a period to the end of the domain name in the DNS record\. This step indicates to the provider that the domain name is fully qualified\.

   Amazon Pinpoint automatically detects the TXT record within 72 hours\.

When verifying your domain, consider the following:
+ You can send from any subdomain of the verified domain without specifically verifying the subdomain\. For example, if you verify *example\.com*, you don't need to verify *a\.example\.com* or *a\.b\.example\.com*\. 
+ As specified in [RFC 1034](https://tools.ietf.org/html/rfc1034), each DNS label can have up to 63 characters, and the whole domain name must not exceed a total length of 255 characters\.
+ You can verify up to 10,000 identities \(domains and email addresses, in any combination\) in each AWS Region\.