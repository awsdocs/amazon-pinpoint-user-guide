# Email Address or Domain Verification<a name="channels-email-manage-verify"></a>

To confirm that you own an email address or domain, and to prevent others from using it, you must verify the address or domain\.

## Email Address Verification<a name="w3ab1c14c16c15c12b5"></a>

When verifying your email address, consider the following:

+ You can verify up to 10,000 identities \(domains and email addresses, in any combination\) per AWS account\. 

+ You can apply labels to verified email addresses by adding a plus sign \(\+\) and a string of text after the recipient's user name, and before the @ sign\. For example, to add *label1* to the address *user@example\.com*, use the modified address *user\+label1@example\.com*\. You can use an unlimited number of labels on each verified address\. You can use labels in the From and Return\-Path fields to implement Variable Envelope Return Path \(VERP\)\. For more information about VERP, see [http://en.wikipedia.org/wiki/Variable_envelope_return_path](http://en.wikipedia.org/wiki/Variable_envelope_return_path)\.
**Note**  
When you verify an unlabeled address, you are verifying all addresses that could be formed by adding a label to the address\. However, if you verify a labeled address, you cannot use other labels with that address\.

## Domain Verification<a name="w3ab1c14c16c15c12b7"></a>

Before you can use Amazon Pinpoint to send emails from a domain, verify your domain to confirm that you own it and to prevent others from using it\. When you verify an entire domain, you are verifying all email addresses from that domain, so you don't need to verify email addresses from that domain individually\. For example, if you verify the domain example\.com, you can send email from user1@example\.com, user2@example\.com, or any other user at example\.com\.

When verifying your domain, consider the following:

+ You can send from any subdomain of the verified domain without specifically verifying the subdomain\. For example, if you verify example\.com, you do not need to verify a\.example\.com or a\.b\.example\.com\. As specified in RFC 1034, each DNS label can have up to 63 characters and the whole domain name must not exceed a total length of 255 characters\.

+ You can verify as many as 10,000 identities \(domains and email addresses, in any combination\) per AWS account\.