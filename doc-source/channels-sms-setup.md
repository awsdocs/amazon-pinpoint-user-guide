# Setting up the Amazon Pinpoint SMS Channel<a name="channels-sms-setup"></a>

To send SMS messages with Amazon Pinpoint, you need an Amazon Pinpoint project in which the SMS channel is enabled\.

You can create a new project with SMS support by using AWS Mobile Hub\. In the AWS Mobile Hub console, create a project, and add the **Messaging & Analytics** feature\. Then, enable the SMS channel as part of that feature\. After you create a project in Mobile Hub, the project becomes available in Amazon Pinpoint\. 

You can also enable the SMS channel for an existing project by using the **Settings** page in the Amazon Pinpoint console\. For more information, see [Managing the Amazon Pinpoint SMS Channel](channels-sms-manage.md)\.

**To create a project with SMS support**

1. Sign in to the AWS Management Console and open the Mobile Hub console at [https://console.aws.amazon.com/mobilehub](https://console.aws.amazon.com/mobilehub)\.

1. If you have other Mobile Hub projects, choose **Create new mobile project**\. If this is your first project, skip this step because you are taken directly to the page for creating a new project\.

1. Enter a project name\. The name you enter will be the name of your project in the Amazon Pinpoint console\. 

1. For the region, keep **US East \(Virginia\)**\. 

1. Choose **Create project**\. Mobile Hub creates the project and shows the **Pick and configure features for your project** page\.

1. Choose **Messaging & Analytics**\.

1. On the **Messaging & Analytics** page, for **What engagement features do you want to enable?**, choose **Messaging**\.

1. For **What Messaging Channels do you want to enable?**, choose **SMS**\.

1. For **Do you want to enable SMS messaging?**, choose **Enable**\.

1. For **What engagement features do you want to enable?**, choose **Analytics**, and choose **Enable**\. With analytics enabled, Amazon Pinpoint provides metrics about your SMS campaign activity\.

In the Amazon Pinpoint console, you can specify SMS preferences\. For more information, see [Managing the Amazon Pinpoint SMS Channel](channels-sms-manage.md)\.