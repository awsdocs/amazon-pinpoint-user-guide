# Special requirements for sending SMS messages to recipients in India<a name="channels-sms-senderid-india"></a>

By default, when you send messages to recipients in India, Amazon Pinpoint uses International Long\-Distance Operator \(ILDO\) routes to transmit those messages\. When recipients see a message sent over an ILDO connection, it appears to be sent from a random numeric ID \(unless you [purchase a dedicated short code](channels-sms-awssupport-short-code.md)\)\.

Companies that are registered in India can also use dedicated sender IDs to send their messages\. If you prefer to use a sender ID, you have to send those messages over *local routes* rather than ILDO routes\.

**Note**  
The price for sending messages using ILDO routes is much higher than the price for sending messages through local routes\. The prices for sending messages using both ILDO and local routes are shown on the [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/) page\.

To send messages using local routes, you must first register your use case and message templates with the Telecom Regulatory Authority of India \(TRAI\) through a Distributed Ledger Technology \(DLT\) portal\. When you register your use case through a DLT portal, you receive an Entity ID and a Template ID, which you must specify when you send your messages through Amazon Pinpoint\. These registration requirements are designed to reduce the number of unsolicited messages that Indian consumers receive and to protect consumers from potentially harmful messages\.

To complete the registration process, you must provide the following information:
+ Your organization's Permanent Account Number \(PAN\)\.
+ Your organization's Tax Deduction Account Number \(TAN\)\.
+ Your organization's Goods and Services Tax Identification Number \(GSTIN\)\.
+ Your organization's Corporate Identity Number \(CIN\)\.
+ A letter of authorization that gives you the authority to register your organization with Vilpower\. The Vilpower website includes a template that you can download and modify to fit your needs\.

