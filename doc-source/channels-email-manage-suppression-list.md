# Managing the email suppression list<a name="channels-email-manage-suppression-list"></a>

When you send an email using Amazon Pinpoint and that email bounces or results in a spam complaint, the recipient’s email address is automatically added to a suppression list\. This suppression list applies only to your AWS account\. If an email address is on the suppression list for your account, and you try to send an email to that account, Amazon Pinpoint accepts the message, but doesn’t attempt to send it\.

You can manage the settings for the suppression list in the Amazon SES console\. This section contains information about changing these settings\.

## Changing the suppression list settings<a name="channels-email-manage-suppression-list-settings"></a>

You can configure how the suppression list behaves by changing the actions that cause an email address to be added to the suppression list\. Addresses can be automatically added to the suppression list when they produce a bounce event, a complaint, or both\. You can also turn off the suppression list altogether\.

**To change the suppression list settings**

1. Open the Amazon SES console at [https://console\.aws\.amazon\.com/sesv2](https://console.aws.amazon.com/sesv2)\.

1. Under **Configuration**, choose **Suppression list**\.

1. In the **Account\-level settings** section, choose **Edit**\.

1. Under **Suppression list settings**, choose the types of events that cause an address to be added to the suppression list\. Alternatively, if you want to turn off the account\-level suppression list, clear the **Enabled** box\.

1. When you finish, choose **Save changes**\.

## Viewing a list of addresses that are on the suppression list<a name="channels-email-manage-suppression-list-view"></a>

In the Amazon SES console, you can view a list of all of the addresses that are on the suppression list for your account\. You can also view the reason that a particular address was added to the suppression list, and the date on which it was added\.

For more information, see [Viewing a list of addresses that are on the account\-level suppression list ](https://docs.aws.amazon.com/ses/latest/dg/sending-email-suppression-list.html#sending-email-suppression-list-view-entries) in the *Amazon Simple Email Service Developer Guide*\.

## Removing addresses from the suppression list<a name="channels-email-manage-suppression-list-removing"></a>

You can remove addresses from the suppression list individually or in bulk\. This feature is helpful when you want to opt customers in upon request, or when you’re sending test emails to an address that you know is valid\.

For information about removing addresses individually, see [Removing an email address from the account\-level suppression list](https://docs.aws.amazon.com/ses/latest/dg/sending-email-suppression-list.html#sending-email-suppression-list-manual-delete) in the *Amazon Simple Email Service Developer Guide*\.

For information about removing addresses in bulk, see [Removing email addresses in bulk from the account\-level suppression list](https://docs.aws.amazon.com/ses/latest/dg/sending-email-suppression-list.html#sending-email-suppression-list-manual-delete-bulk) in the *Amazon Simple Email Service Developer Guide*\.

## Adding addresses to the suppression list<a name="channels-email-manage-suppression-list-adding"></a>

You can also add addresses from the suppression list individually or in bulk\. This feature is helpful when you want to migrate existing opt\-in preferences to Amazon Pinpoint, or when you want to opt customers out upon request\.

For information about adding addresses individually, see [Manually adding individual email addresses to the account\-level suppression list](https://docs.aws.amazon.com/ses/latest/dg/sending-email-suppression-list.html#sending-email-suppression-list-manual-add) in the *Amazon Simple Email Service Developer Guide*\.

For information about adding addresses in bulk, see [Adding email addresses in bulk to the account\-level suppression list](https://docs.aws.amazon.com/ses/latest/dg/sending-email-suppression-list.html#sending-email-suppression-list-manual-add-bulk) in the *Amazon Simple Email Service Developer Guide*\.