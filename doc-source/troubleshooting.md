# Troubleshooting<a name="troubleshooting"></a>

 Become familiar with troubleshooting information and possible solutions to help resolve issues when using Amazon Pinpoint\.<a name="troubleshooting-logging"></a>

As a best practice, consider logging events in Amazon Pinpoint by:
+ Turning on Events Streams through Amazon Kinesis Data Streams following the instructions in [Event stream settings](settings-event-streams.md)\. 
+ Using a custom logging solution\. For more information, see [Digital User Engagement Events Database](https://aws.amazon.com/solutions/implementations/digital-user-engagement-events-database/)\. Multiple services are involved and additional costs are incurred\.
+ Using Amazon CloudWatch metrics supported by Amazon Pinpoint\. For more information, see [Monitoring Amazon Pinpoint with Amazon CloudWatch](monitoring.md)\. 
+ Using Amazon Pinpoint API calls logged in CloudTrail\. For more information, see [Logging Amazon Pinpoint API calls with AWS CloudTrail](https://docs.aws.amazon.com/pinpoint/latest/developerguide/logging-using-cloudtrail.html) in the *Amazon Pinpoint Developer Guide*\.

**Topics**
+ [Segment import failed](#troubleshooting-segment-import)
+ [Segment export failed](#troubleshooting-segment-export)
+ [BadRequestException: Exceeded maximum endpoint per user count: 15](#troubleshooting-badrequestexception)
+ [BadRequestException when calling the UpdateEndpointsBatch or UpdateEndpoints operation: Too many custom attributes](#troubleshooting-attributes)
+ [Campaign issues](#troubleshooting-campaign)
+ [Dynamic segments: Endpoint count](#troubleshooting-dynamic-segment)
+ [Journey issue: Event\-driven journey isn't activated when using a PutEvents request](#troubleshooting-journey-event)
+ [Journey issue: All journey participants go through ‘No’ branch during ‘Yes/No’ split activity](#troubleshooting-journey-split)
+ [SMS delivery failures](#troubleshooting-sms-delivery-failures)
+ [SMS delivery delays](#troubleshooting-sms-delivery-delays)
+ [SMS two\-way](#troubleshooting-sms-two-way)
+ [Voice](#troubleshooting-voice)
+ [Push notifications: Delivery issue](#troubleshooting-push-delivery)
+ [Push notifications: Message not received](#troubleshooting-push-message-not-received)
+ [Push notifications: Message are not displayed](#troubleshooting-push-message-not-displayed)
+ [Email: Messages are not displayed](#troubleshooting-email-message-not-displayed)
+ [Email: Bounce status](#troubleshooting-email-message-bounce)
+ [CLI examples](#troubleshooting-cli-examples)

## Segment import failed<a name="troubleshooting-segment-import"></a>

If a segment import fails, you may see the following error message or similar: 

**Import job**: Import failed for file SampleTemplate\.csv with segment name SampleTemplate\. Bad request: The data we received didn't match the format we expected for the createImportJob operation\. Confirm that the information in your request is formatted properly, and then submit your request again\.

****Issue and solution****
+ This error occurs when the imported template is not formatted correctly\.
+ Verify that the template is in valid JSON or CSV format\. See [Segment files](segments-importing.md#segments-importing-examples-files) for an example of the correct format\. A sample template can also be downloaded from the Console\. Under your project, select **Segments**, **Create a segment**, **Import a segment**, and select **Download example CSV**\.
+ Verify that all specified attributes are valid\. **ChannelType** and **address** are required fields when importing segments\. Attribute names are case\-sensitive\. For a complete list of possible attributes that can be added to a template, see [Supported attributes](segments-importing.md#segments-importing-available-attributes)\.

## Segment export failed<a name="troubleshooting-segment-export"></a>

Can't export segment\. The export job continuously fails from the console\.

****Issue and solution****
+ Export jobs can fail for large exports when exporting from the console\.
+ As a workaround for this limitation, the segment can be exported to an Amazon S3 bucket using the [CreateExportJob](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-jobs-export.html#apps-application-id-jobs-exportpost) API through the command line reference \(CLI\) or SDK\.

## BadRequestException: Exceeded maximum endpoint per user count: 15<a name="troubleshooting-badrequestexception"></a>

This error occurs when attempting to add more than 15 endpoints associated with the same `UserId`\.

**Note**  
If the new endpoint has a channel type of ADM, GCM, APNS, APNS\_VOICE, APNS\_VOIP\_SANDBOX, or BAIDU, the request will succeed if there's already an endpoint with one of those channel types\. For more information, see [Managing an audience members maximum number of endpoints](https://docs.aws.amazon.com/pinpoint/latest/developerguide/audience-define-auto-inactive.html) in the *Amazon Pinpoint Developer Guide*\.

****Issue and solution****
+ You might see this error when creating new endpoints or editing existing ones using the [update\-endpoint](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/update-endpoint.html) API, and the specific endpoint exceeds the maximum number of 15 endpoint addresses\.
+ This limit is currently a hard limit with the service\. It can't be increased\. For more information, see [Endpoint quotas](https://docs.aws.amazon.com/pinpoint/latest/developerguide/quotas.html#quotas-endpoint)\.

## BadRequestException when calling the UpdateEndpointsBatch or UpdateEndpoints operation: Too many custom attributes<a name="troubleshooting-attributes"></a>

This error occurs when attempting to add more than 250 attributes\. Custom attributes can be a maximum of 15 KB per endpoint\.

****Issue and solution****
+ Export the segment and inspect it to confirm the number of custom attributes\.
+ The default number of attributes is 250, including attributes assigned to the `Attributes`, `Metrics`, and `UserAttributes`\.
+ To resolve, you might want to increase the limit\. For more information, see [Endpoint quotas](https://docs.aws.amazon.com/pinpoint/latest/developerguide/quotas.html#quotas-endpoint)\.

## Campaign issues<a name="troubleshooting-campaign"></a>

Verify that logging is turned on to assist in identifying the cause of failure\. For more information, see [Monitoring and logging\.](#troubleshooting-logging) 

### Campaign issue: Some endpoints were not processed or targeted successfully by the campaign<a name="troubleshooting-campaign-endpoints"></a>

 **Endpoints targeted**: The total number of endpoints for the chosen channel that will be sent a message when the campaign runs\. This total excludes duplicate or inactive endpoints from the segment\.

**Endpoints processed**: The total number of successfully targeted endpoints that were sent a message in the campaign run\.

****Issues and solutions****
+ It's possible that the number of endpoints that were successfully processed is lower than the number of total endpoints in the segment\. This difference can happen when the segment contains inactive endpoints or endpoints that are of channel types that are not used by the campaign\. You can view [Metrics for individual campaigns](analytics-campaigns.md#analytics-campaigns-description-individual) under a specific channel associated with your campaign\.
+ When using a dynamic segment, you might not get an accurate count of the number of endpoints per channel contained in the target segment by exporting the segment\. The endpoint data in such segments are subject to change over time based on the criteria defined in the dynamic segment\. 

### Campaign issue: Message throttling<a name="troubleshooting-campaign-throttling"></a>

****Issues and solutions****
+ Throttling due to downstream message delivery and carrier services\.
  + Review the Amazon CloudWatch metric `CampaignSendMessageThrottled` during the time frame that the campaign ran to confirm whether this is the issue\. For more information, see [View Amazon Pinpoint metrics in CloudWatch](monitoring-view-metrics.md)\.
  + Throttling occurs when the endpoint delivery rate capability is exceeded\. For more information, see Amazon Pinpoint [quotas](https://docs.aws.amazon.com/pinpoint/latest/developerguide/quotas.html)\.

### Campaign issue: Recipients timezone<a name="troubleshooting-campaign-time"></a>

****Issues and solutions****
+ Schedule the campaign to use recipient's local time by setting [isLocalTime](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-campaigns.html) to true\.
  + When a campaign is scheduled to use a recipient's local time for the campaign, all endpoints must have a `Demographic.Timezone` attribute value that is formatted correctly in the endpoint definition\. Otherwise, the endpoint won't be targeted successfully\. The [isLocalTime](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-campaigns.html) option bases the delivery time on each recipient's local time zone\.

### Campaign issue: Processing time<a name="troubleshooting-campaign-processing-time"></a>

****Issues and solutions****
+ The campaign doesn't have sufficient time to process all endpoints\.
  + When a campaign doesn't have sufficient time to process all targeted endpoints, the endpoints aren't processed and logs show a campaign\_send\_status of `EXPIRED`\.
  + Based on the number of endpoints being targeted by your campaign, verify that the **Maximum amount of time for a campaign run** and **Maximum number of messages per second** is configured based on your use case and delivery channel\. For more information, see [Configuring default settings for a project](settings-general.md#settings-general-campaigns)\.

### Campaign issue: Delivery, render or permanent failure<a name="troubleshooting-campaign-other"></a>
+ Downstream delivery issues, including rendering issues\.
  + Delivery issues can occur when reaching the different endpoint types\. Verify that logging is enabled to assist in identifying the cause of the failure\. To troubleshoot downstream delivery issues further, see the delivery issues associated with the corresponding endpoint type \.
  + Rendering issues occur for the following reasons: when a message template is used and template data is missing, template data is incorrectly formatted, or there's a mismatch between the template parameters and endpoint data\. For more information, see the email section under delivery issues\. \.
+ Permanent failure\.
  + Permanent failures occur when the endpoint address might not be reached by Amazon Pinpoint\. The reason for the permanent error is displayed in the logs\. Permanent failures are not retried\. Examples of permanent failures can include invalid address, such as an email address or a phone number, as well as permission issues, account in a sandbox, or insufficient quota\.

## Dynamic segments: Endpoint count<a name="troubleshooting-dynamic-segment"></a>

****Issues and solutions****
+ When a dynamic segment is used when creating a campaign, the number of endpoints count is an approximation and may not be accurate\. The segment can be exported to confirm the exact number of endpoints at a given point in time\. This is because endpoint data in dynamic segments are subject to change over time and based on the criteria defined in the dynamic segment

## Journey issue: Event\-driven journey isn't activated when using a PutEvents request<a name="troubleshooting-journey-event"></a>

****Issues and solutions****
+ Verify that the configured [Create a journey](journeys-create.md) are not being exceeded:
  + **Maximum daily messages per endpoint**
  + **Maximum number of messages an endpoint can receive from the journey**
  +  **Maximum number of journey messages per second**
  + **Maximum entries per endpoint ** 
+ Verify that the active number of event\-activated journeys doesn't exceed the provisioned threshold\. 
+ Verify that all components of the [PutEvents](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-events.html) API request are complete, including [Event Component](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-events.html#apps-application-id-events-model-event) and [Endpoint Component](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-events.html#apps-application-id-events-model-publicendpoint)\.
+ Verify that the specific journey is in the same application as the one in the PutEvent request\. 
+ Verify that the correct event is configured to activate your journey\. You can confirm this configuration in the [Journey entry condition](https://docs.aws.amazon.com/pinpoint/latest/userguide/journeys-entry-activity.html#journeys-entry-activity-event-triggered)\.
+ Event\-driven journeys are not conducive to Contact Center use cases because of the limited life span for dial operations is 3 minutes\.
+ You can use the following example request to activate a journey using a “TestEvent” entry condition\.

  ```
  aws pinpoint put-events --application-id 7149cbb8XXXXXXXX --events-request file://PutEvents.json
  file://PutEvents.json 
  {
      "BatchItem": {
          "ExampleEndpointID": {
              "Endpoint": {
                  "User": {
                      "UserId": "10107"
                  }, 
                  "ChannelType": "EMAIL",
                  "Address": "johndoe@example.com"
                     
              },
              "Events": {
                  "JourneyEvent": {
                      "EventType": "TestEvent",
                      "Timestamp": "2019-02-10T19:48:57+00:00"
                  }
              }
          }
      }
  }
  ```

## Journey issue: All journey participants go through ‘No’ branch during ‘Yes/No’ split activity<a name="troubleshooting-journey-split"></a>

****Issues and solutions****
+ This error can occur when no wait time is configured\. Send events are evaluated immediately, which results in moving all participants to the 'No' branch\. 
  + To resolve this issue, verify that some wait time is configured after the condition evaluation\.
+ Yes/No splits based on an event criterion and following custom AWS Lambda activities have an implicit wait time of 15 minutes to accrue and process the event outcomes\.
+ Yes/No splits based on an event criterion and following channel activities \(SMS, EMAIL, PNS\) have a wait time of 1 hour to accrue and process the delivery event statuses for channel message deliveries\.
+ Only standard events specific to channel delivery statuses are supported for Yes/No splits\.

## SMS delivery failures<a name="troubleshooting-sms-delivery-failures"></a>

****Issues and solutions****
+ Confirm that the number is valid using the [Amazon Pinpoint number validator](https://docs.aws.amazon.com/pinpoint/latest/developerguide/validate-phone-numbers.html)\. SMS delivery is supported for ‘MOBILE’ phoneType\. SMS delivery to ‘VOIP’ numbers might not be successful, but will be attempted on a best effort\.
+ Confirm that your monthly SMS spend quota isn't depleted by reviewing the `TextMessageMonthlySpend` metric in Amazon CloudWatch\. For more information see [View your monthly SMS and voice spending by using CloudWatch](channels-sms-monitor-spending.md#channels-sms-monitor-spending-metrics)
+ If the delivery issue is limited to one or two devices, then rule out device\-related issues\. Verify that the number\(s\) can receive SMS outside of Amazon Pinpoint at the time of the failure\. 
+ Turn on SMS event logging to assist in identifying the cause of the failure\.
  + Review the [message status](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams-data-sms.html#event-streams-data-sms-attributes-attrs)\.
  + Review how to resolve [Unknown error attempting to reach phone](https://aws.amazon.com/premiumsupport/knowledge-center/sns-unknown-error-phone-sms/)\.
+ Take note of the special requirements and regulations\. See [Country capabilities and limitations for SMS with Amazon Pinpoint](channels-sms-country-capabilities.md), and confirm that these requirements are being met\.

## SMS delivery delays<a name="troubleshooting-sms-delivery-delays"></a>

****Issue and solution****
+ SMS delivery issues can occur for many reasons\. This is because of the distributed path through which the message travels after leaving the AWS infrastructure\. For example, device\-related issues may be the result of poor network coverage\. 
+ As a best practice, measure SMS delivery delays by comparing the message sent time and the received time of the destination device\.
+ [Message Parts per Second \(MPS\) limits](channels-sms-limitations-mps.md) related to the original identity can also introduce delays\. 

## SMS two\-way<a name="troubleshooting-sms-two-way"></a>

Two\-way SMS responses are not received on either the SNS topic, subscribers, or both\.

****Issues and solutions****
+ Verify that you have a number with two\-way SMS enabled for a country where the feature is supported\. See [Supported countries and regions \(SMS channel\)](channels-sms-countries.md) and [Configuring two\-way SMS messaging in Amazon Pinpoint](channels-sms-two-way.md)\. 
+ Verify that the sender number is from the same country as the two\-way SMS\-enabled number in Amazon Pinpoint\. 
  +  An inbound SMS that is sent from a number outside of the country might fail to be delivered to Amazon Pinpoint\. Deliverability is affected by factors like telecom local rules and regulations across countries\. International SMS deliveries are attempted at a maximum effort\. 
  + If the sender number isn't from the same country as the two\-way SMS activated number in Amazon Pinpoint, and the source country of the sender number supports two\-way SMS, then a long or short code can work for users in the country\. See [Number purchase types](settings-sms.md#number-purchase-types)\. 
+ Verify that the sender number is a valid mobile number and not a virtual number by using the [Amazon Pinpoint Phone Number validator API](https://docs.aws.amazon.com/pinpoint/latest/developerguide/validate-phone-numbers.html)\. Communication between two virtual numbers, like the ones in Amazon Pinpoint, will be attempted at a maximum effort\. 
+ Review [Amazon SNS CloudWatch metrics](https://docs.aws.amazon.com/sns/latest/dg/sns-monitoring-using-cloudwatch.html#sns-metrics) for `NumberOfMessagesPublished`, `NumberOfNotificationsDelivered`, and `NumberOfNotificationsFailed` to verify if the Amazon SNS topic is able to receive the inbound SMS\. 
  + If there are data points for `NumberOfMessagesPublished` at the time of the inbound SMS timestamps, then the recipient response was successfully received from downstream\. They then attempted to reach Amazon SNS subscribers from Amazon Pinpoint\. However,there's a configuration or delivery issue between Amazon SNS and the destination endpoint\. To troubleshoot, activate logging on the Amazon SNS topic for the delivery protocol being used\. See [Amazon SNS message delivery status](https://docs.aws.amazon.com/sns/latest/dg/sns-topic-attributes.html)\. 
  + If there are data points for the `NumberOfMessagesPublished` metric at the time of the inbound SMS timestamps:
    + Review the Amazon SNS topic policy to confirm that it allows the Amazon Pinpoint service to publish to the Amazon SNS topic\. For an example policy, see [Configuring two\-way SMS in Amazon Pinpoint](channels-sms-two-way.md#channels-sms-two-way-configure)\. 
    + If the Amazon SNS topic linked to the two\-way SMS number is encrypted:
      + Verify that the key used is symmetric\. 
      + Verify that the key policy is modified to allow Amazon Pinpoint to use the key, see [Special requirements for encrypted topics](channels-sms-two-way.md#channels-sms-two-way-configure-enable-encrypted-topic)\. 

## Voice<a name="troubleshooting-voice"></a>

For logging of Amazon Pinpoint voice messages, see [How do I set up logging for Amazon Pinpoint voice messages for Amazon Pinpoint SMS and Voice v1 API?](https://aws.amazon.com/premiumsupport/knowledge-center/pinpoint-voice-message-logging-setup/)\. 

****Issues and solutions****
+ By default, the voice channel of an Amazon Pinpoint project is turned off\. To see if voice is turned on for your project, select the **Settings** page under the project\. Under **Features** for SMS and voice, you'll see whether each of the two are turned off or turned on\. While you can turn on SMS under the **Manage** option, you can turn on the voice channel by running the following command: 

  ```
  aws pinpoint update-voice-channel --application-id AppId --voice-channel-request Enabled=true
  ```
+ TooManyRequests exception
  + If your account is in a sandbox, there's a 20\-message limit over a 24 hour period\. This limit can be increased by [Requesting production access](channels-voice-manage.md#channels-voice-manage-sandbox)\.
  + Amazon Pinpoint voice channel has a hard limit of five messages per single recipient over a 24 hour period\. This limit is a hard limit that can't be increased\.

## Push notifications: Delivery issue<a name="troubleshooting-push-delivery"></a>

****Issues and solutions****
+ For direct push notification messages sent through the SendMessages API, verify that you capture the API response to get insights on the delivery\. To do so, review the StatusMessage attribute inside the [EndpointResult](https://docs.aws.amazon.com/pinpoint/latest/apireference/apps-application-id-messages.html#apps-application-id-messages-model-messageresponse) object in the response\. This attribute contains the [Platform response codes](https://docs.aws.amazon.com/sns/latest/dg/sns-msg-status.html#platform-returncodes) received from the Downstream Push Notification Service\. 
+ For campaigns, verify that logging through Kinesis Data Streams is turned on\. Review the [Platform response codes](https://docs.aws.amazon.com/sns/latest/dg/sns-msg-status.html#platform-returncodes) in the [\_campaign\.send](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams-data-campaign.html#event-streams-data-campaign-attributes) event for delivery outcome received by Amazon Pinpoint from the Downstream Push Notification Service\. 

## Push notifications: Message not received<a name="troubleshooting-push-message-not-received"></a>

****Issues and solutions****
+ Device connectivity issues – If the issue is only occurring on certain devices, verify that these devices aren't blocked from connecting to the push notification service endpoints\. See [FCM ports and your firewall](https://firebase.google.com/docs/cloud-messaging/concept-options#messaging-ports-and-your-firewall) and [If your Apple devices aren't getting Apple push notifications](https://support.apple.com/en-us/HT203609)\.
+ Endpoint **OptOut** attribute value – If an endpoint **OptOut** value is set to `ALL`, the endpoint will not receive notifications\. Use the [get\-endpoint](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/get-endpoint.html) CLI to confirm that the endpoint **OptOut** value is set to `NONE`\. If the endpoint is opted out, messages sent through campaigns or journeys won't be delivered to the endpoint, and no logs will be generated\. 
+ Token environment – Verify that the channel type for your Amazon Pinpoint endpoint matches the token generated for the device\. For example, use GCM as a channel for an app token address with FCM integration and for APNs, APNS\_Sandbox for your app in sandbox, or APNS for app in production\. 

  For insights on delivery attempts with a failure status, see the [Push Notification Response codes for the respective Push Channel](https://docs.aws.amazon.com/sns/latest/dg/sns-msg-status.html#platform-returncodes) used in the delivery attempt\. 

## Push notifications: Message are not displayed<a name="troubleshooting-push-message-not-displayed"></a>

****Issues and solutions****
+ You might see that the Kinesis event logs shows a **Successful Delivery** status, or that an issue only occurs with a particular request payload or message type\. This issue might indicate that the notification is being delivered to the device, but not being displayed on the system notification tray\. 
+ To troubleshoot, incorporate log statements in your **onMessageReceived** API handler of your app\. For an example, see [FCM](https://firebase.google.com/docs/cloud-messaging/android/receive) and [APNs](https://developer.apple.com/documentation/uikit/uiapplicationdelegate/1623013-application)\. This action can help determine whether the notification is received by the device, but not displayed in the system notifications tray\. 
+ If messages are received as an alert or notification payload, but not as data or silent payload, review the receive message handler code of your application to confirm that the received notification is pushed to the device notification tray\. 
+ Check what the intended action is when a message type of data, notification, alert, or background is received on your application, and whether the application can handle the different message types\.

## Email: Messages are not displayed<a name="troubleshooting-email-message-not-displayed"></a>

****Issues and solutions****
+ When using an email template, a rendering failure occurs when tmessage variables are missing,  formatted incorrectly, or when there is a mismatch between message variables and endpoint data\. 
+ Review the Amazon SES CloudWatch metric `RenderingFailure` during the time frame that the campaign ran to confirm whether rendering is the issue\. Rendering failures appear in the Amazon Pinpoint event logs as [\_email\.rendering\_failure events](https://docs.aws.amazon.com/pinpoint/latest/developerguide/event-streams-data-email.html#event-streams-data-email-attributes)\.
+ Test running the campaign without the template to confirm whether endpoints can successfully receive messages\. This action can help confirm that the issue is related to template variables\.
+ To resolve the issue, verify that all message variables have a corresponding endpoint attribute present and is in the correct format\. For more information, see [Adding personalized content to message templates](message-templates-personalizing.md)\.
+ Configure default values for all message variables in the template to grant delivery to endpoints if an attribute isn't present for an endpoint in the segment\.

## Email: Bounce status<a name="troubleshooting-email-message-bounce"></a>

****Solution for soft bounce****
+ A *soft bounce* occurs because of a temporary failure and will appear under the **\_email\.softbounce** event type in the logs\. Amazon Pinpoint handles soft bounces by attempting to redeliver the soft bounced emails for a specified period of time\.
+ A soft bounce can occur in the following scenarios:
  + The recipient mailbox is full\.
  + The recipient mailbox is temporarily unavailable\.
  + The server limits are exceeded\.
  + The server is overloaded\.
+ The specific error codes related to soft bounces are 421, 450, 451, or 452\. For the descriptions of these error codes, see [Simple Mail Transfer Protocol \(SMTP\) Enhanced Status Codes Registry](https://www.iana.org/assignments/smtp-enhanced-status-codes/smtp-enhanced-status-codes.xhtml)\. The **smtp\_response** in the logs provide the error code for the bounce event\.

****Solution for hard bounce****
+ A *hard bounce* is a persistent delivery failure that appears under the **\_email\.hardbounce ** event type in the logs\. These failures are not retried\.
+ A hard bounce can occur in the following scenarios:
  + The email address doesn’t exist\.
  + The domain name doesn’t exist\.
  + The recipient’s email server has blocked the emails\.
  + The email address is on the account suppression list\.
+ Monitor the number of hard bounces in your project and remove hard\-bouncing email addresses from your recipient lists\. Hard bounces can negatively impact your sending reputation and the deliverability of your email message\. For more information, review the best practices on [Bounces](channels-email-best-practices.md#channels-email-best-practices-bounce-rate)\.

## CLI examples<a name="troubleshooting-cli-examples"></a>

The following examples are common CLI commands for Amazon Pinpoint\.
+ Get Endpoint Data: [get\-endpoint](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/get-endpoint.html) CLI

  ```
  aws pinpoint get-endpoint —application-id AppId —endpoint-id EndpointId
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *EndpointId* with the ID of an existing endpoint that you're retrieving\.
+ Get User Data: [get\-user\-endpoints](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/get-user-endpoints.html) CLI

  ```
  aws pinpoint get-user-endpoints —application-id AppId —user-id UserId
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *UserId* with the ID of the user\.
+ Update or Create New Endpoint: [update\-endpoint](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/update-endpoint.html) CLI

  ```
  aws pinpoint update-endpoint —application-id AppId —endpoint-id EndpointId —endpoint-request '{"ChannelType":"SMS","Address":"+12345678","Location":{"Country":"USA"},"User":{"UserId":"UserId"}}'
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *EndpointId* with the ID of an existing endpoint that you're creating or updating\.
  + Replace *UserId* with the ID of the user\.
+ Delete Endpoint: [delete\-endpoint](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/delete-endpoint.html) CLI

  ```
  aws pinpoint delete-endpoint —application-id AppId —endpoint-id EndpointId 
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *EndpointId* with the ID of an existing endpoint that you're deleting\.
+ Validate a phone number:[phone\-number\-validate](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/phone-number-validate.html.html) CLI

  ```
  aws pinpoint phone-number-validate —number-validate-request PhoneNumber=+12065550100
  ```

**In the preceding command, make the following changes:**
  + Replace *\+12065550100* with the phone number that you want to validate\.
+ [send\-messages](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/send-messages.html) Examples CLI: SMS to a number

  ```
  aws pinpoint send-messages --application-id AppID --message-request '{"MessageConfiguration": {"SMSMessage":{"Body":"This is a test message"}},"Addresses": {"DestinationPhoneNumber": {"ChannelType":"SMS"}}}‘
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *DestinationPhoneNumber* with the phone number that you want to send to\.
+ [send\-messages](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/send-messages.html) Examples CLI: origination number to SMS

  ```
  aws pinpoint send-messages --application-id AppID --message-request '{"MessageConfiguration": {"SMSMessage":{"Body":"hello, how are you?","OriginationNumber": "OriginPhoneNumber"}},"Addresses": {"DestinationPhoneNumber": {"ChannelType":"SMS"}}}‘
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *OriginPhoneNumber* with the phone number that you want to send the message from\.
  + Replace *DestinationPhoneNumber* with the phone number that you want to send to\.
+ [send\-messages](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/send-messages.html) Examples CLI: SMS to an endpoint

  ```
  aws pinpoint send-messages —application-id AppID  —message-request '{"MessageConfiguration": {"SMSMessage":{"Body":"This is a test message"}},"Endpoints": {"EndPointId": {}}}'
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *EndPointId* with the ID of an existing endpoint that you're sending to\.
+ [send\-messages](https://docs.aws.amazon.com/cli/latest/reference/pinpoint/send-messages.html) Examples CLI: SMS to a userId

  ```
  aws pinpoint send-users-messages —application-id AppID —send-users-message-request '{"MessageConfiguration": {"SMSMessage":{"Body":"This is a test"}},"Users": {"UserId": {}}}'
  ```

**In the preceding command, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *UserId* with the ID of the user\.
+ Campaign Creation With [](messages-templates.md) [create\-campaign](cli/latest/reference/pinpoint/create-campaign.html) CLI

  ```
  aws pinpoint create-campaign —application-id AppId —write-campaign-request file://campaignclirequest.json 
  
  file://campaignclirequest.json 
  {
  	"Description": "CLITestCampaign",
  	"HoldoutPercent": 0,
  	"MessageConfiguration": 
  	{
  		"DefaultMessage": 
  		{
  			"Body": "TestFromCLI"
  		}
  	},
  	"Name": "TestingCLICampaign",
  	"Schedule": 
  	{
  		"StartTime": "IMMEDIATE"
  	},
  	"TemplateConfiguration": 
  		{
  		"EmailTemplate": 
  			{
  			"Name": "TemplateName",
  			"Version": "Version"
  			}
  		},
  	"SegmentId": "SegmentID",
  	"SegmentVersion": 1
  }
  ```

**In the preceding command and file, make the following changes:**
  + Replace *AppId* with the ID of the Amazon Pinpoint project that contains the endpoint\.
  + Replace *TemplateName* with the name of the template\.
  + Replace *Version* with the version of the template\.
  + Replace *SegmentID* with the ID of the segment to target\.