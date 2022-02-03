# Managing the Amazon Pinpoint SMS channel<a name="channels-sms-manage"></a>

You can manage SMS settings, such as your default message type \(transactional or promotional\) and your monthly spending quota, directly in the Amazon Pinpoint console\.

## Updating SMS channel settings<a name="channels-sms-manage-settings"></a>

You can change several SMS\-related settings\. Most of these settings apply to your entire AWS account, but some apply to specific projects\.

**To edit SMS settings for a project**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that you want to edit SMS settings for\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. In the **SMS settings** section, choose **Edit**\.

1. Change the SMS settings for your project as needed\. You can change the following settings:

     
**Enable the SMS channel for this project**  
Select this option to enable or disable the SMS channel for the project\. If this setting is not enabled, you can't send SMS messages from this project\. This setting only applies to the current project\.  
**Default message type**  
Choose the category of SMS messages that you plan to send from this account\. If you send account\-related messages or time\-sensitive messages such as one\-time passcodes, choose **Transactional**\. If you plan to send messages that contain marketing material or other promotional content, choose **Promotional**\. This setting applies to your entire AWS account\.  
**Account spending limit**  
The maximum amount of money \(in US Dollars\) that you can spend sending messages each month\. You can use this setting to ensure that your SMS sending doesn't exceed your budget, or as a way to prevent unexpected increases in spending\. The price to send an SMS message varies depending on the destination country for that message\. For current prices, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/#SMS_text_messages)\. This setting applies to your entire AWS account\.  
**Account sender ID**  
The alphabetic sender ID that you want to use when you send messages from your account\. This setting applies to your entire AWS account\.  
Alphabetic sender IDs are only supported in certain countries\. If you don't send messages to countries where sender ID is supported by the mobile carriers in that country, you don't need to specify anything in this field\. Sender IDs aren't supported in common messaging destinations such as the United States, Canada, and Brazil\.  
Additionally, some countries require sender IDs to be pre\-registered with government agencies or industry organizations\.  
For a list of countries that support alphabetic sender IDs, see [Country capabilities and limitations for SMS with Amazon Pinpoint](channels-sms-country-capabilities.md)\.

1. When you finish, choose **Save changes**\.

## SMS opt out<a name="channels-sms-manage-optout"></a>

Where required by local laws and regulations, SMS recipients can use their devices to opt out by replying to the message with any of the following: 
+ ARRET \(French\)
+ CANCEL
+ END
+ OPT\-OUT
+ OPTOUT
+ QUIT
+ REMOVE
+ STOP
+ TD
+ UNSUBSCRIBE

To opt out, the recipient must reply to the same long code or short code that Amazon Pinpoint used to deliver the message\. After opting out, the recipient no longer receives SMS messages from your AWS account\. You can change this behavior by enabling the self\-managed opt\-out feature\. For more information, see [Self\-managed opt\-outs](settings-sms-managing.md#settings-account-sms-self-managed-opt-out)\.

**Note**  
For toll\-free numbers in the United States, opt\-outs are managed downstream from AWS\. For this reason, the only supported opt\-out keyword for US toll\-free numbers is STOP\. You can't specify additional opt\-out keywords, and you can't modify the response that is sent when this keyword is received\.