# Chart Reference for Amazon Pinpoint Analytics<a name="analytics-charts"></a>

On the **Analytics** page, Amazon Pinpoint provides an overview of key metrics, as well as dashboards that provide details about campaigns, demographics, funnels, usage, revenue, and users\. You can filter these dashboards by date for further analysis\. You can also filter some dashboards by other attributes, such as event or channel\.

**Topics**
+ [Endpoints and Users in Charts](#analytics-endpoints-users)
+ [Exporting Dashboards](#analytics-exporting)
+ [Overview Charts](analytics-overview.md)
+ [Usage Charts](analytics-usage.md)
+ [Revenue Charts](analytics-revenue.md)
+ [Events Charts](analytics-events.md)
+ [Demographics Charts](analytics-demographics.md)
+ [Campaign Charts](analytics-campaigns.md)
+ [Transactional Messaging Charts](analytics-transactional-email.md)

## Endpoints and Users in Charts<a name="analytics-endpoints-users"></a>

Some of the charts in these dashboards provide data about *endpoints*\. Other charts provide data about *users*\.

An *endpoint* is a destination that you can send messages to—such as a user's mobile device, email address, or phone number\. Before you can see data about endpoints, your application must register endpoints with Amazon Pinpoint, or you must import your endpoint definitions\.

A *user* is an individual who has a unique user ID\. This ID can be associated with one or more endpoints\. For example, if a person uses your app on more than one device, your app could assign that person's user ID to the endpoint for each device\. Before you can see data about users, your application must assign user IDs to endpoints, or you must import endpoint definitions that include user IDs\.

For information about registering endpoints and assigning user IDs within your mobile app, see [Registering Endpoints \(iOS\)](https://docs.aws.amazon.com/pinpoint/latest/developerguide/mobile-sdk-ios-register.html) or [Registering Endpoints \(Android\) ](https://docs.aws.amazon.com/pinpoint/latest/developerguide/mobile-sdk-android-register.html)in the *Amazon Pinpoint Developer Guide*\. For information about registering endpoints and assigning user IDs by using the AWS SDK for Java, see [Adding Endpoints](https://docs.aws.amazon.com/pinpoint/latest/developerguide/endpoints.html) in the *Amazon Pinpoint Developer Guide*\. For information about importing endpoint definitions, see [Importing Segments](segments-importing.md)\.

## Exporting Dashboards<a name="analytics-exporting"></a>

You can export the dashboards on the **Usage**, **Revenue**, **Events**, **Demographics**, and **Campaigns** pages to comma\-separated values \(\.csv\) format\. When you export a dashboard, Amazon Pinpoint creates a \.zip file that contains a separate \.csv file for each chart in the dashboard\. You can open these files in any modern spreadsheet or data analysis application\. 

To export a dashboard, choose a date range for the reports \(and other attributes, if applicable\), and then choose **Download CSV**\. 