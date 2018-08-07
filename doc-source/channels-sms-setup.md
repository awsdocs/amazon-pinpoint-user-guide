# Setting up the Amazon Pinpoint SMS Channel<a name="channels-sms-setup"></a>

To send SMS messages with Amazon Pinpoint, you need an Amazon Pinpoint project in which the SMS channel is enabled\. If your project is based on a mobile app, create it by using AWS Mobile Hub\. Otherwise, create your project by using the AWS Command Line Interface \(AWS CLI\)\.

You can also enable the SMS channel for an existing project by using the **Settings** page in the Amazon Pinpoint console\. For more information, see [Managing the Amazon Pinpoint SMS Channel](channels-sms-manage.md)\.

## Creating an SMS Project with AWS Mobile Hub<a name="channels-sms-setup-mobilehub"></a>

You can enable SMS messaging for a mobile app by creating a project with AWS Mobile Hub\. In the Mobile Hub console, create a project, and add the **Messaging & Analytics** feature\. Then, enable the SMS channel as part of that feature\. After you create a project in Mobile Hub, the project becomes available in Amazon Pinpoint\.

For more information, see the following topics in the *AWS Mobile Developer Guide*:
+ To create a project in Mobile Hub, see [Get Started](http://docs.aws.amazon.com/aws-mobile/latest/developerguide/getting-started.html)\.
+ After you create a project, to enable SMS messaging, see [Add Messaging to Your Mobile App with Amazon Pinpoint](http://docs.aws.amazon.com/aws-mobile/latest/developerguide/add-aws-mobile-messaging.html)\.

## Creating an SMS Project with the AWS CLI<a name="channels-sms-setup-cli"></a>

You can create an Amazon Pinpoint project that's enabled for SMS messaging by using the [AWS CLI](https://aws.amazon.com/cli/)\. The AWS CLI requires at least Python 2 version 2\.6\.5 or later, or Python 3 version 3\.3 or later\. For more information about installing and configuring the AWS CLI, see [Installing the AWS Command Line Interface](http://docs.aws.amazon.com/cli/latest/userguide/installing.html) in the *AWS Command Line Interface User Guide*\.

To create a project that's enabled for SMS, use the `create-app` and `update-sms-channel` commands, as shown by the following examples\.

**Example create\-app command**  
Use the [http://docs.aws.amazon.com/cli/latest/reference/pinpoint/create-app.html](http://docs.aws.amazon.com/cli/latest/reference/pinpoint/create-app.html) command to create an Amazon Pinpoint project:  

```
$aws pinpoint create-app --create-application-request Name="My SMS Project"
```
The following response is displayed:  

```
{
    "ApplicationResponse": {
        "Id": "1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o6",
        "Name": "My SMS Project"
    }
}
```
Note the ID that's provided in the response because you'll use it when you enable the SMS channel\.

**Example update\-sms\-channel command**  
Use the [http://docs.aws.amazon.com/cli/latest/reference/pinpoint/update-sms-channel.html](http://docs.aws.amazon.com/cli/latest/reference/pinpoint/update-sms-channel.html) command to enable the SMS channel for a project:  

```
$aws pinpoint update-sms-channel --application-id application-id --sms-channel-request Enabled=true
```
The following response is displayed:  

```
{
    "SMSChannelResponse": {
        "ApplicationId": "1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o6",
        "CreationDate": "2018-02-20T22:15:05.025Z",
        "Enabled": true,
        "Id": "sms",
        "IsArchived": false,
        "LastModifiedDate": "2018-02-20T22:15:05.025Z",
        "Platform": "SMS",
        "Version": 1
    }
}
```

After you create a project, it's available in the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

## Next Steps<a name="channels-sms-setup-next"></a>

You've created a project that's enabled for SMS messaging\. Now you can use Amazon Pinpoint to send SMS messages\. 

To engage an audience segment with an SMS campaign, see [Amazon Pinpoint Campaigns](campaigns.md)\.

To send an SMS message directly to a limited audience without creating a campaign, see [Direct Messages with Amazon Pinpoint](messages.md)\.

Some SMS options, such as dedicated origination numbers or sender IDs, are unavailable until you contact AWS Support\. For more information, see [Requesting Support for SMS Messaging with Amazon Pinpoint](channels-sms-awssupport.md)\.