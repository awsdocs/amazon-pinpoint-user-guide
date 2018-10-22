# Event Stream Settings<a name="settings-event-streams"></a>

On the **Event stream** settings page, you can enable or disable event streaming\. 

**To set up event streaming**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Pinpoint Projects** page, choose the app for which you want to set up data streaming\.

1. In the navigation pane, under **Settings**, choose **Event stream**\.

1. In the **Services** section, choose **Edit**\.

1. Choose **Stream to Amazon Kinesis**\.

1. Under **Stream**, choose one of the following options:
   + **Send events to an Amazon Kinesis stream** – Choose this option if you want to send Amazon Pinpoint event data to an external application for analysis\.
   + **Send events to an Amazon Kinesis Data Firehose delivery stream** – choose this option if you want to send event data to an AWS datastore, such as Amazon Redshift\.

1. For **Amazon Kinesis stream** or **Amazon Kinesis Data Firehose delivery stream**, choose the Amazon Kinesis stream that you want to use to export the data\.
**Note**  
If you haven't already created an Amazon Kinesis stream, go to the Amazon Kinesis console at [https://console\.aws\.amazon\.com/kinesis](https://console.aws.amazon.com/kinesis)\. For more information about creating streams, see the [Amazon Kinesis Data Streams Developer Guide](https://docs.aws.amazon.com/streams/latest/dev/) or the [Amazon Kinesis Data Firehose Developer Guide](https://docs.aws.amazon.com/firehose/latest/dev/)\.

1. Under IAM role, choose one of the following options:
   + **Use an existing role** – choose this option to have Amazon Pinpoint assume an IAM role that already exists in your account\. The role you select must allow the `firehose:PutRecordBatch` action\. For an example of a policy that allows this action, see [Permissions Policies](https://docs.aws.amazon.com/pinpoint/latest/developerguide/permissions-streams.html#permissions-streams-permissionspolicies) in the *Amazon Pinpoint Developer Guide*\.
   + **Automatically create a role** – choose this option to automatically create an IAM role with the required permissions\. This role authorizes Amazon Pinpoint to send data to the stream you chose in step 6\.

1. Choose **Save**\.

As Amazon Pinpoint receives events from your app and generates campaign events, it sends this data to your Kinesis stream\. For more information about the data that Amazon Pinpoint sends for an event, see [Event Data](https://docs.aws.amazon.com/pinpoint/latest/developerguide/analytics-streaming.html#analytics-streaming-data) in the *Amazon Pinpoint Developer Guide*\.