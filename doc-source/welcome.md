# What Is Amazon Pinpoint?<a name="welcome"></a>

Amazon Pinpoint is an AWS service that you can use to engage with your customers across multiple messaging channels\. You can send push notifications, emails, or text messages \(SMS\), depending on the purpose of your campaign\.

The information in this user guide is intended for all Amazon Pinpoint users, including marketers, business users, and developers\. This guide contains information that's especially helpful for users who mainly interact with Amazon Pinpoint by using the AWS Management Console\. If you're new to Amazon Pinpoint, start by reading [Getting Started with Amazon Pinpoint](gettingstarted.md)\.

If you're an application developer, also refer to the [Amazon Pinpoint Developer Guide](http://docs.aws.amazon.com/pinpoint/latest/developerguide/) and the [Amazon Pinpoint API Reference](http://docs.aws.amazon.com/pinpoint/latest/apireference/)\. These documents provide information about using the features of Amazon Pinpoint programmatically\. They also contain information about integrating the features of Amazon Pinpoint into your applications\.

## Amazon Pinpoint Features<a name="welcome-features"></a>

This section describes the major features of Amazon Pinpoint\.

### Define Audience Segments<a name="welcome-segments"></a>

Reach the right audience for your messages by [defining audience segments](segments.md)\. A segment designates which users receive the messages that are sent from a campaign\. You can define dynamic segments based on data that's reported by your application, such as operating system or mobile device type\. You can also import static segments that you define outside of Amazon Pinpoint\.

### Engage Your Audience with Messaging Campaigns<a name="welcome-campaigns"></a>

Engage your audience by [creating a messaging campaign](campaigns.md)\. A campaign sends tailored messages on a schedule that you define\. You can create campaigns that send mobile push, email, or SMS messages\.

To experiment with alternative campaign strategies, set up your campaign as an A/B test, and analyze the results with Amazon Pinpoint analytics\.

### Send Direct Messages<a name="welcome-transactional"></a>

Keep your customers informed by [sending direct mobile push and SMS messages](messages.md)—such as new account activation messages, order confirmations, and password reset notifications—to specific users\.

### Analyze User Behavior<a name="welcome-analyze"></a>

Gain insights about your audience and the effectiveness of your campaigns by using the analytics that Amazon Pinpoint provides\. You can view trends about your users' level of engagement, purchase activity, and demographics\. You can monitor your message traffic with metrics for messages sent and opened\. Through the Amazon Pinpoint API, your application can report custom data, which Amazon Pinpoint makes available for analysis\.

To analyze or store the analytics data outside of Amazon Pinpoint, you can configure Amazon Pinpoint to [stream the data](analytics-streaming.md) to Amazon Kinesis\.

## Get Started<a name="welcome-getstarted"></a>

Get started with Amazon Pinpoint by creating a project in AWS Mobile Hub\. Your Mobile Hub project becomes available in Amazon Pinpoint\. For more information, see [Getting Started with Amazon Pinpoint](gettingstarted.md)\. 

Currently, Amazon Pinpoint is available in the US East \(N\. Virginia\) Region\.