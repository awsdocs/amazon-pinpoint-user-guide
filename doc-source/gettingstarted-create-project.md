# Step 1: Create and configure a project<a name="gettingstarted-create-project"></a>

In Amazon Pinpoint, a *project* is a collection of settings, customer information, segments, and campaigns\. If you're new to Amazon Pinpoint, the first step you should take is to create a project\.

**Note**  
If you've used the Amazon Pinpoint API, you may have seen references to "applications\." In Amazon Pinpoint, a *project* is the same as an *application*\.

This section shows you how to create a project\. As part of this procedure, you also verify an email address\. You use this address to send email when you create your email campaign later in this tutorial\.



## Create and configure a project<a name="gettingstarted-create-project-new-user"></a>

The procedures in this section show you how to create a project and verify an email address\. 



**To create a project and verify an email address**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. If this is your first time using Amazon Pinpoint, you see a page that introduces you to the features of the service\.

   In the **Get started** section, enter a name for your project, and then choose **Create a project**\.
**Note**  
The project name can contain up to 64 characters\.

1. On the **Configure features** page, next to **Email**, choose **Configure**\.

1. For **Email address**, type an email address that you want to use to send email\. For example, you can use your personal email address, or your work email address\. Choose **Verify**\.

1. Wait for 1–2 minutes, and then check the inbox for the email address that you specified in step 4\. You should see an email from *Amazon Web Services \(no\-reply\-aws@amazon\.com\)* with the subject line "Amazon Web Services – Email Address Verification Request in region *RegionName*", where *RegionName* is the name of the AWS Region that you're configuring Amazon Pinpoint in\.

1. Open the email, and then click the link in the body of the email\.

1. Return to the Amazon Pinpoint console in your browser\. On the **Set up email** page, choose **Save**\.

**Next:** [Import customer data and create a segment](gettingstarted-import-customer-data.md)