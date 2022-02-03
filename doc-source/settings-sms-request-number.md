# Requesting a number<a name="settings-sms-request-number"></a>

On the **SMS and voice** settings page, you can request phone numbers for use in various countries\. For the United States, you can purchase SMS\-enabled 10DLC and toll\-free numbers, as well as voice\-enabled long codes\. For other countries, you can purchase voice\-enabled long codes\.

If you want to purchase a phone number for a country that isn't listed on this page, or if you want an SMS\-enabled phone number, you must open a case with AWS Support\. For more information about opening an AWS Support case to request dedicated SMS long codes, see [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\. For more information about opening an AWS Support case to request dedicated SMS long codes, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\.

## Requesting a phone number using the Amazon Pinpoint console<a name="settings-sms-request-number-console"></a>

On the **SMS and voice** settings page in the Amazon Pinpoint console you can request a long code, toll\-free number, or 10DLC phone number\.

**To request a number**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. On the **Phone numbers** tab, choose **Request phone number**\. 

1. On the **Define your phone numbers** page, for **Country**, choose the country in which you want to purchase a phone number\. You can choose only one country at a time, but you can choose additional countries later if necessary\.
**Note**  
You can't request specific numbers or area codes\. Phone numbers are assigned based on availability\.

1. If you're requesting a number for use in the United States, choose the phone number type\. Depending on the type, you might need to provide additional documentation to support the request\. You can choose from the following types of phone numbers:
   + **Long code** – A standard 10\-digit number dedicated only for use with Amazon Pinpoint\. No special documentation is required\.
**Note**  
Unregistered long codes can only be used to send voice messages\. If you want a phone number for sending SMS messages, complete the steps in [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\.
   + **Toll\-free** – \(US only\) A toll\-free number that begins with 888, 877, 866, 855, 844, or 833\. Throughput for toll\-free numbers is limited to 3 message parts per second\. Toll\-free numbers support both SMS and voice messages\. They can't be used to send messages to recipients outside of the US\.
**Note**  
For toll\-free numbers, the default SMS opt\-out and opt\-in keywords are STOP and UNSTOP\. These keywords are carrier\-managed, so no other keywords are supported\. When a user responds with STOP or UNSTOP, the response message is also carrier\-managed and can't be changed\. On the **SMS settings** page of the Amazon Pinpoint console, the opt\-out **Keyword** and **Response message** fields are inactive and can't be edited\.
   + **10DLC** – \(US only\) A 10\-digit number that requires a registration process before it can be used\. These numbers can support both SMS and voice messages\. Associating a phone number with a 10DLC campaign can take 1–2 weeks to complete\.

     To request a 10DLC phone number, you must first register your company and campaign\. After you complete these registrations, you can request a phone number and associate it with a 10DLC campaign\. For more information about 10DLC, see [10DLC](settings-sms-10dlc.md)\.

     If you choose **10DLC**, you're prompted to assign the number to a 10DLC campaign\. This number can only be used for the associated campaign\. A single phone number can't be associated with multiple 10DLC campaigns\. If you request a 10DLC number before you have an active 10DLC campaign, Amazon Pinpoint returns an error message\. If you don't see a campaign listed, verify the campaign status on the **10DLC** tab on **SMS and voice** settings page\.

   For US\-based 10DLC and toll\-free numbers, you must also choose the channels the number supports\. You can choose to enable the **SMS** channel, the **Voice** channel, or both\.

1. Choose a message type for the phone number\. You can choose one of the following options:
   + **Promotional** – Choose this option for sending marketing messages or messages promoting your business or service\.
   + **Transactional** – Choose this option for sending time\-sensitive messages, such as password resets or transaction alerts\.
**Note**  
If you plan to use several different phone numbers with a single 10DLC campaign, you must choose a single message type to use for that campaign\. You can't combine promotional and transactional phone numbers in a single 10DLC campaign\. For example, if you associate a promotional phone number to a 10DLC campaign, and later decide that you want to associate more numbers with that campaign, you won't be able to associate transactional phone numbers with it\.

   In some countries, the value that you choose may determine the price that you pay for each message that you send\. Transactional messages are optimized for high deliverability, resulting in a higher cost in many countries\. Promotional messages are optimized for cost\-effectiveness\. For more information about SMS pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing)\.

1. The **Summary** section displays information about the number\. The **Price per month** shows the cost for a single number\.

   For **Quantity**, choose the quantity of numbers that you want to purchase\. You can purchase up to 10 numbers in a single request\. You can purchase additional numbers later\. The **Subtotal** updates to display the total monthly cost for the quantity of phone numbers that you're purchasing\.

1. \(Optional\) If you want to purchase additional phone numbers, choose **Add a country or region**\. 

1. When you're done purchasing phone numbers, choose **Next**\.

1. On the **Review and request** page, confirm the phone number details\.

   If you're ready to complete the purchase, choose **Request**\. Otherwise, choose **Previous** to go to back and make any changes\.

Requests for long codes and toll\-free numbers are usually approved immediately\. If your request is approved, you can access your new phone numbers on the **Phone numbers** tab of the **SMS and voice ** settings page\.

A 10DLC phone number request takes about 7–10 days to process\. During this time the status of the phone number on the **Phone numbers** tab is **Pending**\. Once your request for the 10DLC number is approved the status changes to **Active**\. You can then associate that number with your 10DLC campaign\.

If there are any problems with your request, an error message appears at the top of the page\. An error can occur if there were no long codes available for one of the countries that you selected, for example\. In some cases, your account might require additional review prior to approving your request\. If this message appears, you need to create a support ticket providing further information about your request\.