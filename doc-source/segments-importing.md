# Importing Segments<a name="segments-importing"></a>

With Amazon Pinpoint, you can define a user segment by importing a file that contains information about the users who belong to the segment\. Importing segments is useful if you define user segments outside of Amazon Pinpoint but you want to engage your users with Amazon Pinpoint campaigns\.

Unlike the dynamic segments that you create with the segment builder in the console, an imported segment is an unchanging set of *endpoints* or *users IDs*: 

**Endpoint**  
A destination that you can send messages to — such as an email address, mobile device identifier, or mobile phone number\. An endpoint definition can include attributes that describe the user or device that you send messages to\. It can also include a user ID\.   
You can define a segment by importing a list of endpoint definitions\. Amazon Pinpoint creates the segment, and it updates any endpoints that you previously added to Amazon Pinpoint with the new information\.

**User ID**  
An ID that represents an individual user in your audience\. This ID must be assigned to one or more endpoints\. For example, if a person uses your app on more than one device, your app could assign that person's user ID to the endpoint for each device\.  
You can define a segment by importing user IDs only if you've added the endpoints that are associated with the user IDs to Amazon Pinpoint\.

An imported segment consists of endpoints, user IDs, or a combination of both\. When you use Amazon Pinpoint to send a message to the segment, the potential destinations include:
+ Each endpoint that you list in the imported file\.
+ Each endpoint that's associated with each user ID that you list in the imported file\.

To import a file, you first upload it to an Amazon Simple Storage Service \(Amazon S3\) bucket\. Next, you provide Amazon Pinpoint with the name of the Amazon S3 bucket that contains the file\. Amazon Pinpoint retrieves the file from Amazon S3 and adds each endpoint or user ID in the file to a segment\.

## Segment Files<a name="segments-importing-examples"></a>

You define the endpoints or user IDs that belong to your segment in a comma\-separated values \(CSV\) or JSON file\. Then, you import the file into Amazon Pinpoint to create the segment\.

