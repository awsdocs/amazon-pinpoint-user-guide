# Getting Started with Amazon Pinpoint<a name="gettingstarted"></a>

In only a few minutes, you can set up Amazon Pinpoint and start sending messages to your customers\. This section shows you how to create a project\. It also provides links to documentation that help you set up your communication channels, create segments, send campaigns, and view response metrics for your campaigns\.

## Create a Project<a name="getting-started-create-project"></a>

In Amazon Pinpoint, projects are collections of settings, customer information, segments, and campaigns\. If you're new to Amazon Pinpoint, the first step you should take is to create a project\.

**To create a project**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. If this is your first time using Amazon Pinpoint, you see a page that introduces you to the features of the service\. In the **Get started** section, type a name for your project, and then choose **Create a project**\.  
![\[The Create a segment page with the Build segment option selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/first_time_use.png)![\[The Create a segment page with the Build segment option selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Create a segment page with the Build segment option selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)
**Note**  
The project name can contain up to 64 alphanumeric characters\. It can also contain the following characters: comma \(,\), period \(\.\), at sign \(@\), underscore \(\_\), equals sign \(=\), and plus sign \(\+\)\. It can't contain spaces\.

1. On the **Configure features** page, choose a message channel or analytics category to set up\. You can choose from the following options:
   + **Email** – Set up a project that can send email from your email address\. Later, you can verify different address, or an entire domain\.
   + **SMS** – Set up a project that can send SMS \(text\) messages\.
   + **Push notifications** – Set up your project to send notifications directly to users of your mobile apps\.
   + **Mobile app analytics** – View instructions for integrating your mobile apps with Amazon Pinpoint\.
   + **Web app analytics** – View instructions for integrating your web apps with Amazon Pinpoint\.

   Alternatively, you can choose **Skip this step** to set up any of these features later\.

   For more information about setting up channels, see the following pages:
   + [Setting up the Amazon Pinpoint Email Channel](channels-email-setup.md)
   + [Setting up Amazon Pinpoint Mobile Push Channels](channels-mobile-setup.md)
   + [Setting up the Amazon Pinpoint SMS Channel](channels-sms-setup.md)

## Next Steps<a name="getting-started-next-steps"></a>

Now that you've created a campaign, you're ready to start engaging with your customers\. You can now complete the following steps:

1. \(Optional\) **Integrate your apps with Amazon Pinpoint** – If you plan to use Amazon Pinpoint to engage with users of your web and mobile apps, you should start by integrating Amazon Pinpoint with your apps\. When your customers use your apps, the apps automatically report data to Amazon Pinpoint\. You can use this data to create targeted customer groups for your communications\. 

   To learn more about integrating your apps with Amazon Pinpoint, see [Integrating Amazon Pinpoint with Your Application](https://docs.aws.amazon.com/pinpoint/latest/developerguide/integrate.html) in the *Amazon Pinpoint Developer Guide*\.

1. **Create segments** – When you create a campaign, you choose a *segment* to send that campaign to\. A segment is a group of your customers that share certain attributes\. For example, a segment might contain all of your customers who use version 2\.0 of your app on an Android device, or all customers who live in the city of Los Angeles\. You can create dynamic segments by using the data that your apps report to Amazon Pinpoint, or you can import segments\.

   To learn more about creating segments, see [Amazon Pinpoint Segments](segments.md)\.

1. **Create a campaign and send your first message** – In Amazon Pinpoint, campaigns contain the messages that you send to your segments\. You can send a single message at a specified time, or you can create messages that are sent on a recurring basis\. 

   To learn more about creating and sending campaigns, see [Amazon Pinpoint Campaigns](campaigns.md)\.

1. \(Optional\) **Request production access** – When you use Amazon Pinpoint to send email, your account begins in the *sandbox*\. While your account is in the sandbox, you can only send email to addresses and domains that you own\. When your account is removed from the sandbox, you can send email to any recipient\. To learn more about having your account removed from the sandbox, see [Opening a Sending Limits Increase Case](channels-email-manage-limits.md#channels-email-manage-limits-increase-case)\.

   When you use Amazon Pinpoint to send SMS messages, your account begins with a spending limit of $1\.00\. When you spend more than $1\.00 sending messages in a calendar month, Amazon Pinpoint stops sending additional messages until the next month\. You can request a higher spending limit by contacting AWS Support\. To learn more about increasing the spending limit for your account, see [Requesting Increases to Your Monthly SMS Spend Threshold for Amazon Pinpoint](channels-sms-awssupport-spend-threshold.md)\.

1. **View response metrics for your campaign** \- After you send campaigns and your customers interact with them \(for example, by opening or clicking messages\), you can use the charts in the **Analytics** section to track these responses\. 

   To learn more about viewing metrics in Amazon Pinpoint, see [Amazon Pinpoint Analytics](analytics.md)\.