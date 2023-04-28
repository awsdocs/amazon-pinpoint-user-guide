# Special requirements for Singapore<a name="channels-sms-senderid-singapore"></a>

Amazon Pinpoint customers are able to send SMS traffic in Singapore using a Sender ID that has been registered through the Singapore SMS Sender ID Registry \(SSIR\)\. SSIR was launched in March of 2022 through the Singapore Network Information Centre \(SGNIC\) which is owned by Info\-communications Media Development Authority \(IMDA\) of Singapore, and enables organizations to register their Sender ID when sending SMS to mobile phones in Singapore\. In order to use a registered Singapore Sender ID you must obtain a Unique Entity Number \(UEN\), then submit a request to Amazon Pinpoint to allow\-list your account for usage of your Sender ID and finally complete the registration process through SSIR\.  

If you do not register your ID by **2023–01–30** any message sent using a Sender ID will have its ID changed to **LIKELY\-SCAM** per regulatory agency rules\. After this date, regulators will continue to filter or block unregistered traffic at their discretion\. 

**Important**  
To ensure you can still send messages in Singapore your registration must be completed by **2023–01–30** in this order:  
[Registering for a Singapore Unique Entity Number \(UEN\)](#channels-sms-senderid-singapore-uen)
[Registering your Singapore Sender ID with Amazon Pinpoint](#channels-sms-senderid-singapore-amazon-procedure)
[Registering a Sender ID with Singapore Network Information Centre \(SGNIC\)](#channels-sms-senderid-singapore-sgnic)

## Registering for a Singapore Unique Entity Number \(UEN\)<a name="channels-sms-senderid-singapore-uen"></a>

In order to start a registration with the SSIR you must first obtain a Singapore Unique Entity Number \(UEN\)\. A UEN is a unique entity number you receive when you register your business with the Account and Corporate Registry Authority \(ACRA\), for more information see [Who Must Register with ACRA?](https://www.acra.gov.sg/how-to-guides/before-you-start/who-must-register)\. The amount of time to process can vary depending on how easily the ACRA can validate your request\. 

## Registering your Singapore Sender ID with Amazon Pinpoint<a name="channels-sms-senderid-singapore-amazon-procedure"></a>

Once you've registered your Singapore Unique Entity Number \(UEN\) you can complete the Sender ID registration process directly in the Amazon Pinpoint console\. When registering your Sender ID make sure the information is complete and accurate or your registration could be rejected\. 

**Important**  
The information you submit via the Amazon Pinpoint console will be passed on to our carrier partners to complete the registration\.

**To register a Singapore Sender ID**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Sender ID registrations** tab, choose **Create registration**\.

1. Choose **Singapore** as your destination country\.

1. In the **Company Information** section, enter the following:
   + For **Company Name**, enter the name of your company exactly how it appears on your UEN registration\. 
   + For **Tax ID**, enter the UEN number you received from the ACRA\.
   + For **Company Website**, enter the URL for your company's website\. 
   + For **Address 1**, enter the street address of your corporate headquarters\. 
   + For **Address 2 \- optional**, if needed enter suite number of your corporate headquarters\. 
   + For **City**, enter the city of your corporate headquarters\. 
   + For **State**, enter the state of your corporate headquarters\. 
   + For **Zip Code**, enter the zip code of your corporate headquarters\. 
   + For **Country**, enter the two digit ISO country code\. 

1. In the ** Contact Information** section, enter the following information:
   + For **First Name**, enter the first name of the person who will be your business's point of contact\.
   + For **Last Name**, enter the last name of the person who will be your business's point of contact\. 
   + For **Support Email**, enter the email address of the person who will be your business's point of contact\.
   + For **Support Phone Number**, enter the phone number of the person who will be your business's point of contact\.

1. In **Sender ID Information**, enter the following:
   + For **Sender ID**, enter the **Sender ID** you want to display for your messages\.
   + For **Registering on behalf of another brand/entity?** if yes then select True\. If you are not the end user sending the messages you are considered a "Representative" of the other brand/entity\.
   + For **Letter of authorization image – optional**, if you checked the box as **Registering on behalf of another brand/entity?** , upload an image of the complete Letter of Authorization \(LOA\)\. The supported file type is PNG and the maximum file size is 400KB\. A template for the LOA can be [downloaded](samples/Singapore_Sender_ID_Registration_LOA_Template.zip) for your convenience\. 
   + For **Sender ID connection – optional** you can add more details about the connection between the requested SenderID and company name\.

1. In **Messaging Use Case**, do the following:
   + For **Monthly SMS Volume** select the number of SMS messages that will be each month\.
   + For **Use Case Category** select one of the following use case types for the number: 
     +  **Two\-factor authentication** – Use this for sending two factor authentication codes\.
     +  **One\-time passwords** – Use this for sending a user a one time password\.
     +  **Notifications** – Use this if you only intend to send your users important notifications\.
     +  **Polling and surveys** – Use this to poll users on their preferences\.
     +  **Info on demand** – This is for sending users messages after they have sent a request\.
     +  **Promotions and Marketing** – Use this if you only intend to send marketing messages to your users\.
     +  **Other** – Use this if your use case doesn't fall into any other category\. Be sure that you fill out the **Use Case Details** for this option\.
   + Complete **Use Case Details – optional** to provide additional context to the selected **Use Case Category**\.

1. In the **Messaging Samples** section, do the following:
   + For **Message Sample 1**, enter an example message of an SMS message body that will be sent to your end users\. 
   + For **Message Sample 2 – optional** and **Message Sample 3 – optional**, enter additional example messages, if needed, of the SMS message body that will be sent\.
   + Each **Message Sample** text box has a maximum character limit of 306 characters\.

1. When you're done, choose **Submit registration**\.
**Important**  
Once your registration status is in the **Reviewing** state you should work with SGNIC to register your Sender ID\. You do not need to wait for your registration status to change to the **Completed** state to start the Sender ID registration process with SGNIC\. You can check your registration status by following the directions at [Singapore Sender ID registration status](#channels-sms-senderid-singapore-company-statuses)\.

## Registering a Sender ID with Singapore Network Information Centre \(SGNIC\)<a name="channels-sms-senderid-singapore-sgnic"></a>

To register a Sender ID with Singapore Network Information Centre \(SGNIC\) there are two steps that must be completed in the following order: 

**Register a Sender ID with Singapore Network Information Centre \(SGNIC\)**

1. You must first work with Amazon Pinpoint to register your Singapore \(SG\) Sender ID for your account\. Once this step is complete you can proceed to the next step\.

1. Work with SGNIC to register your Sender ID using the process at [SGNIC SMS Sender ID Registry](https://smsregistry.sg/web/login)\.

   1. When completing the process ensure you list all of the following as your participating aggregatiors:
     + AMCS SG Private Limited \(Amazon Media Communications Services\)
     + Nexmo PTE LTD
     + Sinch Singapore PTE LTD
     + Telesign Singapore PTE LTD
     + Twilio Singapore PTD LTD

**Warning**  
Doing these steps out of order may result in your Sender ID being blocked by the service or will prevent your Sender ID from being preserved on the mobile device\. 

**Note**  
Please note that you are required to submit a Sender ID registration from each individual AWS account you require to use the Sender ID\.

## Singapore Sender ID registration status<a name="channels-sms-senderid-singapore-company-statuses"></a>

When you register your Singapore Sender ID with Amazon Pinpoint your registration will be in one of five different statuses:
+  **Created** – Your registration is created but not submitted\.
+ **Submitted** – Your registration has been submitted and is being validated\. 
+  **Reviewing** – Your registration has been accepted and is being reviewed\. It may take between 1–3 weeks and in some cases it may take longer for the review to be completed\.
+  **Complete** – Your registration has been approved and you can start using the Sender ID\.
+  **Requires Updates** – You must fix your registration and resubmit it\. See [Editing a Singapore Sender ID registration](#channels-sms-senderid-singapore-modify-company-edit) for more information\. Fields that require updates display a warning icon and a brief description of the issue\.

**Check your registration status**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Sender ID registrations** tab, choose the **SenderID**\.

1. You can then view the registration status of each **SenderID**\.

## Editing a Singapore Sender ID registration<a name="channels-sms-senderid-singapore-modify-company-edit"></a>

After you submit your registration with Amazon Pinpoint, the **registration status** will display as **Requires Updates** if there is an issue with the registration\. In this state, the registration form is editable\. Fields that require updates have a warning icon and a brief description of the issue\.

**To edit a Sender ID**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **SenderID Registration** tab, choose the number that you want to edit and select the **Registration ID**\.

1.  Choose **Update registration** to edit the form and correct fields that have a warning icon\. 

1. If you are **registering on behalf of another brand/entity** you will need to reupload the previously submitted files for **Letter of authorization image – optional**\.

1. 
**Important**  
Recheck all fields to ensure that they're correct\. 

   Choose **Submit registration** to resubmit when you're done\.

## Deleting a Singapore Sender ID registration<a name="channels-sms-senderid-singapore-delete-company"></a>

If you no longer wish to proceed with your Singapore Sender ID registration, you can delete the registration\. Registrations can only be deleted if their status is **Created** or **Requires Updates**\.

**To delete a registration**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Sender ID** tab, choose the registration ID that you want to delete, and then choose **Delete Registration**\.

## Singapore Registration Issues<a name="settings-sms-singapore-registration-issues"></a>

If your Singapore Sender ID is not accepted by Amazon Pinpoint you will see a message explaining why it was rejected\. If you have questions about this rejections that are not answered in our [Best Practices](https://docs.aws.amazon.com/pinpoint/latest/userguide/channels-sms-best-practices.html#channels-sms-best-practices-obtain-permission) you can submit a request with our support teams\.

**To submit a request for information about a rejected Singapore Sender ID**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Choose **Support**, and then **Support Center**\.

1. On the Support page, choose **Create case**\.

1. For **Case type**, choose **Service limit increase**\.

1. For **Limit type**, choose **Pinpoint SMS**\.

1. In the **Requests** section, do the following: 
   + For **Resource Type**, choose **Sender ID Registation**\.
   + For the **Limit**, choose **Registration Rejection Query**\.

1. For **Use case description**, enter the rejected Singapore Sender ID and provided rejection reason\.

1. Under **Contact options**, for **Preferred contact language**, choose the language that you prefer to use when communicating with the AWS Support team\.

1. For **Contact method**, choose your preferred method of communicating with the AWS Support team\.

1. Choose **Submit**\.

The AWS Support team will provide information about the reasons that your Sender ID registration was rejected in your AWS Support case\.

## Singapore Sender ID registration frequently asked questions<a name="channels-sms-senderid-singapore-faq"></a>

Frequently asked questions about the Singapore Sender ID number registration process with Amazon Pinpoint\.

### Do I currently have a Singapore Sender ID<a name="channels-sms-senderid-singapore-faq1"></a>

**To check if you own a Singapore Sender ID**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **SenderID Registration** tab, choose the Sender ID that you want to view and select the **Registration ID**\.

### How long will registration take?<a name="channels-sms-senderid-singapore-faq9"></a>

While a typical review takes 1 – 3 weeks, it may take up to 5 weeks or longer in some cases to verify your information with government agencies\.

### What is a Unique Entity Number \(UEN\) and how do i get one?<a name="channels-sms-senderid-singapore-faq2"></a>

A UEN is a Singapore business ID issued by Accounting and Corporate Regulatory Agency \(ACRA\)\. Local companies and businesses in Singapore can get a UEN by applying through ACRA\. Once you pass through the registration and standard incorporation procedure, it will be issued\. You can apply for a UEN with ACRA via [Bizfile](https://www.bizfile.gov.sg/ngbbizfileinternet/faces/oracle/webcenter/portalapp/pages/BizfileHomepage.jspx)\.

### Do I have to register for a Singapore Sender ID?<a name="channels-sms-senderid-singapore-faq7"></a>

Yes\. If you currently haven't registered your Singapore Sender ID by **2023–01–30** any message sent using a Sender ID will have its ID changed to **LIKELY\-SCAM**

### How do I register my Singapore Sender ID with Amazon Pinpoint?<a name="channels-sms-senderid-singapore-faq3"></a>

Follow the directions at [Registering your Singapore Sender ID with Amazon Pinpoint](#channels-sms-senderid-singapore-amazon-procedure) to register a Sender ID\.

### What is the registration status of my Singapore Sender ID and what does it mean?<a name="channels-sms-senderid-singapore-faq4"></a>

Follow the directions at [Singapore Sender ID registration status](#channels-sms-senderid-singapore-company-statuses) to check your registration and status\.

### What information do I need to provide?<a name="channels-sms-senderid-singapore-faq5"></a>

You will need to provide your companies address, a business contact, and a use case\. You can find the required information at [Registering your Singapore Sender ID with Amazon Pinpoint](#channels-sms-senderid-singapore-amazon-procedure)\.

### What if my Singapore Sender ID registration is rejected?<a name="channels-sms-senderid-singapore-faq6"></a>

If your registration is rejected, its status will be changed to **Requires Updates** and you can make updates by following the directions in [Editing a Singapore Sender ID registration](#channels-sms-senderid-singapore-modify-company-edit)\.

### What permissions do I need?<a name="settings-sms-tfn-register-faq8"></a>

The IAM user/role that you use to visit the Amazon Pinpoint console must be enabled with the *`“sms-voice:*”`* permission\.