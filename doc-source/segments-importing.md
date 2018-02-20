# Importing Segments<a name="segments-importing"></a>

In Amazon Pinpoint, you can define a user segment by importing information about the users who belong to the segment\.

Importing segments is useful if you have segments of your users outside of Amazon Pinpoint but you want to engage your users with Amazon Pinpoint campaigns\.

Unlike the dynamic segments that you create with the segment builder in the console, an imported segment is an unchanging set of *endpoints*\. Each endpoint is a unique messaging destination, such as an email address, a mobile device identifier, or a mobile phone number\. When Amazon Pinpoint sends a message to the segment, it sends the message to each of the endpoints in that segment\.

To import a file, you first upload it to an Amazon Simple Storage Service \(Amazon S3\) bucket\. Next, you provide Amazon Pinpoint with the name of the Amazon S3 bucket that contains the file\. Amazon Pinpoint retrieves the file from Amazon S3 and adds each endpoint in the file to a segment\.

## Creating Endpoint Files<a name="segments-importing-examples"></a>

You can define one or more endpoints in a CSV or newline\-delimited JSON file, and then import that file into Amazon Pinpoint to create a segment\.

When you import segments, consider the following:

+ If you're importing new endpoints, the `Address` and `ChannelType` attributes are required\.

+ If you're updating existing endpoints, the `Id` attribute is required for each endpoint that you want to update\.

+ Amazon Pinpoint can't import compressed files\.

+ The files that you import must use UTF\-8 character encoding\.

