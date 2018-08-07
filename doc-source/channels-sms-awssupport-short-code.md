# Requesting Dedicated Short Codes for SMS Messaging with Amazon Pinpoint<a name="channels-sms-awssupport-short-code"></a>

A short code is a five\-digit or six\-digit number that's meant for high\-volume SMS messaging\. Short codes are often used for application\-to\-person \(A2P\) messaging, two\-factor authentication \(2FA\), and marketing\.

To use short codes in multiple countries, request a separate short code for each country\. You can use a short code only to message the same country in which it was approved by wireless carriers\.

For information about short code pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/)\.

**Important**  
If you're new to SMS messaging with Amazon Pinpoint, request a monthly SMS spend threshold that meets the expected demands of your SMS use case\. By default, your monthly spend threshold is $1\.00 USD\. You can request to increase your spend threshold in the same support case that includes your request for a short code\. Or, you can use a separate case\. For more information, see [Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

After receiving your request, AWS works with the wireless carriers to provision your short code on your behalf\. This provisioning process typically takes 8–12 weeks to complete, but some carriers may require additional time to complete the process\.

To request a dedicated short code, complete the following steps\.

## Step 1: Open an Amazon Pinpoint SMS Case<a name="channels-sms-awssupport-short-code-open"></a>

Open a case with AWS Support by completing the following steps\.

1. Sign in to the AWS Management Console, and go to the [AWS Support Center](https://console.aws.amazon.com/support/home#/)\.

1. Choose **Create case**\.

1. For **Regarding**, choose **Service Limit Increase**\.

1. For **Limit Type**, choose **Pinpoint SMS**\.

## Step 2: Specify Your Request<a name="channels-sms-awssupport-short-code-request"></a>

Tell AWS Support that you're requesting a dedicated short code by completing the following steps\.

1. For **Resource Type**, choose **Dedicated SMS Short Codes**\.

1. For **Limit**, choose the type of message that you'll send with your short code:
   + **One\-time Passwords/Two\-Factor Authentication** – Messages that provide passwords to authenticate with your website or application\.
   + **Promotional/Marketing** – Noncritical messages that promote your business or service, such as special offers or announcements\.
   + **Transactional** – Important informational messages that support customer transactions, such as order confirmations or transaction alerts\. Transactional messages must not contain promotional content\.

1. For **New limit value**, specify the number of short codes that you're requesting\. Typically, this value is **1**\.

1. \(Optional\) If you want to include multiple requests in this support case, choose **Add another request**\. Then, specify the type of request\.

   If you include multiple requests, provide the required information for each\. For the required information, see the other sections within [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.

## Step 3: Describe Your SMS Use Case<a name="channels-sms-awssupport-short-code-usecase-"></a>

Describe how you'll use your dedicated short code by completing the following steps\.

1. For **Link to site or app which will be sending SMS**, identify the website or application where your audience members will opt in to receive your SMS messages\.

1. For **Type of messages**, choose the type of message that you'll send using your short code: **Transactional**, **Promotional**, or **One Time Passwords**\.

1. For **Targeted Countries**, specify the country that you'll send SMS messages to with your short code\.

1. For **Use Case Description**, provide the following details, which AWS requires to register your short code with wireless carriers:

**Company information:**
   + Company name\.
   + Company mailing address\.
   + Name and phone number for the primary contact for your request\.
   + Email address and toll\-free number for support at your company\.
   + Company tax ID\.
   + Name of your product or service\.

**User sign\-up process:**
   + Company website, or the website that your customers will sign up on to receive messages from your short code\.
   + How users will sign up to receive messages from your short code\. Specify one or more of the following options:
     + **Text messages**\.
     + **Website**\.
     + **Mobile app**\.
     + **Other**\. If other, explain\.
   + The text for the option to sign up for messages on your website, app, or elsewhere\.
   + The sequence of messages that you'll use for double opt\-in\. Provide:

     1. The SMS message that you'll send when a user signs up\. This message asks for the user's consent for recurring messages\. For example:

        *ExampleCorp: Reply YES to receive account transaction alerts\. Msg&data rates may apply\.*

     1. The opt\-in response that you expect from the user\. This is typically a keyword, such as *YES*\.

     1. The confirmation message that you'll send in response\. For example:

        *You are now registered for account alerts from ExampleCorp\. Msg&data rates may apply\. Txt STOP to cancel or HELP for info\.*

**The purpose of your messages:**
   + The purpose of the messages that you'll send with your short code\. Specify one of the following options:
     + **Promotions and marketing**\.
     + **Location\-based services**\.
     + **Notifications**\.
     + **Information on demand**\.
     + **Group chat**\.
     + **Two\-factor authentication \(2FA\)**\.
     + **Polling and surveys**\.
     + **Sweepstakes or contests**\.
     + **Other**\. If other, explain\.
   + Whether you'll use your short code for promotional or marketing messages for a business other than your own\.

**Message content:**
   + The message that you'll send when customers opt in to your messages by sending you a specific keyword\. Be careful when you specify this keyword and message—it may take several weeks to change this message\. When we create your short code, we register the keyword and message with the mobile phone carriers in the country where you use the short code\. Your message may resemble the following example:

     *Welcome to *ProductName* alerts\! Msg&data rates apply\. *2* msgs per month\. Reply HELP for help, STOP to cancel\.*
   + The message that you'll send in response to the *HELP* keyword\. This message must include customer support contact information\. For example:

     **ProductName* Alerts: Help at *example\.com/help* or *\(800\) 555\-0199*\. Msg&data rates apply\. *2* msgs per month\. Reply STOP to cancel\.*
   + The message that you'll send in response to the *STOP* keyword\. This message must confirm that messages are no longer sent to the user\. For example:

     *You are unsubscribed from *ProductName* Alerts\. No more messages will be sent\. Reply HELP for help or *\(800\) 555\-0199*\.*
   + The text you'll use for a periodic reminder that the user is subscribed to your messages\. For example:

     *Reminder: You are subscribed to account alerts from ExampleCorp\. Msg&data rates may apply\. Txt STOP to cancel or HELP for info\.*
   + An example of each type of message that you'll send with your short code\. Provide at least 3 examples, but if you are sending more than 3 types of messages, provide examples for all of them\.

1. When you finish, choose **Submit**\.

## Step 4: Update Your SMS Settings in the Amazon Pinpoint Console<a name="channels-sms-awssupport-short-code-settings"></a>

After AWS notifies you that your short code is registered with the wireless carriers, complete the following steps\.

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose **Account settings**\.

1. Under **Number settings**, choose the short code that AWS assigned to your account\.

1. Under **Default keywords**, verify that the messages for the *HELP* and *STOP* keywords match the values you provided to AWS Support\.

1. Under **Registered keyword**, verify that the opt\-in keyword and message match the values you provided to AWS Support\.

1. \(Optional\) If you want to specify additional keyword responses, or if you want to process inbound messages outside of Amazon Pinpoint, configure two\-way SMS settings\. For more information, see [Two\-Way SMS Settings](settings-account.md#settings-account-sms-number-2way)\.

1. When you finish making your changes, choose **Save**\.

## Next Steps<a name="channels-sms-awssupport-short-code-next"></a>

You've registered a short code with wireless carriers and reviewed your settings in the Amazon Pinpoint console\. Now you can use Amazon Pinpoint to send SMS messages with your short code as the origination number\.

To engage an audience segment with an SMS campaign, see [Amazon Pinpoint Campaigns](campaigns.md)\.

To send an SMS message directly to a limited audience without creating a campaign, see [Direct Messages with Amazon Pinpoint](messages.md)\.