# Adding Personalized Content to Message Templates<a name="message-templates-personalizing"></a>

To deliver dynamic, personalized content in messages that use a template, add *message variables* to the message template\. A *message variable* is a placeholder that refers to a specific attribute that you or Amazon Pinpoint created to store information about your users\. Each attribute typically corresponds to a characteristic of a user, such as a user's first name or the city where they live\. By adding message variables to templates, you can use these attributes to deliver custom content to each recipient of a message\.

If a template contains message variables, Amazon Pinpoint automatically replaces each variable with the current, corresponding value of the attribute for each recipient\. It does this each time it sends a message that uses the template\. This means that you can send personalized content to each recipient without creating multiple, customized versions of a message or message template\. You can also feel confident that the message contains the latest information that you have for a recipient\.

For example, if your project is a fitness application for runners and it includes attributes for each user's first name, preferred activity, and personal record, you could use the following text and message variables in a template:

`Hi {{Attributes.FirstName}}, congratulations on your new {{Attributes.Activity}} record of {{Attributes.PersonalRecord}}!`

When you send a message that uses the template, Amazon Pinpoint replaces the variables with the current value of each attribute for each recipient, as shown in the following examples\.

**Example 1**  
`Hi Sofia, congratulations on your new half marathon record of 1:42:17!`

**Example 2**  
`Hi Alejandro, congratulations on your new 5K record of 20:52!`

If an attribute value doesn't exist for a recipient, Amazon Pinpoint can replace a variable with a default value that you specify for the variable\. For example, if a user of your fitness application hasn't chosen their preferred activity, you could use `running` as a default value for the `{{Attributes.Activity}}` variable\. In this case, Amazon Pinpoint replaces the variable as shown in the following examples\.

**Example 1**  
`Hi Jane, congratulations on your new running record of 1:42:17!`

**Example 2**  
`Hi John, congratulations on your new running record of 20:52!`

If you don't specify a default value and a value doesn't exist for a recipient, Amazon Pinpoint omits all text for the variable when it sends a message to that recipient\. For example: `Hi Mary, congratulations on your new record of 20:52!`

## Adding Message Variables<a name="message-templates-add-variables"></a>

You can add message variables to a new template when you create the template, or to an existing template\. If you add variables to an existing template, Amazon Pinpoint doesn't apply the changes to any existing messages that use the previous version of the template\. This includes messages that haven't been sent yet, such as campaign messages that are scheduled to be sent at a later time\. This means that your changes won't affect any existing messages that use the template\.

**To add a message variable to a message template**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Message templates**\.

1. On the **Message templates** page, do one of the following: 
   + To create a new template and add a message variable to it, choose **Create a template**\. Then, on the template page, enter a name for the template and, optionally, a description of the template\.
   + To add a message variable to an existing template, choose the template that you want to add a variable to\. Then, on the template page, choose **Edit**\.

1. In the message details section, determine where you want to add a message variable\. Then add the name of the attribute whose value you want to display in that location\. Enclose the name in two sets of curly braces and use the exact capitalization of the name—for example, `{{Attributes.FirstName}}`\. For information about attributes that you can use, see the next topic in this section\.

   You can add a variable to the message body of any type of template\. For email and push notification templates, you can also add a variable to the message subject or title\.

1. Repeat the preceding step for each message variable that you want to add\.

1. \(Optional\) To specify a default value for a message variable, expand the **Default personalization values** section\. Then, in the list of variables, enter the default value that you want to use for the variable\.

1. When you finish, choose **Create** or **Update**, depending on whether you added one or more variables to a new or existing template\.

## Supported Attributes<a name="message-templates-variables"></a>

Each project can have standard attributes, which are attributes that Amazon Pinpoint provides automatically for any project, and custom attributes, which are attributes that you optionally define for a project\. There are three types of custom attributes:
+ **User attributes** – These attributes describe a user, such as a user's first name, last name, and birth date\. A *user* is an individual who has a unique user ID for a project\.
+ **Endpoint attributes** – These attributes describe a specific endpoint for a user\. An *endpoint* is a destination that you can send messages to—such as an email address, phone number, or mobile device\. Each user can be associated with one or more endpoints\. For example, if you communicate with a user by email, SMS, and phone, the user could be associated with three endpoints—one for the user's email address, another for the user's mobile phone number, and another for the user's home \(landline\) phone number\.
+ **Metric attributes** – These attributes are numeric metrics that your application reports to Amazon Pinpoint for individual endpoints, such as the number of sessions for a mobile app or the number of items left in a cart\.

