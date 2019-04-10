# Managing Segments<a name="segments-managing"></a>

You can use the Amazon Pinpoint console to create, update, duplicate, and delete segments\. You can also use the segment page in the console to create campaigns that target existing segments\.

**To manage a segment**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **All projects** page, choose the project that contains the segments that you want to manage\.

1. In the navigation pane, choose **Segments**\.

1. In the list of segments, choose the segment that you want to manage\.

1.  On the **Actions** menu, choose one of the following options:
   + **View details** – Choose this option to show information about the segment, including the date and time when the segment was created, and the date and time when the segment was last updated\. When you view the details of a dynamic segment, you also see the approximate number of endpoints that meet the segment criteria, and the segment groups and filters that define the segment\. When you view the details of an imported segment, you see the number of records that were imported for the segment, the Amazon S3 location that the segment was imported from, as well as the name of the IAM role that was used to import the segment\.
   + **Edit** – Choose this option to modify the segment\. You can use this option with any type of segment to change the segment name\. When you edit a dynamic segment, you can change the segment groups that define the segment\. When you edit an imported segment, you can change the Amazon S3 location that the segment is imported from, as well as the IAM role that is used to import the segment\.
   + **Copy to new** – Choose this option to create a new segment that is a copy of the chosen segment\. You can modify all of the settings in the new segment to meet your requirements\.
   + **Delete** – Choose this option to delete the segment\. The segment becomes unavailable for future campaigns, but existing campaigns that use the segment are not affected\. 