# General Settings<a name="settings-general"></a>

The **General settings** page contains several settings that impact the delivery of your campaigns\.

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Pinpoint Projects** page, choose the project that you want to change the settings for\.

1. Choose **Edit**\.

1. On the **Edit general settings** page, you can change the following settings:
   + **Quiet time** – Change these settings to prevent Amazon Pinpoint from sending messages during specific hours\. When you configure this setting, you provide a Start time and an End time\. The times you specify have to be in the format HH:MM, and have to use 24\-hour notation\.
   + **Max daily messages per endpoint** – Change this setting to specify the maximum number of messages that Amazon Pinpoint can send to a single endpoint in a 24\-hour period\. The value you specify can't be larger than 100\.
   + **Max campaign messages per endpoint** – Change this setting to specify the maximum number of messages that a single campaign can send to a single endpoint\. The value you specify can't be larger than 100\.
   + **Max messages per second** – Change this setting to specify the maximum number of messages that Amazon Pinpoint can send each second\. The value you specify has to be at least 50, and can't be larger than 20,000\.
   + **Max campaign run time** – Change this setting to specify the amount of time, in seconds, that individual campaigns are allowed to run\. The minimum value for this setting is 60 seconds\.

1. When you finish making changes, choose **Save**\.