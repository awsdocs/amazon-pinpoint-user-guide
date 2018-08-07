# Creating an Amazon Pinpoint Project with Email Support<a name="channels-email-setup-create"></a>

To send email messages with Amazon Pinpoint, you must create an Amazon Pinpoint project, and then enable the email channel in that project\. There are two ways to create an Amazon Pinpoint project: by using the AWS Mobile Hub console, or by using the Amazon Pinpoint API\.

**Topics**
+ [Create a New Project by Using the Console](#channels-email-setup-create-console)
+ [Create a New Project by Using the Amazon Pinpoint API](#channels-email-setup-create-cli)

## Create a New Project by Using the Console<a name="channels-email-setup-create-console"></a>

If your project is based on a mobile app, you can create a project by using the Mobile Hub console\. By creating a project in the Mobile Hub console, you gain access to the features of Mobile Hub, such as user sign\-in and cloud\-based data storage\. When you create a project by using the following procedure, your project automatically appears in the Amazon Pinpoint console\.

**To create a Mobile Hub project by using the console**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose **Create a project in Mobile Hub**\.

1. For **Enter a name for your Mobile Hub project**, type a name, and then choose **Create project**\.

1. Under **What engagement features do you want to enable**, choose **Messaging**\.

1. Under **What messaging channels do you want to enable**, choose **Email**\.

1. Under **Do you want to enable email messaging**, choose **Enable**\.

1. Verify an identity by completing the procedures in [Verifying an Email Identity](channels-email-manage-verify.md)\.

## Create a New Project by Using the Amazon Pinpoint API<a name="channels-email-setup-create-cli"></a>

You can also create a project by using the Amazon Pinpoint API\. The steps in this section show you how to interact with the API by using the AWS CLI\. These steps assume that you've configured the AWS CLI to interact with your AWS account\. For more information about installing and configuring the AWS CLI, see the [AWS Command Line Interface User Guide](http://docs.aws.amazon.com/cli/latest/userguide/)\.

**To create a project by using the AWS CLI**

1. At the command line, type the following command to create a new project: 

   ```
   aws pinpoint create-app --create-application-request Name="My Email Project"
   ```

   Replace *My Email Project* in this command with a name for the project\.

1. Verify an identity by completing the procedures in [Verifying an Email Identity](channels-email-manage-verify.md)\.