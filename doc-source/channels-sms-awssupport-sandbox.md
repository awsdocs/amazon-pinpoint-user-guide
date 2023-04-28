# Moving from the Amazon Pinpoint SMS sandbox to production<a name="channels-sms-awssupport-sandbox"></a>

After fully testing your SMS environment in the SMS sandbox, you can choose to move to production\. To do so, create an AWS Support case for a **Service limit increase** request\. 

Alternatively, you can request production access from the sandbox environment\. To do so, choose **Request production access** under ** Account tier** on the **SMS and voice** page\.

**Note**  
If your account is in multiple regions, you must submit a support request for each region\.

**To move from the SMS sandbox**

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
   + For **Resource Type**, choose** General Limits**\.
   + For the Limit, choose **SMS Production Access**\.
   + For **New limit value**, enter 1\.

1. Under **Case description**, for **Use case description**, enter any relevant details about this request\.

1. \(Optional\) If you want to submit any further requests, choose **Add another request**\. For the required information, see the other sections within [Requesting support for SMS messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

1. Under **Contact options**, for **Preferred contact language**, choose whether you want to receive communications for this case in **English** or **Japanese**\.

1. When you finish, choose **Submit**\.

After we receive your request, we provide an initial response within 24 hours\. We might contact you to request additional information\.

## <a name="channels-sms-awssupport-sender-id-settings"></a>