# Managing Amazon Pinpoint projects<a name="projects-manage"></a>

You can use the Amazon Pinpoint console to create, view, edit, and delete projects\. Within a project, you can also [import endpoints](segments-importing.md), [create segments](segments-building.md), [create campaigns](campaigns.md), [create journeys](journeys-create.md), and [view analytics data](analytics-charts.md) for that project\.

## Creating a project<a name="projects-manage-create"></a>

The procedure for creating a new project differs depending on whether your account already contains projects in the current AWS Region\.

### Option 1: Create and configure a project \(new Amazon Pinpoint users\)<a name="projects-manage-create-new-user"></a>

The procedures in this section show you how to create a new project\. If you've never created a project in Amazon Pinpoint, complete the procedures in this section\.

If your Amazon Pinpoint account includes one or more existing projects, you should complete the steps in [Option 2: Create and configure a project \(existing Amazon Pinpoint users\)](#projects-manage-create-existing-user) instead\.

**To create a project**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. If this is your first time using Amazon Pinpoint, you see a page that introduces you to the features of the service\.

   In the **Get started** section, enter a name for your project, and then choose **Create a project**\. The project name that you specify can contain up to 64 characters\.
**Note**  
You can't rename a project after it's been created\.

1. On the **Configure features** page, choose a channel to configure\. For example, if you plan to use the project to send email, choose the **Configure** button in the **Email** section\.

   When you choose to set up a channel, you see options related to configuring that channel\. For example, if you choose to [set up the email channel](channels-email-setup.md), you see options related to verifying an email address\. If you choose to [set up the SMS channel](channels-sms-setup.md), you see options related to setting your spending limit and default message type\. If you choose to [set up push notifications](channels-push-setup.md), you see options related to configuring your push notification service credentials\.
**Note**  
You can configure additional channels in this project later\. You aren't limited to only sending messages through the channel that you configured during this process\.

### Option 2: Create and configure a project \(existing Amazon Pinpoint users\)<a name="projects-manage-create-existing-user"></a>

The procedures in this section show you how to create a project if your Amazon Pinpoint account already includes one or more existing projects\.

If your Amazon Pinpoint account doesn't contain any projects, you should complete the steps in [Option 1: Create and configure a project \(new Amazon Pinpoint users\)](#projects-manage-create-new-user) instead\.

**To create a project**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose **Create a project**\.

1. On the **Create a project** window, for **Project name**, enter a name for your project, and then choose **Create**\. The project name that you specify can contain up to 64 characters\.

1. On the **Configure features** page, choose a channel to configure\. For example, if you plan to use the project to send email, choose the **Configure** button in the **Email** section\.

   When you choose to set up a channel, you see options related to configuring that channel\. For example, if you choose to [set up the email channel](channels-email-setup.md), you see options related to verifying an email address\. If you choose to [set up the SMS channel](channels-sms-setup.md), you see options related to setting your spending limit and default message type\. If you choose to [set up push notifications](channels-push-setup.md), you see options related to configuring your push notification service credentials\.
**Note**  
You can configure additional channels in this project later\. You aren't limited to only sending messages through the channel that you configured during this process\.  
If you prefer to set up channels later, choose **Skip this step**\.

## Editing a project<a name="projects-manage-edit"></a>

You can't edit the name of a project after it's been created, but you can edit some settings related to the project\. This section includes procedures for changing these settings, as well as descriptions of the settings that you can change\.

**To edit a project**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, in the list of projects, choose the project that you want to delete\.

1. In the navigation pane, under **Settings**, choose **General settings**\.

1. Choose **Edit**\.

1. On the **Edit general settings** page, change any of the following settings:  
**Quiet time hours**  
Use these settings to prevent Amazon Pinpoint from sending messages during specific hours\. When you configure these settings, you provide a **Start time** and an **End time**\. If a message would be sent between the start and end times in an endpoint's local time zone, Amazon Pinpoint doesn't attempt to send the message to that endpoint\.  
In order for this setting to observe local time zones, the endpoint definition for a recipient has to include a properly\-formatted `Demographic.Timezone` attribute\.
The times that you specify have to use 24\-hour notation and be in *HH:MM* format\. For example, for 9:30 PM, enter **21:30**\.  
**Maximum number of daily messages per endpoint**  
Use this setting to specify the maximum number of messages that can be sent to a single endpoint during a 24\-hour period by all the campaigns and journeys in the project\. The value that you specify can't be larger than 100\.   
**Maximum number of messages per endpoint**  
Use this setting to specify the maximum number of messages that can be sent to a single endpoint by each campaign or journey\. If a campaign recurs, this setting applies to all runs of the campaign\. The value that you specify can't be larger than 100\.  
This setting considers the number of messages that *target* an endpoint, as opposed to the number of messages that are actually *delivered* to an endpoint\. For example, if a campaign is configured to automatically send a message when a customer creates a new account, but the endpoint isn't able to receive the message \(for example, if the quiet time setting applies to the endpoint\), then the endpoint is still counted as having been targeted\. In this situation, the endpoint would be removed from subsequent runs of the campaign\.  
**Maximum number of messages per second**  
Use this setting to specify the maximum number of messages that can be sent each second by a campaign or journey\. The value that you specify has to be a number between 50 and 20,000\. If you define a messages per second parameter, we try to match it\. Otherwise, if this is not defined, we attempt to deliver the message as fast as possible\. Note that delivery speed, however, is dependent on channel latency at any given time\.  
**Maximum amount of time for a campaign run**  
Use this setting to specify the maximum amount of time, in seconds, that a campaign can attempt to deliver a message after the scheduled start time\. The minimum value for this setting is 60 seconds\.

1. When you finish, choose **Save**\.

## Deleting a project<a name="projects-manage-delete"></a>

You can delete projects\. When you do, all of the endpoint data, segments, campaigns, journeys, and analytics data are deleted too\.

**Warning**  
You can't restore a project after it's been deleted\.

**To delete a project**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, in the list of projects, choose the project that you want to delete\.

1. In the navigation pane, under **Settings**, choose **General settings**\.

1. Choose **Delete project**\.

1. On the confirmation window, in the text field, enter **delete**\. Choose **Delete**\.