You can use any standard or custom attribute in a message variable\.

The following table indicates the name to use in a message variable for each supported attribute, and it describes each attribute\. In the table, attributes that include *custom\_attribute* indicate the name to use for a custom attribute\. In those cases, replace *custom\_attribute* with the name of the custom attribute that you want a variable to use\. For example, if your project stores users' first names in a custom endpoint attribute named `FirstName` and you want to display a user's first name in a message, insert an `{{Attributes.FirstName}}` variable where you want a user's first name to appear in the message\.


| Attribute | Description | 
| --- | --- | 
| Address | The destination address for messages or push notifications that you send to the endpoint—for example, an email address, phone number, or device token\. | 
| Attributes\.custom\_attribute | A custom attribute that describes the endpoint\. | 
| ChannelType | The channel to use when sending messages or push notifications to the endpoint\. For example:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/message-templates-personalizing.html) | 
| CreationDate | The date and time when the endpoint was added to the project, in [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601)\. For example, 2019\-06\-30T13:45:25\.220Z\. | 
| Demographic\.AppVersion | The version number of the mobile app that's associated with the endpoint\. | 
| Demographic\.Locale | The locale of the endpoint, in the following format: the [ISO 639\-1 alpha\-2](https://en.wikipedia.org/wiki/ISO_639-1) code, followed by an underscore \(\_\), followed by an [ISO 3166\-1 alpha\-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) value\. For example, en\_US is the English language locale for the United States\. | 
| Demographic\.Make | The manufacturer of the endpoint's device, such as apple or samsung\. | 
| Demographic\.Model | The model name or number of the endpoint's device, such as iPhone or SM\-G900F\. | 
| Demographic\.ModelVersion | The model version of the endpoint's device\. | 
| Demographic\.Platform | The operating system on the endpoint's device, such as ios or android\. | 
| Demographic\.PlatformVersion | The version of the operating system on the endpoint's device\. | 
| Demographic\.Timezone | The endpoint's time zone, as a [tz database value](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)\. For example, America/Los\_Angeles for Pacific Time \(North America\)\. | 
| EffectiveDate | The date and time when the endpoint was last updated, in [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601)\. For example, 2019\-08\-23T15:54:35\.220Z\. | 
| EndpointStatus | Whether to send messages or push notifications to the endpoint: ACTIVE, send messages to the endpoint; or, INACTIVE, don't send messages to the endpoint\. | 
| Id | The unique identifier for the endpoint\. | 
| Location\.City | The city where the endpoint is located\. | 
| Location\.Country | The two\-character code, in [ISO 3166\-1 alpha\-2 format](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2), for the country or region where the endpoint is located\. For example, US for the United States\. | 
| Location\.Latitude | The latitude coordinate of the endpoint's location, rounded to one decimal place\. | 
| Location\.Longitude | The longitude coordinate of the endpoint's location, rounded to one decimal place\. | 
| Location\.PostalCode | The postal or ZIP code for the area where the endpoint is located\. | 
| Location\.Region | The name of the region where the endpoint is located\. For locations in the United States, this value is the name of a state\. | 
| Metrics\.custom\_attribute | A custom, numeric metric that your application reports to Amazon Pinpoint for the endpoint\. | 
| OptOut | Whether a user opted out of receiving messages and push notifications from you: ALL, the user opted out and doesn't want to receive any messages or push notifications; or, NONE, the user hasn't opted out and wants to receive all messages and push notifications\. | 
| RequestId | The unique identifier for the most recent request to update the endpoint\. | 
| User\.UserAttributes\.custom\_attribute | A custom attribute that describes the user\. | 
| User\.UserId | The unique identifier for the user\. | 