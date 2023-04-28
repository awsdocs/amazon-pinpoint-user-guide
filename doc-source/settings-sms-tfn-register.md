# US toll\-free number registration requirements and process<a name="settings-sms-tfn-register"></a>

**Important**  
US mobile carriers have recently changed their policies, and will require that all toll\-free numbers \(TFNs\) complete a registration process before 09/30/2022\. You can check the status of your number by visiting [Toll\-free number registration status](#settings-sms-tfn-register-company-statuses)\. For more information about registration, see [Registering your toll\-free number](#settings-sms-tfn-register-company-procedure)\.  
It can take up to 15 business days for your registration to be processed after it is submitted\.  
**Update March 3, 2023**: Effective April 1, 2023, mobile carriers will apply the following industry\-wide thresholds for messaging sent over any **unregistered toll\-free number**:   
Daily limit: 500 messages, resets at 12:00am PT
Weekly limit: 1,000 messages, resets Sunday at 12:00am PT 
Monthly limit: 2,000 messages, resets at the end of calendar month at 12:00am PT 
**We strongly encourage you to complete your registration as soon as possible\. Messages sent via unregistered TFNs will be on best effort basis, the messages will be subject to increased filtering and blocking over time as carriers continue to restrict unregistered traffic\.**

If you use Amazon Pinpoint to send messages to recipients in the United States, you can use toll\-free phone numbers \(TFN\) to deliver those messages\. After you request a TFN you can register your company using the TFN\. Each TFN requires a specific use case\. For example, if you register a TFN to use for one\-time passwords, it can only be used for sending one\-time passwords\. If a TFN is used for anything other than the specified use case, it can be revoked\. 

## Toll\-free number forbidden use cases<a name="settings-sms-tfn-register-forbidden-use-cases"></a>

Please be aware that AWS is limited in our ability to send any messages or register TFNs for some use cases\. Certain use cases are blocked entirely \(for example, use cases related to controlled substance, or phishing\) and other may be subject to high levels of filtering \(for example, high risk financial messages\)\. You may be unable to register TFNs associated with restricted content use cases defined in [Prohibited message content](channels-sms-best-practices.md#channels-sms-best-practices-message-content)\.

## Registering your toll\-free number<a name="settings-sms-tfn-register-company-procedure"></a>

Once you've purchased a toll\-free number following the steps in [Requesting a phone number using the Amazon Pinpoint console](settings-sms-request-number.md#settings-sms-request-number-console) you must register the number\. You can complete the registration process directly in the Amazon Pinpoint console\. The information you submit via the Amazon Pinpoint console will be passed on to our carrier partners to complete the registration\. When registering your TFN make sure the information is complete and accurate or your registration could be rejected\. The information that you enter should be an exact match for the company's corporate headquarters\. 

**Important**  
The information you submit via the Amazon Pinpoint console will be passed on to our carrier partners to complete the registration\.

**To register a toll\-free number**

1. Before you can register, purchase a TFN by following the directions found in [Requesting a phone number using the Amazon Pinpoint console](settings-sms-request-number.md#settings-sms-request-number-console)\. 

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Toll\-free registrations** tab, choose the Toll\-free Phone number that you want to register, then choose **Create registration**\.

1. In the **Company Information** section, enter the following:
   + For **Company Name**, enter the name of your company\. 
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
   + For **Opt\-in Workflow Description** enter a description of how users consent to receive SMS messages\. For example, by filling out an online form on your website\. 
   + For **Opt\-in workflow file**, upload an image showing how users consent to receiving messages\. The supported file type is PNG and the maximum file size is 400KB\. Additional information and examples of a compliant opt\-in workflow can be found at [Obtain permission](channels-sms-best-practices.md#channels-sms-best-practices-obtain-permission) \.
**Important**  
**Website opt\-in**: Mockup or screenshots of a web\-form where the client adds their number and agrees to receive messages\.
**Website Posting \(Support\)**: Where is the number advertised and where does the customer find the number to text in\.
**Keyword or QR Code Opt\-in**: Where does the customer find the keyword or QR code in order to opt\-in to these messages\.
**2FA/OTP**: Mockup or screenshot of opt\-in if applicable, if verbal, provide a mockup or screenshot of the verbal opt\-in script\.
**Informational**: Provide a mockup or screenshot of a verbal consent workflow and provide the messaging content\.

1. In the **Messaging Samples** section, do the following:
   + For **Message Sample 1**, enter an example message of an SMS message body that will be sent to your end users\. 
   + For **Message Sample 2 – optional** and **Message Sample 3 – optional**, enter additional example messages, if needed, of the SMS message body that will be sent\.
   + Each **Message Sample** text box has a maximum character limit of 306 characters\.

1. When you're done, choose **Submit registration**\.

## Toll\-free number registration status<a name="settings-sms-tfn-register-company-statuses"></a>

When you register your toll\-free number your registration will be in one of five different statuses:
+  **Created** – Your registration is created but not submitted\.
+ **Pending** – You must register the number before you can start sending messages\. 
+  **Reviewing** – Your registration has been accepted and is being reviewed\. It may take up to 15 business days for the review to be completed\.
+  **Complete** – Your registration has been approved and you can start using the toll\-free number to start sending messages\.
+  **Requires Updates** – You must fix your registration and resubmit it\. See [Editing a toll\-free number registration](#settings-sms-tfn-register-modify-company-edit) for more information\. Fields that require updates display a warning icon and a brief description of the issue\.
+  **Closed** – You deleted the toll\-free number and must also delete the registration for the number\.

**Check your registration status**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Toll\-free registrations** tab, choose the **Toll\-free Phone number**\.

1. You can then view the registration status of each toll\-free number\.

## Editing a toll\-free number registration<a name="settings-sms-tfn-register-modify-company-edit"></a>

After you submit your registration, the **registration status** will display as **Requires Updates** if there is an issue with the registration\. In this state, the registration form is editable\. Fields that require updates have a warning icon and a brief description of the issue\.

**To edit a company registration**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Toll\-free registrations** tab, choose the number that you want to edit and select the **Registration ID**\.

1.  Choose **Update registration** to edit the form and correct fields that have a warning icon\. 

1. Reupload previously submitted files for **Opt\-in Screenshot file**\.

1. 
**Important**  
Recheck all fields to ensure that they're correct\. 

   Choose **Submit registration** to resubmit when you're done\.

## Deleting a toll\-free number registration<a name="settings-sms-tfn-register-delete-company"></a>

If you no longer wish to use the toll\-free number after you have submitted your toll\-free number registration, you can delete the registration\. It is recommended that you first delete the toll\-free number and then the registration\.

**To delete a registration**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. On the **Toll\-free registrations** tab, choose the registration ID that you want to delete, and then choose **Delete Registration**\.

## Registration Issues<a name="settings-sms-tfn-registration-issues"></a>

If your Toll\-Free Number registration is not accepted you will see a message explaining why it was rejected\. If you have questions about this rejections that are not answered in our [Best Practices](https://docs.aws.amazon.com/pinpoint/latest/userguide/channels-sms-best-practices.html#channels-sms-best-practices-obtain-permission) you can submit a request with our support teams\.

**To submit a request for information about a rejected Toll\-Free Number**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Choose **Support**, and then **Support Center**\.

1. On the Support page, choose **Create case**\.

1. For **Case type**, choose **Service limit increase**\.

1. For **Limit type**, choose **Pinpoint SMS**\.

1. In the **Requests** section, do the following: 
   + Choose the place that you attempted to register the campaign in\.
   + For **Resource Type**, choose **10DLC or TFN Registration**\.
   + For the **Limit**, choose **Company or Campaign Registration Rejection**\.

1. For **Use case description**, enter the rejected Toll\-Free Number\.

1. Under **Contact options**, for **Preferred contact language**, choose the language that you prefer to use when communicating with the AWS Support team\.

1. For **Contact method**, choose your preferred method of communicating with the AWS Support team\.

1. Choose **Submit**\.

The AWS Support team will provide information about the reasons that your toll free registration was rejected in your AWS Support case\.

## Toll\-free number frequently asked questions<a name="settings-sms-tfn-register-faq"></a>

Frequently asked questions about the toll\-free number registration process\.

### Do I currently own a toll\-free number?<a name="settings-sms-tfn-register-faq1"></a>

**To check if you own a toll\-free number**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **SMS and voice**, choose **Phone numbers**\.

1. Toll\-free numbers have their **type** listed as **toll free**\.

### Do I have to register my toll\-free number?<a name="settings-sms-tfn-register-faq7"></a>

Yes\. If you currently own a toll\-free number, you must register before 09/30/2022 to continue using it\. If you purchase a new toll\-free number after 08/01/2022, you will need to register it to send messages\.

### How do I purchase a toll\-free number?<a name="settings-sms-tfn-register-faq2"></a>

Follow the directions at [Requesting a phone number using the Amazon Pinpoint console](settings-sms-request-number.md#settings-sms-request-number-console) to purchase a toll\-free number\.

### How do I register my toll\-free number?<a name="settings-sms-tfn-register-faq3"></a>

Follow the directions at [Registering your toll\-free number](#settings-sms-tfn-register-company-procedure) to register a toll\-free number\.

### What is the registration status of my toll\-free number and what does it mean?<a name="settings-sms-tfn-register-faq4"></a>

Follow the directions at [Toll\-free number registration status](#settings-sms-tfn-register-company-statuses) to check your registration and status\.

### What information do I need to provide?<a name="settings-sms-tfn-register-faq5"></a>

You will need to provide your companies address, a business contact, and a use case\. You can find the required information at [Registering your toll\-free number](#settings-sms-tfn-register-company-procedure)\.

### What if my registration is rejected?<a name="settings-sms-tfn-register-faq6"></a>

If your registration is rejected, its status will be changed to **Requires Updates** and you can make updates by following the directions in [Editing a toll\-free number registration](#settings-sms-tfn-register-modify-company-edit)\.

### What permissions do I need?<a name="settings-sms-tfn-register-faq8"></a>

The IAM permissions that you use to visit the Amazon Pinpoint console must be enabled with the *`“sms-voice:*”`* permission\.