When you import a segment, remember the following:
+ If you're importing new endpoints, the `Address` and `ChannelType` attributes are required\.
+ If you're updating existing endpoints, the `Id` attribute is required for each endpoint that you want to update\.
+ Amazon Pinpoint can't import compressed files\.
+ The files that you import must use UTF\-8 character encoding\.
+ Your endpoint definitions can only include certain attributes\. For a list, see [Available Attributes](#segments-importing-available-attributes)\.

### Example Segment Files<a name="segments-importing-examples"></a>

The example files in this section are based on the following data:


**Example Endpoint Attribute Values**  

| ChannelType | Address | Location\.Country | Demographic\.Platform | Demographic\.Make | User\.UserId | 
| --- | --- | --- | --- | --- | --- | 
| SMS | \+12365550182 | CAN | Android | LG | example\-user\-id\-1 | 
| APNS | 1a2b3c4d5e6f7g8h9i0j1a2b3c4d5e6f | USA | iOS | Apple | example\-user\-id\-2 | 
| EMAIL | john\.stiles@example\.com | USA | iOS | Apple | example\-user\-id\-2 | 
| GCM | 4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c | CHN | Android | Google | example\-user\-id\-3 | 
| EMAIL | wang\.xiulan@example\.com | CHN | Android | OnePlus | example\-user\-id\-3 | 

Each row in this table represents an individual endpoint\. Note that the user IDs example\-user\-id\-2 and example\-user\-id\-3 are assigned to two endpoints each\.

**Example File with Endpoint Definitions**  
You can import endpoints that are defined in a CSV file, as in the following example:  

```
ChannelType,Address,Location.Country,Demographic.Platform,Demographic.Make,User.UserId
SMS,2065550182,CAN,Android,LG,example-user-id-1
APNS,1a2b3c4d5e6f7g8h9i0j1a2b3c4d5e6f,USA,iOS,Apple,example-user-id-2
EMAIL,john.stiles@example.com,USA,iOS,Apple,example-user-id-2
GCM,4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c,CHN,Android,Google,example-user-id-3
EMAIL,wang.xiulan@example.com,CHN,Android,OnePlus,example-user-id-3
```
The first line is the header, which contains the endpoint attributes\. For the supported attributes, see [Available Attributes](#segments-importing-available-attributes)\.  
The subsequent lines define the endpoints by providing values for each attribute in the header\.  
To include a comma, line break, or double quote in a value, enclose the value in double quotes, as in `"aaa,bbb"`\. For more information about the CSV format, see [RFC 4180 Common Format and MIME Type for Comma\-Separated Values \(CSV\) Files](https://tools.ietf.org/html/rfc4180)\.
You can import endpoints that are defined in a newline\-delimited JSON file\. In this format, each line is a complete JSON object that contains an individual endpoint definition, as in the following example:  

```
{"ChannelType":"SMS","Address":"2065550182","Location":{"Country":"CAN"},"Demographic":{"Platform":"Android","Make":"LG"},"User":{"UserId":"example-user-id-1"}}
{"ChannelType":"APNS","Address":"1a2b3c4d5e6f7g8h9i0j1a2b3c4d5e6f","Location":{"Country":"USA"},"Demographic":{"Platform":"iOS","Make":"Apple"},"User":{"UserId":"example-user-id-2"}}
{"ChannelType":"EMAIL","Address":"john.stiles@example.com","Location":{"Country":"USA"},"Demographic":{"Platform":"iOS","Make":"Apple"},"User":{"UserId":"example-user-id-2"}}
{"ChannelType":"GCM","Address":"4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c","Location":{"Country":"CHN"},"Demographic":{"Platform":"Android","Make":"Google"},"User":{"UserId":"example-user-id-3"}}
{"ChannelType":"EMAIL","Address":"wang.xiulan@example.com","Location":{"Country":"CHN"},"Demographic":{"Platform":"Android","Make":"OnePlus"},"User":{"UserId":"example-user-id-3"}}
```
For the supported attributes, see [Available Attributes](#segments-importing-available-attributes)\.

**Example File with User IDs**  
You can also import user IDs that are listed in a CSV file, as in the following example:  

```
User.UserId
example-user-id-1
example-user-id-2
example-user-id-3
```
The first line is the header, which must contain only the `User.UserId` attribute\.  
The subsequent lines list each user ID that belongs to the segment\.  
As you can see in the example endpoint definitions, the user ID `example-user-id-1` is associated with one endpoint\. The user IDs `example-user-id-2` and `example-user-id-3` are associated with two endpoints each\. Therefore, the segment that's created by importing this file could be used to message up to five endpoints\.
You can also import user IDs that are listed in a newline\-delimited JSON file, as in the following example:  

```
{"User":{"UserId":"example-user-id-1"}}
{"User":{"UserId":"example-user-id-2"}}
{"User":{"UserId":"example-user-id-3"}}
```
As you can see in the example endpoint definitions, the user ID `example-user-id-1` is associated with one endpoint\. The user IDs `example-user-id-2` and `example-user-id-3` are associated with two endpoints each\. Therefore, the segment that's created by importing this file could be used to message up to five endpoints\.

## Uploading Segment Files to Amazon S3<a name="segments-importing-addtos3"></a>

Amazon S3 is an AWS service that provides highly scalable cloud storage\. Amazon S3 stores data as objects within buckets, and those objects can be grouped into folders\.

Before you import a segment, you must create an S3 bucket and upload your file to that bucket\. You can organize the files for different segments into separate folders\. When Amazon Pinpoint imports the endpoints or user IDs for a segment, it includes the files within all folders and subfolders that belong to the Amazon S3 location you specify\.

For an introduction to creating buckets and uploading objects, see the [Amazon Simple Storage Service Getting Started Guide](http://docs.aws.amazon.com/AmazonS3/latest/gsg/)\.

Amazon Pinpoint can import the following types of files:
+ CSV
+ Newline\-delimited JSON

Amazon Pinpoint can import only one of these formats per segment, so the Amazon S3 path you specify should only contain one format type\.

## Importing a Segment<a name="segments-importing-procedure"></a>

You can create a segment by importing the segment's endpoints or user IDs from Amazon S3\.

**To import a segment**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project that you want to add the segment to\.

1. In the navigation menu, choose **Segments**\. The **Segments** page opens, which displays previously defined segments and the number of active users that belong to them\.

1. Choose **New segment**\.

1. For **Segment name**, type a name for your segment to make it easy to recognize later\.

1. For **How would you like to define your segment**, choose **Import segment**\.  
![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_import.png)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. For **Amazon S3 URL**, type the location of the Amazon S3 bucket that contains the file for your segment\. The address of the bucket must be in the following format:

   ```
   s3://bucket-name/folder-name
   ```

   Amazon Pinpoint imports the files from the path that you specify, and from any subfolders in that path\.

1. For **IAM role**, complete one of the following steps:
   + If you want to have Amazon Pinpoint create a role that allows it to read from an Amazon S3 bucket, choose **Automatically create a role**\. Then, for **Name for new role**, type a name for the role that you're creating\.
   + If you've already created an IAM role that allows Amazon Pinpoint to read from an Amazon S3 bucket, choose **Choose a role from your account**\. Then, for **Role**, choose a role that contains the appropriate permissions\.

   If you want to create the IAM role yourself, see [IAM Role for Importing Segments](http://docs.aws.amazon.com/pinpoint/latest/developerguide/permissions-import.html) in the *Amazon Pinpoint Developer Guide*\. After you create the role, specify it in the Amazon Pinpoint console\.

1. For **What is the format of the file**, choose either **CSV** or **JSON**, depending on the format of your file\.

1. Choose **Import Segment**\. Amazon Pinpoint imports the endpoints and user IDs from the specified Amazon S3 bucket and adds them to your segment\.

   The **Jobs** page provides the status of your import\. Refresh your browser to see the current status\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/segments_job.png)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

## Available Attributes<a name="segments-importing-available-attributes"></a>

The table in this section provides the attributes that you can specify in the endpoint definitions that you import into Amazon Pinpoint\. If you import segments using CSV files, the headers in the file should match the names shown in the **Attributes** column\.

For JSON files, a period in the attribute name indicates that the name following the period is an object that's nested in a parent object with a name equal to the value preceding the period\. For example, a JSON file that contains the `Demographic.Make` and `Demographic.Model` attributes has the following structure:

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

The full JSON structure closely resembles the [Example EndpointRequest](http://docs.aws.amazon.com/pinpoint/latest/apireference/rest-api-endpoint.html#rest-api-endpoint-schemas-requests) in the *Amazon Pinpoint API Reference*\. However, not all attributes in the EndpointRequest schema are supported when you import segments, including `EndpointStatus` and `EffectiveDate`\.

You can replace attribute names that are shown in italics with any value\. For example, you can create custom attributes called `User.UserAttributes.FirstName` and `User.UserAttributes.LastName`\.


| Attribute | Description | 
| --- | --- | 
| Address | The unique destination of the endpoint, such as an email address, a mobile phone number, or a token for mobile push notifications\. | 
| Attributes\.custom\_attribute | Custom attributes that your app reports to Amazon Pinpoint\. You can use these attributes as selection criteria when you create a segment\. You can replace custom\_attribute with any value\. You can specify up to 20 custom attributes per endpoint\. | 
| ChannelType | The channel type of the endpoint\. Acceptable values: GCM, APNS, SMS, or EMAIL\. | 
| Demographic\.AppVersion | The version number of the application that's associated with the endpoint\. | 
| Demographic\.Locale | The locale of the endpoint in ISO 15897 format\. For example, en\_US \(English language locale for the United States\) or zh\_CN \(Chinese locale for China\)\. | 
| Demographic\.Make | The manufacturer of the endpoint device, such as Apple or Samsung\. | 
| Demographic\.Model | The model of the endpoint device, such as iPhone\. | 
| Demographic\.ModelVersion | The model version of the endpoint device\. | 
| Demographic\.Platform | The operating system of the endpoint device, such as ios or android\. | 
| Demographic\.PlatformVersion | The platform version of the endpoint device\. | 
| Demographic\.Timezone | The time zone of the endpoint\. It's specified as a [tz database value](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones), such as America/Los\_Angeles\. | 
| EffectiveDate | The time at which the endpoint was last updated, in [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601)\. For example, 20171011T150548Z\. | 
| Id | The unique ID of the endpoint\. | 
| Location\.City | The city where the endpoint is located\. | 
| Location\.Country | The three\-letter code for the country or region where the endpoint is located, in ISO 3166\-1 alpha\-3 format\. For example, USA \(United States\) or CHN \(China\)\. For a complete list of ISO 3166\-1 alpha\-3 abbreviations, see the [ISO website](https://www.iso.org/obp/ui/#search/code/)\. | 
| Location\.Latitude | The latitude of the endpoint location, rounded to one decimal place\. | 
| Location\.Longitude | The longitude of the endpoint location, rounded to one decimal place\. | 
| Location\.PostalCode | The postal or ZIP code of the endpoint\. | 
| Location\.Region | The region of the endpoint location, such as a state or province\. | 
| Metrics\.custom\_attribute | Custom metrics, such as the number of sessions or number of items left in a cart, to use for segmentation purposes\. You can replace custom\_attribute with any value\. You can specify up to 20 custom attributes per endpoint\.These custom values can only be numeric\. Because they're numeric, Amazon Pinpoint can perform arithmetic operations, such as the average or sum, on them\. | 
| OptOut | Indicates whether a user has opted out of receiving messages\. Acceptable values: ALL \(the user has opted out of all messages\) or NONE \(the user hasn't opted out and receives all messages\)\. | 
| RequestId | The unique ID of the most recent request to update the endpoint\. | 
| User\.UserAttributes\.custom\_attribute | Custom attributes that are specific to the user\. You can replace custom\_attribute with any value, such as FirstName or Age\. You can specify up to 20 custom attributes per endpoint\. | 
| User\.UserId | The unique ID of the user\. | 

**Note**  
You can specify up to 20 custom attributes per endpoint for `Attributes`, `Metrics` and `User.UserAttributes`\. However, you can create no more than 40 custom attributes per AWS account\.