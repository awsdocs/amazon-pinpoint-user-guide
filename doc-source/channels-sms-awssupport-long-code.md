# Requesting dedicated long codes for SMS messaging with Amazon Pinpoint<a name="channels-sms-awssupport-long-code"></a>

A long code \(also referred to as a long virtual number, or LVN\) is a standard phone number that contains up to 12 digits, depending on the country that it's based in\. Long codes are typically meant for low\-volume, person\-to\-person communication\. In some countries, you can use long codes for sending test messages, or for sending low volumes of messages to your customers\. In other countries, including the United States, senders are prohibited from using long codes to send Application\-to\-Person \(A2P\) messages, which includes the messages that you send from Amazon Pinpoint\.

**Note**  
If you're new to SMS messaging with Amazon Pinpoint, you should also request a monthly SMS spending threshold that meets the expected demands of your SMS use case\. By default, your monthly spending threshold is $1\.00 \(USD\)\. For more information, see [Requesting increases to your monthly SMS spending quota for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

## Requesting a long code<a name="request-number-row"></a>

You can request a long code by opening a case in the AWS Support Center\.

**Important**  
If you want to send messages to recipients in the United States, you must use either [a short code](channels-sms-awssupport-short-code.md), a [10DLC phone number](settings-sms-10dlc.md), or a [toll\-free number](settings-sms-request-number.md)\. If you complete the following steps and request a long code for the United States, your request will be rejected\.

**To request a dedicated long code by opening a case in the AWS Support Center**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Support** menu, choose **Support Center**\.

1. On the **Your support cases** pane, choose **Create case**\.

1. Choose the **Looking for service limit increases?** link\.

1. Choose **Service limit increase**, then complete the following:
   + For **Limit type**, choose **Pinpoint SMS**\.
   + \(Optional\) For **Provide a link to the site or app which will be sending SMS messages**, provide information about the website, application, or service that will send SMS messages\.
   + \(Optional\) For **What type of messages do you plan to send**, choose the type of message that you plan to send using your long code:
     + **One Time Password** – Messages that provide passwords that your customers use to authenticate with your website or application\.
     + **Promotional** – Noncritical messages that promote your business or service, such as special offers or announcements\.
     + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or account alerts\. Transactional messages must not contain promotional or marketing content\.
   + \(Optional\) For **Which AWS Region will you be sending messages from**, choose the region that you'll be sending messages from\.
   + \(Optional\) For **Which countries do you plan to send messages to**, enter the country or region that you want to purchase short codes in\.
   + \(Optional\) In the **How do your customers opt to receive messages from you**, provide details about your opt\-in process\.
   + \(Optional\) In the **Please provide the message template that you plan to use to send messages to your customers** field, include the template that you will be using\.

1. Under **Requests**, complete the following sections:
   + For the **Region**, choose the Region from which you'll be sending messages\. 
**Note**  
The Region is required in the **Requests** section\. Even if you provided this information in the **Case details** section you must also include it here\.
   + For **Resource Type**, choose** Dedicated SMS Long Codes**\.
   + For **New limit value**, enter the number of long codes that you want to purchase\.

1. Under **Case description**, for **Use case description**, provide details about your use case\.

1. \(Optional\) If you want to submit any further requests, choose **Add another request**\. For the required information, see the other sections within [Requesting support for SMS messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

1. Under **Contact options**, for **Preferred contact language**, choose whether you want to receive communications for this case in **English** or **Japanese**\.

1. When you finish, choose **Submit**\.

After we receive your request, we provide an initial response within 24 hours\. We might contact you to request additional information\. Once approved, you can add keywords and response messages to your long code\. See [Managing SMS and voice settings in Amazon Pinpoint](settings-sms-managing.md)\. 

If we're able to provide you with a long code, we send you information about the costs associated with obtaining it\. We also provide an estimate of the amount of time that's required to provision the long code\. In many countries, we can provide you with a dedicated long code within 24 hours\. However, in some countries and regions, it can take several weeks to obtain a dedicated long code for the SMS channel\.

In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. We might not be able to grant your request if your use case doesn't align with our policies\.

## Next steps<a name="register-campaign-10dlc"></a>

You've registered a long code and updated your settings in the Amazon Pinpoint console\. Now you can use Amazon Pinpoint to send SMS messages with your long code as the origination number\.

To engage an audience segment with an SMS campaign, see [Amazon Pinpoint campaigns](campaigns.md)\.



To send an SMS message directly to a limited audience without creating a campaign, see [Sending a test SMS message](messages-sms.md)\.