# Managing configuration sets<a name="channels-email-manage-configuration-sets"></a>

Configuration sets are groups of rules that you can apply to the emails that you send\. When you apply a configuration set to an email, all of the rules in that configuration set are applied to the email\. For example, you can configure a configuration set so that emails are only sent using a group of IP addresses \(known as an *IP pool*\) that you specify\.

You can use configuration sets in both Amazon Pinpoint and Amazon Simple Email Service \(Amazon SES\)\. Configuration sets rules that you configure in Amazon SES are also applied to email messages that you send using Amazon Pinpoint\.

You can view a list of configuration sets for your account in the Amazon Pinpoint console\. However, you must use Amazon SES to setup and manage configuration sets\. For more information about creating configuration sets, see [Creating configuration sets](https://docs.aws.amazon.com/ses/latest/dg/creating-configuration-sets.html) in the *Amazon Simple Email Service Developer Guide*\.

## Viewing a list of configuration sets<a name="channels-email-manage-configuration-sets-viewing"></a>

**To view a list of configuration sets in the Amazon Pinpoint console**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **Email**, choose **Configuration sets**\.

## Applying a configuration set to an email identity<a name="channels-email-manage-configuration-sets-applying"></a>

To use configuration sets with Amazon Pinpoint, you have to specify a default configuration set for the email identity \(that is, the email address or domain\) that you use to send email through Amazon Pinpoint\. You can set up default configuration sets in the Amazon SES console\.

When you set a default configuration set for an identity, all emails that you send through that identity are sent using that configuration set, unless you specify a different one\. Currently, Amazon Pinpoint doesn't allow you to specify a different configuration set, so the only way to use configuration sets is to specify a default configuration set\.

**Note**  
The following procedure assumes that you've already verified an identity\. Identities that you verify in Amazon SES are available in Amazon Pinpoint, and vice\-versa\. For more information, see [Verifying email identities](channels-email-manage-verify.md)\.  
This procedure also assumes that you've created a configuration set\.

**To specify a default configuration set for an identity**

1. Open the Amazon SES console at [https://console\.aws\.amazon\.com/ses/](https://console.aws.amazon.com/ses/)\.

1. In the navigation pane, under **Configuration**, choose **Verified identities**\.

1. In the list of identities, choose the identity that you want to specify a default configuration set for\.

1. On the **Configuration set** tab, choose **Edit**\.

1. Select **Assign a default configuration set**\.

1. For **Default configuration set**, choose the configuration set that you want to use for this identity, and then choose **Save changes**\.