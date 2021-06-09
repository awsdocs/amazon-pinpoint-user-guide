# Managing the Amazon Pinpoint voice channel<a name="channels-voice-manage"></a>

You can use the Amazon Pinpoint console to enable the voice channel for a project and to manage settings that apply to the voice channel for your Amazon Pinpoint account\. For example, you can request production access for your account, or request dedicated phone numbers for sending voice messages\.

**Topics**
+ [Enabling the voice channel](#channels-voice-manage-enable)
+ [Requesting production access](#channels-voice-manage-sandbox)
+ [Requesting phone numbers](#channels-voice-manage-request-phone-numbers)
+ [Relinquishing phone numbers](#channels-voice-manage-remove-phone-numbers)

## Enabling the voice channel<a name="channels-voice-manage-enable"></a>

Before you can use Amazon Pinpoint to send voice messages, you have to enable the voice channel for one or more projects\. To learn how to create a new project and enable the voice channel for it, see [Setting up the Amazon Pinpoint voice channel](channels-voice-setup.md)\. To enable the voice channel for an existing project, complete the following steps\.

Note that the settings that you choose for the voice channel also apply to the SMS channel for the project\. If you want to send both voice and SMS messages from the project, choose settings that support your goals for both channels\. To learn more, see [Amazon Pinpoint SMS channel](channels-sms.md)\.

**To enable the voice channel for an existing project**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that you want to enable the voice channel for\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\.

1. On the **SMS and voice** page, next to **SMS settings**, choose **Edit**\.

1. Select **Enable the SMS channel for this project**\.

1. Choose **Save changes**\.

1. On the **SMS and voice** page, under **Number settings**, refer to the table to determine whether any phone numbers that are already associated with your account can be used to send voice messages\. If there are, the **Voice** column displays **Enabled** next to each phone number that you can use to send voice messages\. If there aren't, [request a phone number for the voice channel](#channels-voice-manage-request-phone-numbers)\.

## Requesting production access<a name="channels-voice-manage-sandbox"></a>

When you first start using the voice channel, your account is in the *sandbox*\. 

To remove these quotas from your account, you can request to have your account removed from the sandbox\. When your account is removed from the sandbox, it has *production access*\.

**Note**  
Before you request production access, you must send at least one voice message from your Amazon Pinpoint account\. You can send a voice message on the [Test Messaging](messages.md) page, or by using the [SendMessages](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-messages.html#SendMessages) API\.

**To request production access**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Support** menu, choose **Support Center**, as shown in the following image\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/console_region_selector.png)

1. Under **Open support cases**, choose **Create case**\.

1. Choose **Service limit increase**\.

1. Under **Case details**, for **Limit type**, choose **Pinpoint Voice**\.

1. \(Optional\) Complete the following information:
   + **What's the maximum number of voice messages that you plan to send per day?**
   + **What will be the average length of each call that you send?**
   + **How do you obtain the phone numbers that you plan to send mvoice messages to?**
   + **How many dedicated phone numbers will you use to send your messages? Why did you choose this number?**
   + **How many calls do you expect to make from each phone number? \(1 to X\) messages per \(day/week/month/other\)**
   + **How do you obtain consent to send voice messages to your customers?**
   + **How can customers opt out of receiving messages from you? How will you process these requests?**

1. Under **Requests**, for **Region**, choose the AWS Region that you use to send voice messages\.

1. For **Limit**, verify that **Production Access** is selected\.

1. For **New limit value**, enter the maximum amount, in US Dollars, that you want to spend sending voice messages each calendar month\.

1. Under **Case description**, for **Use case description**, provide the following details:
   + The website or app of the company or service that will send voice messages\.
   + The service that's provided by your website or app, and how your voice messages contribute to that service\.

1. Under **Contact options**, for **Preferred contact language**, choose whether you want to receive communications for this case in **English** or **Japanese**\.

1. When you finish, choose **Submit**\. 

The AWS Support team provides an initial response to your request within 24 hours\.

In order to prevent our systems from being used to send unsolicited or malicious content, we have to consider each request carefully\. If we’re able to do so, we'll grant your request within this 24\-hour period\. However, if we need to obtain additional information from you, it might take longer to resolve your request\.

We might not be able to grant your request if your use case doesn’t align with our policies\.

## Requesting phone numbers<a name="channels-voice-manage-request-phone-numbers"></a>

You can use the Amazon Pinpoint console to request and lease phone numbers for sending voice messages\. These phone numbers are referred to as *long codes*\. A *long code* is a standard telephone number that contains up to 15 digits, depending on the country or region that it's based in\. When you lease a long code, the code is *dedicated*—that is, it's reserved for use only by your Amazon Pinpoint account\. You can lease local long codes that are based in a variety of countries or regions\.

**To request a dedicated long code for sending voice messages**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\. 

1. Under **Phone numbers**, choose **Request phone number**\.

1. On the **Define your phone numbers** page, for **Country**, choose the country where your recipients are located\. You can choose only one country at a time, but you can add more countries later if necessary\.

1. Specify the use case for the phone number\. You can choose one of the following options:
   + **Promotional** – Choose this option for sending marketing messages or messages promoting your business or service\.
   + **Transactional** – Choose this option for sending time\-sensitive messages, such as password resets or transaction alerts\.

   In some countries and regions, the value that you choose may determine the price that you pay for each message that you send\. Transactional messages are optimized for high deliverability, resulting in a higher cost in many countries\. Promotional messages are optimized for cost\-effectiveness\. For more information about SMS pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing)\.

1. The **Summary** section displays information about the number\. The **Price per month** shows the cost for a single number\.

1. For **Quantity**, choose the quantity of numbers you want to purchase\. You can purchase up to 10 numbers in a single request\. You can purchase additional numbers later\. The **Subtotal** updates to display the total monthly cost for the quantity of phone numbers that you're purchasing\.

1. \(Optional\) If you want to purchase additional phone numbers, choose **Add a country or region**\. 

1. When you're done purchasing phone numbers, choose **Next**\.

1. The **Review and request** page displays the number request details for each destination country\.

1. The **Total cost** displays the total cost for all numbers for all countries you've chosen\.

1. Choose **Request** if you're ready; otherwise, choose **Previous** to go to back and make any changes\. Once you choose **Request** you can no longer make changes\.

1. Typically, the request is approved instantaneously, and a confirmation appears at the top of the page noting that the phone numbers were added successfully\. You can now access those numbers on the Phone numbers tab of the **SMS and voice **page\.

   If the request encounters any errors, an error message displays at the top of the page\. Common errors might be that there were no long codes available for one of your selected countries or an error occurred while trying to provision a long code\. In some cases, your account might require additional review prior to approving your request\. Should this message appear, you'll need to create a support ticket providing further information about your request\.

## Relinquishing phone numbers<a name="channels-voice-manage-remove-phone-numbers"></a>

If you don't need a dedicated phone number \(long code\) for your account anymore, you can relinquish and end your lease for it\. When you relinquish a dedicated long code, we stop charging you for it in your bill for the next calendar month\.

**Important**  
If you relinquish a dedicated long code, you might not be able to obtain the same long code again in the future\.

**To relinquish a dedicated long code**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **Settings**, choose **SMS and voice**\. 

1. In the navigation pane, under **Settings**, choose **SMS and voice**\. 

1. On Phone numbers, select the long code that you want to relinquish, as shown in the following image\. Choose **Remove phone number**\.
**Note**  
You can also remove a phone number by choosing the phone number link, and then choosing **Remove phone number **from the number details page\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-manage-remove-phone-numbers.png)

1. In the **Remove number confirmation** window, confirm that you want to relinquish the long code by entering **delete**, and then choose **Delete**\.