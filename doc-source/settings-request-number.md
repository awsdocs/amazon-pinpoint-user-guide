# Requesting a number<a name="settings-request-number"></a>

You can request a long code, toll\-free number, or 10DLC phone number on the **SMS and voice** settings page\. Long codes and toll\-free numbers are ready to be used immediately after you purchase them\. To request a 10DLC phone number, you must first register your company and campaign\. After you complete these registrations, you can request a phone number and associate it with a 10DLC campaign\. For more information about 10DLC, see [10DLC](settings-10dlc.md)\.

**Note**  
On this page, you can purchase long codes that you can use to send voice messages\. If you want to purchase long codes for sending SMS messages, or if you want to purchase a long code for a country that isn't listed on this page, you must open a ticket with AWS Support\. For more information about opening a Support ticket to request long codes, see [Requesting dedicated long codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-long-code.md)\.

## Step 1: Request a number<a name="request-a-number-10dlc"></a>

On the **SMS and voice** settings page in the Amazon Pinpoint console you can request a long code, toll\-free number, or 10DLC phone number\.

**To request a number**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. On the **Phone numbers** tab, choose **Request phone number**\. 

1. On the **Define your phone numbers** page, for **Country**, choose the country where your recipients are located\. You can choose only one country at a time, but you can add more countries later if necessary\. For all countries except the United States, the only type of phone numbers that you can purchase on this page are long codes\.
**Note**  
You can't request a specific number or area code\. Phone numbers are assigned based on availability\.

   If you're requesting a number for use in the United States, choose the phone number type\. Depending on the type, you might need to provide additional documentation to support the request\.
   + **Long code** – This is a standard 10\-digit number dedicated only for use with Amazon Pinpoint\. No special documentation is required\.
**Note**  
Unregistered long codes only support voice messages\. SMS is not supported due to U\.S\. telecom carrier requirements\. Choose **10DLC** to request a number using an SMS\-enabled 10\-digit phone number format\.
   + **Toll\-free** – Request a toll\-free number\. Your throughput is limited to 3 messages per second\. Toll\-free number support both SMS and voice messages\. A toll\-free number cannot be used to send messages outside of the U\.S\.
**Note**  
For toll\-free numbers, the default SMS opt\-out and opt\-in keywords are STOP and UNSTOP\. These keywords are carrier\-managed, so no other keywords are supported\. When a user responds with STOP or UNSTOP, the response message is also carrier\-managed and can't be changed\. On the **SMS settings** page of the Amazon Pinpoint console, the opt\-out **Keyword** and **Response message** fields are grayed\-out and can't be edited\.
   + **10DLC** – Only available for sending messages within the United States\. Can support both SMS and voice\. Company and campaign registration approval is required before a number can be purchased\. Requesting a 10DLC number might take up to a week for approval\.

     If you choose **10DLC**, you're prompted to assign the number to an existing 10DLC campaign\. This number can only be used for the associated campaign\. A single 10DLC phone number can't be used for multiple campaigns\. If you request a 10DLC number before you have an active 10DLC campaign, Amazon Pinpoint returns an error message\. If you don't see a campaign listed, verify the campaign status on the **10DLC** tab on **SMS and voice** settings page\. This tab shows a list of current 10DLC campaigns and their statuses\. For information about creating new 10DLC campaigns, see [Registering a 10DLC campaign](settings-register-campaign-10dlc.md)\. 

   For US\-based phone numbers, you also need to choose the channels the number supports\. You can choose to enable the **SMS** channel, the **Voice** channel, or both\.

1. Specify the use case for the phone number\. You can choose one of the following options:
   + **Promotional** – Choose this option for sending marketing messages or messages promoting your business or service\.
   + **Transactional** – Choose this option for sending send time\-sensitive messages, such as password resets or transaction alerts\.

   In some countries and regions, the value that you choose may determine the price that you pay for each message that you send\. Transactional messages are optimized for high deliverability, resulting in a higher cost in many countries\. Promotional messages are optimized for cost\-effectiveness\. For more information about SMS pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing)\.

1. The **Summary** section displays information about the number\. The **Price per month** shows the cost for a single number\.

1. For **Quantity**, choose the quantity of numbers you want to purchase\. You can purchase up to 10 numbers in a single request\. You can purchase additional numbers later\. The **Subtotal** updates to display the total monthly cost for the quantity of phone numbers that you're purchasing\.

1. \(Optional\) If you want to purchase additional phone numbers, choose **Add a country or region**\. 

1. When you're done purchasing phone numbers, choose **Next**\.

## Step 2: Review and submit your number request<a name="review-request"></a>

Before you request a number, use this page to verify whether the information is correct\. Once you submit the request you have to submit a support request to make any changes\.

**To review and submit your number request**

1. The **Review and request** page displays the number request details for each destination country\.

1. The **Total cost** displays the total cost for all numbers for all countries you've chosen\.

1. Choose **Request** if you're ready; otherwise, choose **Previous** to go to back and make any changes\. Once you choose **Request** you can no longer make changes\.

1. Typically, a request for a long code or toll\-free number is approved instantaneously, and a confirmation appears at the top of the page noting that the phone number type was added successfully\. You can now access those numbers on the Phone numbers tab of the **SMS and voice **page\.

   A 10DLC phone number request takes an average of 7\-10 days to process\. During this time the status of the phone number on the Phone numbers tab is **Pending**\. Once your request for the 10DLC number is approved the status changes to **Active**\. You can then associate that number with your 10DLC campaign\.

   If the request encounters any errors, an error message displays at the top of the page\. Common errors might be that there were no long codes available for one of your selected countries or an error occurred while trying to provision a long code\. In some cases, your account might require additional review prior to approving your request\. Should this message appear, you'll need to create a support ticket providing further information about your request\.

1. If your number is enabled for SMS you can further customize it by adding HELP and STOP keywords, or enabling two\-way SMS\. See [Managing SMS and voice settings](settings-sms-managing.md)\. 

1. If you've enabled SMS on the number, test it\. See [Sending a test SMS message](messages-sms.md)\. 