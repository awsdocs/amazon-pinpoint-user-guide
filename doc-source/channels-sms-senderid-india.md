# Special requirements for sending SMS messages to recipients in India<a name="channels-sms-senderid-india"></a>

By default, when you send messages to recipients in India, Amazon Pinpoint uses International Long Distance Operator \(ILDO\) connections to transmit those messages\. When recipients see a message sent over an ILDO connection, it appears to be sent from a random numeric ID\.

**Note**  
The price for sending messages using local routes is shown on the [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/) page\. The price for sending messages using ILDO connections is higher than the price for sending messages through local routes\. Currently, the price for sending ILDO messages is USD $0\.02171 per message\.

If you prefer to use an alphabetic sender ID for your SMS messages, you have to send those messages over local routes rather than ILDO routes\. To send messages using local routes, you must first register your use case and message templates with the Telecom Regulatory Authority of India \(TRAI\) through Distributed Ledger Technology \(DLT\) portals\. These registration requirements are designed to reduce the number of unsolicited messages that Indian consumers receive and to protect consumers from potentially harmful messages\. This registration process is managed by Vodafone India through its Vilpower service\.

To complete the registration process, provide the following information:
+ Your organization's Permanent Account Number \(PAN\)\.
+ Your organization's Tax Deduction Account Number \(TAN\)\.
+ Your organization's Goods and Services Tax Identification Number \(GSTIN\)\.
+ Your organization's Corporate Identity Number \(CIN\)\.
+ A letter of authorization that gives you the authority to register your organization with Vilpower\. The Vilpower website includes a template that you can download and modify to fit your needs\.

Vilpower charges a fee for completing the registration process\. Currently, this fee is ₹5900\.

To send SMS messages to India you'll need to follow these steps:

**Topics**
+ [Step 1: Register with the TRAI](#india-senderid-register)
+ [Step 2: File an AWS Support request](#india-senderid-support)
+ [Step 3: Ensure your SMS are delivered successfully](#india-senderid-postregister)

## Step 1: Register with the TRAI<a name="india-senderid-register"></a>

**To register your organization with the TRAI**

1. In a web browser, go to the Vilpower website at [https://www\.vilpower\.in](https://www.vilpower.in)\.

1. Choose **Signup** to create another account\. During the registration process, do the following:
   + When you're asked to specify the type of entity that you want to register as, choose **As Enterprise**\.
   + You'll need to select a Telemarketer Name, which is **Infobip Private Limited \- ALL**\. When prompted, start typing **Infobip** and then choose **Infobip Private Limited – ALL** from the dropdown list\.
   +  For **Enter Telemarketer ID**, enter **110200001152**\.
   + When prompted to provide your Header IDs, enter the sender IDs that you want to register\.
   + When prompted to provide your Content Templates, enter the message content that you plan to send to your recipients\. Include a template for every message that you plan to send\. 
**Note**  
The Vilpower website is not maintained by Amazon Web Services\. Steps on their website are subject to change by Vilpower\.

## Step 2: File an AWS Support request<a name="india-senderid-support"></a>

**To file an AWS Support request**
+ Complete the steps at [Requesting sender IDs](channels-sms-awssupport-sender-id.md)\. In your request, provide the following required information:
  + Which AWS region the user will be calling our API/service from\.
  + The Company name as it was registered through DLT\.
  + The Principal Entity ID \(PEID\) that you received after successful DLT entity registration\.
  + The estimated monthly volumes\.
  + An explanation of your use case\.
  + A description of the end user opt\-in flow\.
  + Confirmation that end user opt\-ins are collected and registered\.

## Step 3: Ensure your SMS are delivered successfully<a name="india-senderid-postregister"></a>

To make sure your SMS messages are delivered successfully using local routes, you need to complete the following two steps: providing values for two Send Message API parameters and choosing the route type\.

**To ensure your SMS are delivered successfully**

1. In the Send Message API, provide values for the following parameters:
   + `EntityId` – The entity ID or Principal Entity \(PE\) ID received from the regulatory body for sending SMS in your country\.
   + `TemplateId` – The template ID received from the regulatory body for sending SMS in your country\.

1. Choose one of the following route types:
   + **Promotional** – Choose this type for promotional messages, which use a numeric sender ID\.
   + **Transactional** – Choose this type for transactional messages, which use a case\-sensitive alphabetic sender ID\.
**Note**  
You can use both numeric sender IDs \(promotional messages\) and alphabetic sender IDs \(transactional messages\) for an account within the same region\. For additional content guidelines, see the Vilpower website at [https://www\.vilpower\.in](https://www.vilpower.in)\. 

1. When adding the content to your message, thoroughly review your content to ensure that it exactly matches the content in the DLT registered template\. If you include additional character returns, spaces, punctuation, or mismatched sentence case, carriers will block your SMS\. Variables in a template – for example, `{#var#}` – cannot exceed 30 characters for each variable\. The following are some common use cases for message rejection:
   + **No template was found that matched the content sent\.**

     Content sent: **<\#> 12345 is your OTP to verify mobile number\. Your OTP is valid for 15 minutes \-\- ABC Pvt\. Ltd\.**

     Matched template: None

     Issue: There are no DLT templates that include `<#>` or `{#var#}` at the beginning of the DLT registered template\.
   + **The value of a variable exceeds 30 characters\.**

     Content sent: **12345 is your OTP code for ABC \(ABC Company \- India Private Limited\) \- \(ABC 123456789\)\. Share with your agent only\. \- ABC Pvt\. Ltd\.**

     Matched template: **\{\#var\#\} is your OTP code for \{\#var\#\} \(\{\#var\#\}\) \- \(\{\#var\#\} \{\#var\#\}\)\. Share with your agent only\. \- ABC Pvt\. Ltd\.**

     Issue: The value of “ABC Company \- India Private Limited” in the content sent exceeds a single `{#var#}` character limit of 30\. 
   + **The message sentence case does not match the sentence case in the template\.**

     Content sent: **12345 is your OTP code for ABC \(ABC Company \- India Private Limited\) \- \(ABC 123456789\)\. Share with your agent only\. \- ABC Pvt\. Ltd\.**

     Matched template: **\{\#var\#\} is your OTP code for \{\#var\#\} \(\{\#var\#\}\) \- \(\{\#var\#\} \{\#var\#\}\)\. Share with your agent only\. \- ABC PVT\. LTD\.**

     Issue: The company name appended to the DLT matched template is capitalized while the content sent has changed parts of the name to lowercase — “ABC Pvt\. Ltd\.” vs\. “ABC PVT\. LTD\.” 