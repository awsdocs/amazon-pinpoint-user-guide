# Importing Segments<a name="segments-importing"></a>

With Amazon Pinpoint, you can define a user segment by importing information about the users who belong to the segment\.

Importing segments is useful if you have segments for your users outside of Amazon Pinpoint but you want to engage your users with Amazon Pinpoint campaigns\.

Unlike the dynamic segments that you create with the segment builder in the console, an imported segment is an unchanging set of *endpoints*\. Each endpoint represents a point of interaction for a user of your application\. When Amazon Pinpoint sends a message to the segment, it sends the message to each of the endpoints in that segment\.

To import a file, you first upload it to an Amazon Simple Storage Service \(Amazon S3\) bucket\. Next, you create an AWS Identity and Access Management \(IAM\) role that gives Amazon Pinpoint permission to access your Amazon S3 bucket\. Finally, you provide Amazon Pinpoint with the name of the Amazon S3 bucket in which you uploaded the file\. Amazon Pinpoint retrieves the file from Amazon S3 and adds each endpoint in the file to a segment\.

## Creating Endpoint Files<a name="segments-importing-examples"></a>

You can define one or more endpoints in a CSV or newline\-delimited JSON file, and then import that file into Amazon Pinpoint to create a segment\.

When you import segments, consider the following:

+ If you are importing new endpoints, the `Address` and `ChannelType` attributes are required\.

+ If you are updating existing endpoints, the `Id` attribute is required for each endpoint that you want to update\.

+ Amazon Pinpoint cannot import compressed files\.

+ The files that you import must use UTF\-8 character encoding\.

