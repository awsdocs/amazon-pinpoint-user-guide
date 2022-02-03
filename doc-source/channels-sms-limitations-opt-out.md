# Opting out<a name="channels-sms-limitations-opt-out"></a>

Opt\-out settings are controlled on the **SMS settings** page of the Amazon Pinpoint console\. By default, opt\-outs are managed by AWS automatically\. You can choose to disable this automatic opt\-out handling by enabling self\-managed opt\-outs\. Your account can contain both numbers for which opt\-outs are managed by AWS and numbers for which opt\-outs are self\-managed\. For more information about enabling self\-managed opt\-outs, see [Self\-managed opt\-outs](settings-sms-managing.md#settings-account-sms-self-managed-opt-out)\.

## Supported opt\-out keywords<a name="settings-sms-self-opt-out-terms"></a>

Where required by local laws and regulations \(such as in the US and Canada\), SMS recipients can use their devices to opt out by replying to the message with any of the following: 
+ ARRET
+ CANCEL
+ END
+ OPT\-OUT
+ OPTOUT
+ QUIT
+ REMOVE
+ STOP
+ TD
+ UNSUBSCRIBE

To opt out, the recipient must reply to the same long code or short code that Amazon Pinpoint used to deliver the message\. After opting out, the recipient no longer receives SMS messages from your AWS account\.

**Note**  
For US toll\-free numbers, opt\-outs are managed at the carrier level\. The only supported opt\-out keyword for a US toll\-free number is STOP\. You can't add additional opt\-out keywords, or change the response message that your recipients get when they opt\-out\.