# Email Settings<a name="settings-email"></a>

On the **Email Settings** page, you can enable or disable the email channel for your current project\. When you disable the email channel for a project, you can't send campaign\-based emails from that project\. However, you can still send transactional emails from your Amazon Pinpoint account\. You can also use this page to verify additional email identities\. In Amazon Pinpoint, an identity is an email address or domain that you use to send email\. Every email address that you use as a "From," "Source," "Sender," or "Return\-path" in your emails has to be verified\. Finally, you can use this page to view information about the number of emails you've sent over the past 24 hours\. You can also see how many emails you can send in a 24\-hour period \(your sending quota\), as well as the maximum number of emails you can send per second \(your maximum sending rate\)\.

**Topics**
+ [Enabling and Disabling the Email Channel](#settings-email-enable)
+ [Viewing Details About Email Usage](#settings-email-usage-details)
+ [Verifying Identities](#settings-email-verify-identity)

## Enabling and Disabling the Email Channel<a name="settings-email-enable"></a>

You can change the status of the email channel for the current project\. You have to enable to email channel in each project that you want to send email campaigns from\.

**To enable the email channel for a project**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Choose a project\.

1. In the navigation pane, choose **Email**\.

1. If you haven't yet verified an identity, complete the procedures in the next section\. Otherwise, choose an identity to use, and then choose **Save**\.

The process for disabling the email channel is similar\. When the email channel is disabled, you can't send email campaigns from the project\. However, you can still send transactional email from your Amazon Pinpoint account\.

**To disable the email channel**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Choose a project\.

1. In the navigation pane, choose **Email**\.

1. On the **Identities** tab, choose **Edit**\.

1. Clear the box next to **Enable the email channel for this project**, and then choose **Save**\.

## Viewing Details About Email Usage<a name="settings-email-usage-details"></a>

The **Email Settings** page provides information about your email usage\. On this page, you can see how many emails have been sent from your account in the past 24 hours, and compare that number to the maximum number of emails that your account is allowed to send in a 24\-hour period \(also referred to as your *sending quota*\)\. This page also displays the maximum number of emails you can send per second \(your *sending rate*\), and indicates whether or not your account is in the sandbox\. If your account is in the sandbox, your sending quota and sending rate are set to relatively low values, and you can only send email to verified addresses or domains\.

For more information about requesting an increase to your sending quota or sending rate, or to learn how to have your account removed from the sandbox, see [Managing Email Sending Limits](channels-email-manage-limits.md)\.

For more detailed email reports, see the [Campaigns](analytics-campaigns.md) and [Transactional Messaging](analytics-transactional-email.md) analytics pages\.

## Verifying Identities<a name="settings-email-verify-identity"></a>

An *identity* is an email address or domain that you use to send email\. You can verify up to 10,000 email addresses or domains, in any combination, in each AWS Region\. Every address that you use as the “From,” “Source,” “Sender,” or “Return\-path” address has to be verified\.

### Verifying an Email Address<a name="settings-email-verify-email-address"></a>

If you aren't able to change the DNS settings for your domain, you can verify individual email addresses\. You can also verify individual email addresses if you want to send email from an address on a commercial domain, such as *gmail\.com* or *hotmail\.com*\.

**To verify an email address**

1. Complete the procedure in the [previous section](#settings-email-enable) to enable the email channel\.

1. Under **Identity type**, choose **Email address**, and then choose **Verify a new email address**\.

1. For **Email address**, type the email address that you want to verify, and then choose **Verify email address**\.

1. Check your inbox for an email from *no\-reply\-aws@amazon\.com*\. Click the link in the email to complete the verification process for the email address\.
**Note**  
You should receive the verification email within 5 minutes\. If you don't receive the email, do the following:  
Make sure you typed the address correctly\.
Make sure that the email address you're attempting to verify is able to receive email\. You can test this by using another email address to send a test email\.
Check your junk mail folder\.
Also note that the link in the verification email expires after 24 hours\. To re\-send the verification email, choose **Send the verification email again**\.

### Verifying a Domain<a name="settings-email-verify-domain"></a>

If you plan to send email from a domain that you own, you should verify that domain, rather than verify individual email addresses\. When you verify a domain, you can send email from any address on that domain\. You can also send email from any address on any subdomain of the domain\. For example, if you verify the domain *example\.com*, you can send email from *sender1@example\.com* and *sender2@subdomain\.example\.com*\.

**Important**  
In order to verify a domain, you have to be able to modify the DNS settings for the domain\. The procedures for modifying the DNS settings for your domain vary depending on who your DNS provider is\. See the documentation for your DNS provider for more information\.

**To verify a domain**

1. Complete the procedures in the previous section to enable the email channel\.

1. Under **Identity type**, choose **Domain**, and then choose **Verify a new domain**\.

1. For **Domain**, type the name of the domain that you want to verify\.

1. For **Default sender address**, type an email address to use as the default sending address for the domain\. When you send emails, you can specify a different address\. However, if you don't specify a different address for an email, Amazon Pinpoint sends the email from this default address\.

1. Choose **Verify domain**\.

1. Under **DNS records for domain verification**, copy the three CNAME records\. Alternatively, choose **Download record set** to save the records to your computer\.

1. Log in to the management console for your DNS provider\. Create three new CNAME records that contain the values that you copied in the previous step\. See the next section for links to the documentation for several major DNS providers\.

   It usually takes 24–48 hours for changes to DNS settings to propagate\. As soon as Amazon Pinpoint detects all three of these CNAME records in the DNS configuration of your domain, the verification process is complete\. You can’t send email from a domain until the verification process is complete\.

#### Instructions for Configuring DNS Records for Various Providers<a name="settings-email-verify-domain-providers"></a>

The procedures for updating the DNS records for your domain depend which DNS provider you use\. This section includes links to the documentation for several common DNS providers\. This list isn't exhaustive\. If your provider isn't listed below, you can probably still use it with Amazon Pinpoint\.


| DNS/Hosting Provider Name | Documentation Link | 
| --- | --- | 
| Amazon Route 53 | [Creating Records by Using the Amazon Route 53 Console](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resource-record-sets-creating.html) | 
| GoDaddy | [Add a CNAME record](https://www.godaddy.com/help/add-a-cname-record-19236) \(external link\) | 
| Dreamhost | [How do I add custom DNS records?](https://help.dreamhost.com/hc/en-us/articles/215414867-How-do-I-add-custom-DNS-records-) \(external link\) | 
| Cloudflare | [How do I add a CNAME record?](https://support.cloudflare.com/hc/en-us/articles/200169046-How-do-I-add-a-CNAME-record-) \(external link\) | 
| HostGator | [Manage DNS Records with HostGator/eNom](https://support.hostgator.com/articles/hosting-guide/lets-get-started/dns-name-servers/manage-dns-records-with-hostgatorenom) \(external link\) | 
| Namecheap | [How do I add TXT/SPF/DKIM/DMARC records for my domain? ](https://www.namecheap.com/support/knowledgebase/article.aspx/317/2237/how-do-i-add-txtspfdkimdmarc-records-for-my-domain) \(external link\) | 
| Names\.co\.uk | [Changing your domains DNS Settings](https://www.names.co.uk/support/1156-changing_your_domains_dns_settings.html) \(external link\) | 
| Wix | [Adding or Updating CNAME Records in Your Wix Account](https://support.wix.com/en/article/adding-or-updating-cname-records-in-your-wix-account) \(external link\) | 

**Note**  
This list contains links to the documentation for several common DNS providers\. It isn't a complete list of providers\. Inclusion on this list isn’t an endorsement or recommendation of any company’s products or services\.

#### Domain Registration Tips and Troubleshooting<a name="settings-email-verify-domain-troubleshooting"></a>

If you completed the preceding steps, but your domain still isn’t verified after 72 hours, check the following:
+ Make sure that you entered the values for the DNS records in the correct fields\. Some DNS providers refer to the **Name/host** field as the *Host* or *Hostname*\. Some providers label the **Value** field as the *Points to* or *Result*\.
+ Make sure that your provider didn’t automatically append your domain name to the end of the value in the name column\. Some providers append the domain name without providing any indication that they’ve done so\. If your provider does append the domain name onto the end of the value, remove the domain name from the end of the value in the Name column\.
+ The underscore character \(\_\) is required in the name of each record\. If your provider doesn't allow you to include underscores in DNS record names, contact the provider's customer support department for additional assistance\.
+ The validation records that you have to add to the DNS configuration for your domain are different for each AWS Region\. If you want to use a domain to send email from multiple regions using Amazon Pinpoint, you have to validate the domain in each of those regions\.