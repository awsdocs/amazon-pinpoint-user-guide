# Opting out<a name="channels-sms-limitations-opt-out"></a>

You might have a combination of numbers on your account that are AWS\-managed or self\-managed\. Opt\-out options are controlled on the **SMS settings** page of the Amazon Pinpoint console\. Here you can set any of your number to self\-manage your own process outside of Amazon Pinpoint\. See [Self\-managed opt\-outs](settings-sms-managing.md#settings-account-sms-self-managed-opt-out) for the steps to self\-manage opt outs\.

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
For toll\-free numbers, opt\-out is carrier\-managed\. The only supported opt\-out keyword for a toll\-free number is STOP\. You will be unable to change or edit this keyword\. This is only applicable for the U\.S\.