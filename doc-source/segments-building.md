# Building Segments<a name="segments-building"></a>

To reach the intended audience for a campaign, build a segment based on the data reported by your application\.

For example, to reach users who haven’t used your mobile app recently, you can define a segment for users who haven’t used your app in the last 7 days\.

User segments are defined by various criteria, including but not limited to:

+ How recently they used your application

+ The operating system they use

+ The model of mobile device they use

Because the segment is built from segmentation criteria, it is dynamic, meaning the end users who belong to the segment vary over time based on user activity\. For example, if your segment includes users who haven’t used your application recently, users who respond to a campaign by using your application are removed from the segment\.

To create a static segment, which includes a fixed set of end users, import endpoints that represent those users\. For more information, see [Importing Segments](segments-importing.md)\.

You can create segments separately from campaigns to assemble a collection of segments for multiple campaigns\. You also can create a segment when [creating a campaign](campaigns.md)\. 

**To create a segment**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project to which you want to add the segment\.

1. In the navigation menu, choose **Segments**\. The **Segments** page opens, which displays previously defined segments and the number of active users that belong to them\.

1. Choose **New segment**\.

1. For **Segment name**, type a name for your segment to make it easy to recognize later\.

1. For **How would you like to define your segment**, keep **Build segment** selected\.  
![\[The Build segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_build.png)![\[The Build segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Build segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. For **What messaging channel do you want to use?**, choose the channel you will use to engage the segment with a campaign\. The channel must be enabled in your Amazon Pinpoint project\. For more information, see [Amazon Pinpoint Channels](channels.md)\.

1. If you selected **Mobile push** as the channel type, define the **App usage criteria**\. Select which users belong to the segment based on whether they have \(or haven't\) used your app within the specified number of days\.  
![\[The app usage criteria options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_usage.png)![\[The app usage criteria options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The app usage criteria options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. \(Optional\) For **Filter by standard attributes**, define which users belong to the segment based on the characteristics that are standard to Amazon Pinpoint\.  
![\[The device attributes options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_standard_attributes.png)![\[The device attributes options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The device attributes options.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. \(Optional\) For **Filter by custom attributes** and **Filter by user attributes**, define which users belong to the segment based on custom attributes that you add to your Amazon Pinpoint endpoint resources\.

1. When you are finished selecting criteria, choose **Create segment**\.