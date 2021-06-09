# Setting up the Amazon Pinpoint voice channel<a name="channels-voice-setup"></a>

To send voice messages by using Amazon Pinpoint, start by creating a new Amazon Pinpoint project\. Then, enable the voice channel for the project and request a dedicated phone number, referred to as a *long code*, for sending voice messages\. A *long code* is a standard telephone number that contains up to 15 digits, depending on the country or region that it's based in\. These phone numbers are *dedicated*—that is, they're reserved for use only by your Amazon Pinpoint account\. You can lease local phone numbers that are based in a variety of countries or regions\.

**Tip**  
You can also enable the voice channel for an existing project\. To do this, use the **SMS and voice** settings page on the Amazon Pinpoint console\. For more information, see [Managing the Amazon Pinpoint voice channel](channels-voice-manage.md)\. 

Note that the settings that you choose for the voice channel also apply to the SMS channel for the project\. If you want to send both voice and SMS messages from the project, choose settings that support your goals for both channels\. To learn more about enabling and using the SMS channel, see [Amazon Pinpoint SMS channel](channels-sms.md)\.

**To set up the voice channel for a new project**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose **Create a project**\.

1. For **Project name**, enter a name, and then choose **Create**\.
**Note**  
The project name can contain up to 64 alphanumeric characters\. It can also include the following characters: comma \(,\), period \(\.\), at sign \(@\), underscore \(\_\), equals sign \(=\), and plus sign \(\+\)\.

1. Under **Project features**, in the **SMS and voice** section, choose **Configure**\.

1. Select **Enable the SMS channel for this project**\.

1. Expand the **Advanced configurations** section, and then choose **Request phone number**\.

1. On the **Define your phone numbers** page, for **Country**, choose the country where your recipients are located\. You can choose only one country at a time, but you can add more countries later if necessary\.

1. Specify the use case for the phone number\. You can choose one of the following options:
   + **Promotional** – Choose this option for sending marketing messages or messages promoting your business or service\.
   + **Transactional** – Choose this option for sending time\-sensitive messages, such as password resets or transaction alerts\.

   In some countries and regions, the value that you choose may determine the price that you pay for each message that you send\. Transactional messages are optimized for high deliverability, resulting in a higher cost in many countries\. Promotional messages are optimized for cost\-effectiveness\. For more information about SMS pricing, see [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing)\.

1. The **Summary** section displays information about the number\. The **Price per month** shows the cost for a single number\.

1. For **Quantity**, choose the quantity of numbers you want to purchase\. You can purchase up to 10 numbers in a single request\. You can purchase additional numbers later\. The **Subtotal** updates to display the total monthly cost for the quantity of phone numbers that you're purchasing\.

1. \(Optional\) If you want to purchase additional phone numbers, choose **Add a country or region**, and repeat the previous steps until you've defined requests for all of the countries where you need long codes\.

1. When you're done purchasing phone numbers, choose **Next**\.

1. The **Review and request** page displays the number request details for each destination country\.

1. The **Total cost** displays the total cost for all numbers for all countries you've chosen\.

1. Choose **Request** if you're ready; otherwise, choose **Previous** to go to back and make any changes\. Once you choose **Request** you can no longer make changes\.