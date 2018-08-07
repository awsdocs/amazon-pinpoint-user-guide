# Verifying an Email Identity<a name="channels-email-manage-verify"></a>

In Amazon Pinpoint, an *identity* is an email address or domain that you use to send email\. Before you can send email using Amazon Pinpoint, you must verify each identity that you'll use as a "From", "Source", "Sender", or "Return\-Path" address to prove that you own it\. If your account is still in the Amazon Pinpoint sandbox, you also need to verify the identities that you plan to send emails to\.

Before you verify an identity, you must first create a project\. For information about creating projects, see [Creating an Amazon Pinpoint Project with Email Support](channels-email-setup-create.md)\.

**Topics**
+ [Verifying an Email Address](#channels-email-manage-verify-email-address)
+ [Verifying a Domain](#channels-email-manage-verify-domain)

## Verifying an Email Address<a name="channels-email-manage-verify-email-address"></a>

You can verify an email address by using the Amazon Pinpoint console\.

**To verify an email address**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project that you want to verify the identity in\. 
**Note**  
If you created the project in Mobile Hub, it appears in Amazon Pinpoint in lowercase letters, with all spaces removed, and with "\_MobileHub" added to the end of the name\. For example, if you created a project in Mobile Hub and named it "My New Project", it would appear in Amazon Pinpoint as "mynewproject\_MobileHub"\. If you create a project by using the API, the name isn't changed\.

1. Choose **Settings**\.

1. On the **Channels** tab, under **Choose channels to enable**, choose **Email**\.

1. Select the check box next to **Enable email channel**\.

1. Under **To use email messaging provide either an email address or email domain to start verifying your credentials**, choose **Email address**\.

1. For **Email address**, type the email address that you want to verify, and then choose **Verify**\.
**Note**  
The email address you specify must be one that you have access to, and that is able to receive email\.

1. Check the inbox of the address that you specified for a message from *no\-reply\-aws@amazon\.com*\. Open the message, and then click the link to verify your email address\.

When you verify email addresses, consider the following:
+ The *local part*of the email address \(the part that comes before the @ sign\) is case sensitive\. If you verify *user@example\.com*, you can't send from *USER@example\.com* unless you verify that address as well\.
+ Domain names are case insensitive\. If you verify *user@example\.com*, you can also send from *user@EXAMPLE\.com*\.
+ You can verify up to 10,000 identities \(domains and email addresses, in any combination\) per AWS account\.
+ You can apply labels to verified email addresses by adding a plus sign \(\+\) and a string of text after the local part of the address, and before the @ sign\. For example, to add *label1* to the address *user@example\.com*, use the modified address *user\+label1@example\.com*\.

  You can use as many labels as you want to on each verified address\. You can use labels in the From and Return\-Path fields to implement Variable Envelope Return Path \(VERP\)\. 
**Note**  
When you verify an unlabeled address, you are verifying all addresses that could be formed by adding a label to the address\. However, if you verify a labeled address, you can't use other labels with that address\.

## Verifying a Domain<a name="channels-email-manage-verify-domain"></a>

When you verify a domain, you're verifying all email addresses that are associated with that domain\. Therefore, you don't need to verify email addresses from that domain individually\. For example, if you verify the domain *example\.com*, you can send email from *user1@example\.com*, *user2@example\.com*, or any other address in the *example\.com* domain\.

Before you can use Amazon Pinpoint to send emails from a domain, you must verify the domain to confirm that you own it, and to prevent others from using it\.

**Note**  
In order to complete the verification process, you must be able to modify the DNS settings for the domain\. For more information about changing the DNS settings for your domain, see your hosting provider's documentation\.

**To verify a domain**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project that you want to verify the identity in\. 
**Note**  
If you created the project in Mobile Hub, it appears in Amazon Pinpoint in lowercase letters, with all spaces removed, and with "\_MobileHub" added to the end of the name\. For example, if you created a project in Mobile Hub and named it "My New Project", it would appear in Amazon Pinpoint as "mynewproject\_MobileHub"\. If you create a project by using the API, the name isn't changed\.

1. Choose **Settings**\.

1. On the **Channels** tab, under **Choose channels to enable**, choose **Email**\.

1. Select the check box next to **Enable email channel**\.

1. Under **To use email messaging provide either an email address or email domain to start verifying your credentials**, choose **Email domain**\.

1. For **Email domain**, type the domain that you want to verify, and then choose **Verify**\. Make a note of the TXT record values that appear on the **Email domain verification** pop\-up\.

1. Open the DNS configuration page for your email domain, and then add a new TXT record\. In the new TXT record, paste the **Name** and **Value** that you received in the previous step\.
**Note**  
If your DNS provider doesn't allow DNS record names to contain underscores, you can omit *\_amazonses* from the **Name**\.  
Some DNS providers automatically add the domain name to the end of each DNS record name\. To avoid duplication of the domain name, add a period to the end of the domain name in the DNS record\. This step indicates to the provider that the domain name is fully qualified\.

   Amazon Pinpoint automatically detects the TXT record within 72 hours\.

When verifying your domain, consider the following:
+ You can send from any subdomain of the verified domain without specifically verifying the subdomain\. For example, if you verify *example\.com*, you don't need to verify *a\.example\.com* or *a\.b\.example\.com*\. As specified in [RFC 1034](https://tools.ietf.org/html/rfc1034), each DNS label can have up to 63 characters, and the whole domain name must not exceed a total length of 255 characters\.
+ You can verify up to 10,000 identities \(domains and email addresses, in any combination\) per AWS account\.