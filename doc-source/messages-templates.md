# Message Templates<a name="messages-templates"></a>

To save your message and reuse it in a separate campaign or test message, choose **Save as template** and provide a template name\. Then, you can load the template for any message by choosing **Load template** and selecting it from a list of saved templates\. Amazon Pinpoint populates your message with the template's content\. Then, you can send the message as\-is or customize as needed\.

You can base a template on any supported message type, and you can use the same template for other message types\. For example, you can write a push notification message, save it as a template, and use that template for an SMS message\. Note that if you use a single template for multiple message types, Amazon Pinpoint loads the content differently for each type\. For example, if you base a template on a push notification, and you load this template for an email message, the push notification *title* is used as the email *subject*\. The correlations between message parts are as follows:


**Mobile push templates**  

| The push notification \. \. \.  | Is used as the email \. \. \. | Is used as the SMS \. \. \. | 
| --- | --- | --- | 
| Title | Subject | Not used | 
| Message body | Plain text message | Message body | 


**Email templates**  

| The email \. \. \. | Is used as the push notification \. \. \.  | Is used as the SMS \. \. \. | 
| --- | --- | --- | 
| Subject | Title | Not used | 
| Message body \(HTML\) | Not used | Not used | 
| Plain text message | Message body | Message body | 


**SMS templates**  

| The SMS \. \. \. | Is used as the push notification \. \. \.  | Is used as the email \. \. \. | 
| --- | --- | --- | 
| Message type | Title | Subject | 
| Message body | Message body | Plain text message | 