**Topics**
+ [Step 1: Register your company and use case with the TRAI](#channels-sms-senderid-india-register)
+ [Step 2: Create a case with AWS Support](#channels-sms-senderid-india-support)
+ [Step 3: Specify the Entity ID and Template ID values when you send messages](#channels-sms-senderid-india-specify-ids)
+ [Understanding template matching issues](#channels-sms-senderid-india-specify-ids-templates)

## Step 1: Register your company and use case with the TRAI<a name="channels-sms-senderid-india-register"></a>

The first step is to register your company and use case with TRAI\. This section includes information about registering your sender ID using Vodafone Idea's Vilpower portal\. However, there are several other registration portals\. All DLT registration portals require you to provide the same registration details\. The Entity ID and Template ID values that you receive from these portals are interchangeable\. That is, if you register your use case using a portal other than the Vilpower portal, you can still use your Entity ID and Template ID to send messages using Amazon Pinpoint\.

**Note**  
Vilpower charges a fee for registering your company\. The current fee is shown on the [Vilpower website](https://www.vilpower.in/)\.

**To register your organization with the TRAI**

1. In a web browser, go to the Vilpower website at [https://www\.vilpower\.in](https://www.vilpower.in)\.

1. Choose **Signup** to create another account\. During the registration process, do the following:
   + When you're asked to specify the type of entity that you want to register as, choose **As Enterprise**\.
   + For **Telemarketer Name**, choose **Infobip Private Limited \- ALL**\. When prompted, start typing **Infobip** and then choose **Infobip Private Limited – ALL** from the dropdown list\.
   +  For **Enter Telemarketer ID**, enter **110200001152**\.
   + When prompted to provide your Header IDs, enter the sender IDs that you want to register\.
   + When prompted to provide your Content Templates, enter the message content that you plan to send to your recipients\. Include a template for every message that you plan to send\. 
**Note**  
The Vilpower website is not maintained by Amazon Web Services\. Steps on the Vilpower website are subject to change\.

## Step 2: Create a case with AWS Support<a name="channels-sms-senderid-india-support"></a>

After you register your company and use case with TRAI, you must create a case with AWS Support\. The AWS Support team uses the information that you provide in your case to associate your Entity ID and Template ID with your AWS account\.

**To open an AWS Support case**
+ Complete the steps at [Requesting sender IDs](channels-sms-awssupport-sender-id.md)\. In your request, provide the following required information:
  + The AWS Region that you use with Amazon Pinpoint\.
  + The company name\. The name that you provide must exactly match the name that you provided during the registration process\.
  + The Principal Entity ID \(PEID\) that you received after completing the registration process\.
  + An estimate of the number of messages that you plan to send each month\.
  + A description of your use case\.
  + Information about the steps that your recipients must complete to opt in to receiving your messages\.
  + Confirmation that you collect and manage opt\-ins and opt\-outs\.

## Step 3: Specify the Entity ID and Template ID values when you send messages<a name="channels-sms-senderid-india-specify-ids"></a>

To successfully deliver your messages using local routes, you must specify Entity ID and Template ID values that you received after completing the sender ID registration process\. You must also choose the correct entity type, and ensure that your messages match the example templates that you registered\.

The steps that you complete depend on how you send your SMS messages\. If you use the [SendMessages](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-messages.html#SendMessages) API to send your messages, you can include these attributes in your call to the API\. If you use campaigns or journeys to send your messages, you can specify the correct values when you set up the campaign or journey\. This section includes information for both scenarios\.

### Sending messages over Indian local routes using the SendMessages API<a name="channels-sms-senderid-india-specify-ids-api"></a>

**To send messages over Indian local routes using the SendMessages API**

1. In your call to the `SendMessages` API, provide values for the following parameters:
   + `EntityId` – The entity ID or Principal Entity \(PE\) ID that you received after completing the sender ID registration process\.
   + `TemplateId` – The template ID that you received after completing the sender ID registration process\.
**Important**  
Make sure that the Template ID that you specify matches your message template exactly\. If your message doesn't match the template that you provided during the registration process, the mobile carriers might reject your message\.

1. For the `MessageType` parameter, specify the appropriate route type for your message\. You can specify one of the following values:
   + `Promotional` – Specify this message type for promotional messages\. Promotional sender IDs only contain numbers\.
   + `Transactional` – Specify this message type for transactional messages\. Transactional sender IDs only contain letters, and are case\-sensitive\.

1. When you add content to your message, review your content thoroughly to ensure that it matches the content in the DLT registered template exactly\. If you include additional character returns, spaces, punctuation, or mismatched sentence case, carriers will block your SMS messages\. For more information about issues related to template matching, see [Understanding template matching issues](#channels-sms-senderid-india-specify-ids-templates)\.

### Sending messages over Indian local routes using campaigns<a name="channels-sms-senderid-india-specify-ids-campaigns"></a>

**To send messages over Indian local routes using campaigns**

1. Create a campaign as you normally would by following the steps in [Step 1: Create a campaign](campaigns-begin.md)\.

1. On [Step 3](campaigns-message.md) of the campaign creation process, in the **SMS settings** section, do the following:
   + For **Message type**, choose one of the following:
     + **Promotional** – Choose this option if you registered a promotional use case\. Promotional sender IDs only contain numbers\.
     + **Transactional** – Choose this option if you registered a transactional use case\. Transactional sender IDs only contain letters, and are case\-sensitive\.
   + In the **Sender ID** section, enter the sender ID that you registered with TRAI\.
   + In the **Regulatory Settings** section, enter the **Entity ID** and **Template ID** that you received during the registration process\. 
**Important**  
Make sure that the Template ID that you specify matches your message template exactly\. If your message doesn't match the template that you provided during the registration process, the mobile carriers might reject your message\.

1. Finish creating the campaign as you normally would\.

### Sending messages over Indian local routes using journeys<a name="channels-sms-senderid-india-specify-ids-journeys"></a>

**To send messages over Indian local routes using journeys**

1. Create a journey as you normally would by following the steps in [Create a journey](journeys-create.md)\.

1. Each time you add a **Send an SMS message** activity to the journey, do the following:
   + Under **Message type**, choose one of the following:
     + **Promotional** – Choose this option if you registered a promotional use case\. Promotional sender IDs only contain numbers\.
     + **Transactional** – Choose this option if you registered a transactional use case\. Transactional sender IDs only contain letters, and are case\-sensitive\.
   + Expand the **Additional settings** section\. On the **SMS Settings** tab, for **Sender ID**, enter the sender ID that you registered\.
   + On the **Regulatory Settings** tab, enter the **Entity ID** and **Template ID** that you received during the registration process\. 
**Important**  
Make sure that the Template ID that you specify matches your message template exactly\. If your message doesn't match the template that you provided during the registration process, the mobile carriers might reject your message\. For more information, see [Understanding template matching issues](#channels-sms-senderid-india-specify-ids-templates)\.

1. Finish creating the journey as you normally would\.

## Understanding template matching issues<a name="channels-sms-senderid-india-specify-ids-templates"></a>

Indian carriers will reject your messages if they don't align exactly with the templates that you submitted during the registration process\. If you experience message delivery issues, check your messages for the following common issues:
+ **Message content doesn't match registered template** – All of the messages that you send must correspond to a registered template\. If you send a message that doesn't exactly match the template associated with the Template ID that you provided, the mobile carriers will reject your message\.
+ **The value of a variable is too long** – If the value of a variable contains more than 30 characters, the mobile carriers will reject your message\.
+ **Case mismatch** – The mobile carriers compare your messages to the templates that you registered\. This comparison process is case\-sensitive\.
+ **Slightly different characters** – Your message can be rejected if it contains characters that look similar to the characters in your registered template, but are actually different\. For example, if you copy text from Microsoft Word, the text might include curly\-quote characters \( “ and ” \), as opposed to the straight quote character \( " \)\. Make sure that your message matches your registered templates exactly\.