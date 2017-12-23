# Managing the Amazon Pinpoint SMS Channel<a name="channels-sms-manage"></a>

Use the Amazon Pinpoint console to enable the SMS channel and manage SMS settings, such as how your deliveries are optimized \(for cost or for reliable delivery\) and your monthly spending limit\.

To update your SMS settings, use the **Account settings** page\. For more information, see [Managing Account Settings in Amazon Pinpoint](settings-account.md)\.

Before you can use Amazon Pinpoint to send SMS messages, you must enable the SMS channel for one or more projects\.

**To enable the SMS channel for a project**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project for which you want to enable the SMS channel\.

1. In the navigation menu, choose **Settings**\.

1. On the **Settings** page, choose **Channels**, and then choose **SMS**\.

1. Choose **Enable SMS channel**\.

1. Choose **Save**\.

## SMS Opt Out<a name="channels-sms-manage-optout"></a>

Where required by local laws and regulations \(such as in the US and Canada\), SMS recipients can use their devices to opt out by replying to the message with any of the following: 

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

To opt out, the recipient must reply to the same long code or short code that Amazon Pinpoint used to deliver the message\. After opting out, the recipient no longer receives SMS messages from your AWS account\.