+ Your endpoint definitions can only include certain attributes\. For a list, see [Available Attributes](#segments-importing-available-attributes)\.

+ To determine if an endpoint is already registered, you can issue an HTTP `GET` request to the `endpoints` URI in the Amazon Pinpoint API\.

The following two sections provide examples of JSON and CSV file layouts based on the data in the following table\.


****  

| ChannelType | Address | Location\.Country | Demographic\.Platform | Demographic\.Make | 
| --- | --- | --- | --- | --- | 
| SMS | 2065550182 | USA | Android | LG | 
| APNS | 1a2b3c4d5e6f7g8h9i0j1a2b3c4d5e6f | USA | iOS | Apple | 
| EMAIL | john\.stiles@example\.com | CAN | iOS | Apple | 
| GCM | 4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c | EGY | Android | Google | 
| EMAIL | wang\.xiulan@example\.com | CHN | Android | OnePlus | 

### JSON Endpoint File Example<a name="segments-importing-examples-json"></a>

Amazon Pinpoint can import files in newline\-delimited JSON format\. In this format, each line is a complete JSON object that contains an individual endpoint definition, as in the following example:

```
{"ChannelType":"SMS","Address":"2065550182","Location":{"Country":"USA"},"Demographic": {"Platform":"Android","Make":"LG"}}
{"ChannelType":"APNS","Address":"1a2b3c4d5e6f7g8h9i0j1a2b3c4d5e6f","Location":{"Country":"USA"},"Demographic": {"Platform":"iOS","Make":"Apple"}}
{"ChannelType":"EMAIL","Address":"john.stiles@example.com","Location":{"Country":"CAN"},"Demographic": {"Platform":"iOS","Make":"Apple"}}
{"ChannelType":"GCM","Address":"4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c","Location":{"Country":"EGY"},"Demographic": {"Platform":"Android","Make":"Google"}}
{"ChannelType":"EMAIL","Address":"wang.xiulan@example.com","Location":{"Country":"CHN"},"Demographic": {"Platform":"Android","Make":"OnePlus"}}
```

### CSV Endpoint File Example<a name="segments-importing-examples-csv"></a>

Amazon Pinpoint can also import endpoints that are defined in a CSV file, as in the following example:

```
ChannelType,Address,Location.Country,Demographic.Platform,Demographic.Make
SMS,2065550182,USA,Android,LG
APNS,1a2b3c4d5e6f7g8h9i0j1a2b3c4d5e6f,USA,iOS,Apple
EMAIL,john.stiles@example.com,CAN,iOS,Apple
GCM,4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c,EGY,Android,Google
EMAIL,wang.xiulan@example.com,CHN,Android,OnePlus
```

The first line is the header, which contains the endpoint attributes\. These attributes are the same as those in the endpoint JSON format\. Use a period to address attributes that are nested in the JSON structure\. For example, the header for the device make is `Demographic.Make`\. The subsequent lines define the endpoints by providing values for each attribute in the header\.

To include a comma, line break, or double quote in a value, enclose the value in double quotes, as in `"aaa,bbb"`\. For more information about the CSV format, see [RFC 4180 Common Format and MIME Type for Comma\-Separated Values \(CSV\) Files](https://tools.ietf.org/html/rfc4180)\.

## Uploading Endpoint Definitions to Amazon S3<a name="segments-importing-addtos3"></a>

Amazon S3 is an AWS service that provides highly scalable cloud storage\. Amazon S3 stores data as objects within buckets, and those objects can be grouped into folders\.

Before you import a segment, you must create an S3 bucket and upload your endpoint file to that bucket\. You can organize the endpoints for different segments into separate folders\. When Amazon Pinpoint imports the endpoints for a segment, it includes the endpoints within all folders and subfolders that belong to the Amazon S3 location you specify\.

For an introduction to creating buckets and uploading objects, see the [Amazon Simple Storage Service Getting Started Guide](http://docs.aws.amazon.com/AmazonS3/latest/gsg/)\.

Amazon Pinpoint can import endpoints that are contained in the following types of files:

+ Newline\-delimited JSON

+ Comma\-separated values \(CSV\)

Amazon Pinpoint can import only one of these formats per segment, so the Amazon S3 path you specify should only contain one format type\.

## Importing a Segment<a name="segments-importing-procedure"></a>

You can create a segment by importing the segment's endpoints from Amazon S3\.

**To import a segment**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project that you want to add the segment to\.

1. In the navigation menu, choose **Segments**\. The **Segments** page opens, which displays previously defined segments and the number of active users that belong to them\.

1. Choose **New segment**\.

1. For **Segment name**, type a name for your segment to make it easy to recognize later\.

1. For **How would you like to define your segment**, choose **Import segment**\.  
![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_import.png)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. For **Amazon S3 URL**, type the location of the Amazon S3 bucket that contains the endpoints for your segment\. The address of the bucket must be in the following format:

   ```
   s3://bucket-name/folder-name
   ```

   Amazon Pinpoint imports endpoints from the path you specify and from any subfolders in that path\.

1. For **IAM role**, complete one of the following steps:

   + If you want to have Amazon Pinpoint create a role that allows it to read from an Amazon S3 bucket, select **Automatically create a role**\. Then, for **Name for new role**, type a name for the role that you're creating\.

   + If you've already created an IAM role that allows Amazon Pinpoint to read from an Amazon S3 bucket, select **Choose a role from your account**\. Then, for **Role**, choose a role that contains the appropriate permissions\.

1. For **What is the format of the file**, choose either **CSV** or **JSON**, depending on the format of your endpoint file\.

1. Choose **Import Segment**\. Amazon Pinpoint imports the endpoints from the specified Amazon S3 bucket and adds them to your segment\.

   The **Jobs** page provides the status of your import\. Refresh your browser to see the current status\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_job.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

## Available Attributes<a name="segments-importing-available-attributes"></a>

The following table contains the list of attributes that you can specify in the files you import into Amazon Pinpoint\. If you import segments using CSV files, the headers in the file should match the names shown in the **Attributes** column\.

For JSON files, a period in the attribute name indicates that the name following the period is an object that is nested in a parent object with a name equal to the value preceding the period\. For example, a JSON file that contains the `Demographic.Make` and `Demographic.Model` attributes has the following structure:

```
{
...
"Demographic": {
  ...
  "Make":"Apple",
  "Model":"iPhone"
  ...
  }
...
}
```

You can replace attribute names shown in italics with any value\. For example, you can create custom attributes called `User.UserAttributes.FirstName` and `User.UserAttributes.LastName`\.


| Attribute | Description | 
| --- | --- | 
| Address | The unique destination of the endpoint, such as an email address, a mobile phone number, or a token for mobile push notifications\. | 
| Attributes\.custom\_attribute | Custom attributes that your app reports to Amazon Pinpoint\. You can use these attributes as selection criteria when you create a segment\. You can replace custom\_attribute with any value\. You can specify up to 20 custom attributes per endpoint\. | 
| ChannelType | The channel type of the endpoint\. Acceptable values: GCM, APNS, SMS, or EMAIL\. | 
| Demographic\.AppVersion | The version number of the application associated with the endpoint\. | 
| Demographic\.Locale | The locale of the endpoint in ISO 15897 format\. For example, en\_US \(English language locale for the United States\) or zh\_CN \(Chinese locale for China\)\. | 
| Demographic\.Make | The manufacturer of the endpoint device, such as Apple or Samsung\. | 
| Demographic\.Model | The model of the endpoint device, such as iPhone\. | 
| Demographic\.ModelVersion | The model version of the endpoint device\. | 
| Demographic\.Platform | The operating system of the endpoint device, such as ios or android\. | 
| Demographic\.PlatformVersion | The platform version of the endpoint device\. | 
| Demographic\.Timezone | The time zone of the endpoint\. Specified as a [tz database value](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones), such as America/Los\_Angeles\. | 
| EffectiveDate | The time at which the endpoint was last updated, in [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601)\. For example, 20171011T150548Z\. | 
| Id | The unique ID of the endpoint\. | 
| Location\.City | The city where the endpoint is located\. | 
| Location\.Country | The three\-letter code for the country or region where the endpoint is located, in ISO 3166\-1 alpha\-3 format\. For example, USA \(United States\) or CHN \(China\)\. For a complete list of ISO 3166\-1 alpha\-3 abbreviations, see [https://www\.iso\.org/obp/ui/\#search/code](https://www.iso.org/obp/ui/#search/code/)\. | 
| Location\.Latitude | The latitude of the endpoint location, rounded to one decimal place\. | 
| Location\.Longitude | The longitude of the endpoint location, rounded to one decimal place\. | 
| Location\.PostalCode | The postal or ZIP code of the endpoint\. | 
| Location\.Region | The region of the endpoint location, such as a state or province\. | 
| Metrics\.custom\_attribute | Custom metrics, such as the number of sessions or number of items left in a cart, to use for segmentation purposes\. You can replace custom\_attribute with any value\. You can specify up to 20 custom attributes per endpoint\.These custom values can only be numeric\. Because they are numeric, Amazon Pinpoint can perform arithmetic operations, such as average or sum, on them\. | 
| OptOut | Indicates whether a user has opted out of receiving messages\. Acceptable values: ALL \(user has opted out of all messages\) or NONE \(user has not opted out and receives all messages\)\. | 
| RequestId | The unique ID of the most recent request to update the endpoint\. | 
| User\.UserAttributes\.custom\_attribute | Custom attributes that are specific to the user\. You can replace custom\_attribute with any value, such as FirstName or Age\. You can specify up to 20 custom attributes per endpoint\. | 
| User\.UserId | The unique ID of the user\. | 

**Note**  
You can specify up to 20 custom attributes per endpoint for `Attributes`, `Metrics`, and `User.UserAttributes`\. However, you can create no more than 40 custom attributes across your entire Amazon Pinpoint account\.