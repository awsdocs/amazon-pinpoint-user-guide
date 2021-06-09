# Pause, resume, or stop a journey<a name="journeys-pause-stop"></a>

## Pausing a journey<a name="journeys-pause"></a>

After publishing a journey you can pause that journey\. During a paused journey, messages aren't sent and analytics data isn't generated\. You can pause a journey during holidays or if you need to re\-evaluate the journey itself for changes\. Any endpoints that entered the journey before the pause are completed and then paused\. Any endpoints waiting to enter the journey do not enter the journey during the pause\. If a journey is in a **Wait** activity, the timer on the **Wait** activity is paused\. After the journey is resumed, the **Wait** activity continues from the point at which it was paused\. A paused journey cannot be edited\.

**To pause a journey**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. For **All Projects**, choose an existing project\.

1. In the navigation pane, choose **Journeys**\.

1. Choose a currently published journey\.

1. In the upper\-right corner of the published journey's workspace, choose **Actions**\. 

1. Choose **Pause**\.

1. When prompted to confirm pausing the journey, choose **Pause**\.

   A paused journey stays paused indefinitely until you resume it\. 

## Resuming a journey<a name="journeys-resume"></a>

A paused journey can only be resumed after five minutes have passed\. When you resume a paused journey, participants resume traveling through the journey from the point they were at when the journey was paused\. If any journeys were in a **Wait** activity, the **Wait** activity countdown resumes from the point at which the journey was paused\.

**To resume a journey**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. For **All Projects**, choose an existing project\.

1. In the navigation pane, choose **Journeys**\.

1. Choose a currently paused journey\.

1. In the upper\-right corner of the paused journey's workspace, choose **Actions**\. 

1. Choose **Resume**\.

1. When prompted to confirm resuming the journey, choose **Resume**\.

   The journey resumes\.

## Stopping a journey<a name="journeys-stop"></a>

Stopping a journey permanently ends the journey and all activities associated with it\. Any activities that are currently in\-process are ended\. However, you'll still be able to view analytics data\.

**Tip**  
If you are unsure whether to stop a journey, consider pausing instead\. Because a stopped journey is stopped permanently , you must recreate the journey if you want to use it again\.

**To stop a journey**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. For **All Projects**, choose an existing project\.

1. In the navigation pane, choose **Journeys**\.

1. Choose a currently published journey\.

1. In the upper\-right corner of the journey workspace, choose **Actions**\. 

1. Choose **Stop**\.

1. When prompted to confirm stopping the journey, choose **Stop journey**\.

   The journey permanently stops\.

**Next**: [View journey metrics](journeys-metrics.md)