+ Your endpoint definitions may only include certain attributes\. For a list, see [Available Attributes](#segments-importing-available-attributes)\.

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

Amazon Pinpoint can import endpoints contained in the following types of files:

+ Newline\-delimited JSON

+ Comma\-separated values \(CSV\)

Amazon Pinpoint can import only one of these formats per segment, so the Amazon S3 path you specify should only contain one format type\.

## Creating an IAM Role for Importing<a name="segments-importing-iamrole"></a>

By default, Amazon Pinpoint does not have access to your S3 bucket\. Before you can import endpoints for a segment, create an IAM role that allows Amazon Pinpoint to get the endpoints from Amazon S3\.

**To create the IAM role**

1. Sign in to the AWS Management Console and open the IAM console at [https://console\.aws\.amazon\.com/iam/](https://console.aws.amazon.com/iam/)\.

1. In the navigation pane, choose **Roles**, and then choose **Create role**\.

1. Under **Select type of trusted entity**, choose **Another AWS account**\.

1. Under **Specify accounts that can use this role**, for **Account ID**, type your AWS account ID\. For more information about obtaining your AWS account ID, see [Your AWS Account ID and Its Alias](http://docs.aws.amazon.com/IAM/latest/UserGuide/console_account-alias.html)\.

   Choose **Next: Permissions**\.

1. On the **Attach permissions policies** page, select the **AmazonS3ReadOnlyAccess** policy, and then choose **Next: Review**\.
**Tip**  
Use the search box to quickly find the correct policy\.  
![\[The AmazonS3ReadOnly AWS managed policy is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The AmazonS3ReadOnly AWS managed policy is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The AmazonS3ReadOnly AWS managed policy is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. On the **Review** screen, for **Role name**, type a name for the role\. You can optionally type a description of the role in the **Description** field\. When you finish, choose **Create**\.

1. In the list of roles, choose the role that you created\.

1. On the **Trust relationships** tab, choose **Edit trust relationship**\. The **Edit Trust Relationship** page opens with the access control policy in the editor\.

1. For the `Principal` object in your access control policy, replace:

   ```
   "AWS": "arn:aws:iam::your-account-id:root"
   ```

   With:

   ```
   "Service": "pinpoint.us-east-1.amazonaws.com"
   ```

   The complete trust policy should be the following:

   ```
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Effect": "Allow",
         "Principal": {
           "Service": "pinpoint.us-east-1.amazonaws.com"
         },
         "Action": "sts:AssumeRole",
         "Condition": {}
       }
     ]
   }
   ```

   Choose **Update Trust Policy**\.

1. On the role details page, note the value shown next to **Role ARN**\. You will provide this value when you import the endpoints for a segment\.  
![\[The role ARN in the IAM role details page.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The role ARN in the IAM role details page.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The role ARN in the IAM role details page.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

## Importing a Segment<a name="segments-importing-procedure"></a>

You can create a segment by importing the segment's endpoints from Amazon S3\.

**To import a segment**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project to which you want to add the segment\.

1. In the navigation menu, choose **Segments**\. The **Segments** page opens, which displays previously defined segments and the number of active users that belong to them\.

1. Choose **New segment**\.

1. For **Segment name**, type a name for your segment to make it easy to recognize later\.

1. For **How would you like to define your segment**, choose **Import segment**\.  
![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

1. For **Amazon S3 URL**, type the Amazon S3 location that contains the endpoints for your segment\. The URL should follow this format:

   ```
   s3://bucket-name/folder-name
   ```

   Amazon Pinpoint imports endpoints from the path you specify, and from any subfolders in that path\.

1. For **IAM role ARN** specify the Amazon Resource Name \(ARN\) of the IAM role that you created to grant Amazon Pinpoint access to Amazon S3\.

1. For **What is the format of the file**, choose the format of your endpoint files in Amazon S3: either **CSV** or **JSON**\.

1. Choose **Import Segment**\. Amazon Pinpoint imports the endpoints from the specified Amazon S3 location and adds them to your segment\.

   The **Jobs** page provides the status of your import\. Refresh your browser to see the current status\.  
![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)![\[The Import segment button is selected.\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/)

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
| Address | The address of the endpoint, such as an email address, a mobile phone number, or a token for mobile push notifications\. | 
| Attributes\.custom\_attribute | Custom attributes that your app reports to Amazon Pinpoint\. You can use these attributes as selection criteria when you create a segment\. You can replace custom\_attribute with any value\. You can specify up to 20 custom attributes per endpoint\. | 
| ChannelType | The channel type\. Acceptable values: GCM, APNS, SMS, or EMAIL\. | 
| Demographic\.AppVersion | The version of the application associated with the endpoint\. | 
| Demographic\.Locale | The locale of the endpoint in ISO 15897 format\. For example, en\_US \(English language locale for the United States\) or zh\_CN \(Chinese locale for China\)\. | 
| Demographic\.Make | The manufacturer of the endpoint device, such as Apple or Samsung\. | 
| Demographic\.Model | The model of the endpoint device, such as iPhone\. | 
| Demographic\.ModelVersion | The model version of the endpoint device\. | 
| Demographic\.Platform | The operating system of the endpoint device, such as ios or android\. | 
| Demographic\.PlatformVersion | The platform version of the endpoint device\. | 
| Demographic\.Timezone | The timezone of the endpoint\. Specified as a [tz database value](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones), such as America/Los\_Angeles\. | 
| EffectiveDate | The time at which the endpoint was last updated, in [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601)\. For example, 20171011T150548Z\. | 
| EndpointStatus | The endpoint status\. Acceptable values: ACTIVE or INACTIVE\. The status is set to INACTIVE if a delivery fails\. It is set to ACTIVE if the address is updated\. | 
| Id | The unique ID of the endpoint\. | 
| Location\.City | The city in which the endpoint is located\. | 
| Location\.Country | The three\-letter country code for the country in which the endpoint is located, in ISO 3166\-1 alpha\-3 format\. For example, USA \(United States\) or CHN \(China\)\. For a complete list of ISO 3166\-1 alpha\-3 abbreviations, see [https://www\.iso\.org/obp/ui/\#search/code](https://www.iso.org/obp/ui/#search/code/)\. | 
| Location\.Latitude | The latitude of the endpoint location, rounded to one decimal place\. | 
| Location\.Longitude | The longitude of the endpoint location, rounded to one decimal place\. | 
| Location\.PostalCode | The postal or ZIP code of the endpoint\. | 
| Location\.Region | The region of the endpoint location, such as a state or province\. | 
| Metrics\.custom\_attribute | Custom metrics, such as number of sessions or number of items left in cart, to use for segmentation purposes\. You can replace custom\_attribute with any value\. You can specify up to 20 custom attributes per endpoint\.These custom values can only be numeric\. Because they are numeric, Amazon Pinpoint can perform arithmetic operations, such as average or sum, on them\. | 
| OptOut | Indicates whether a user has opted out of receiving messages\. Acceptable values: ALL \(user has opted out of all messages\) or NONE \(user has not opted out and receives all messages\)\. | 
| RequestId | The unique ID of the most recent request to update the endpoint\. | 
| User\.UserAttributes\.custom\_attribute | Custom attributes that are specific to the user\. You can replace custom\_attribute with any value, such as FirstName or Age\. You can specify up to 20 custom attributes per endpoint\. | 
| User\.UserId | The unique ID of the user\. | 

**Note**  
You can specify up to 20 custom attributes per endpoint for `Attributes`, `Metrics`, and `User.UserAttributes`\. However, you can create no more than 40 custom attributes across your entire Amazon Pinpoint account\.