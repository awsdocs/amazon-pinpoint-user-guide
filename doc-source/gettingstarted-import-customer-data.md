# Step 2: Import customer data and create a segment<a name="gettingstarted-import-customer-data"></a>

A *segment* is a group of your customers that share certain attributes\. For example, a segment might contain all of your customers who use version 2\.0 of your app on an Android device, or all customers who live in the city of Los Angeles\.

When you create a campaign, you have to choose a segment to send the campaign to\. You can send multiple campaigns to a single segment, and you can send a single campaign to multiple segments\.

There are two types of segments that you can create in Amazon Pinpoint:
+ **Dynamic segments** – Segments that are based on attributes that you define\. Dynamic segments can change over time\. For example, if you add new endpoints to Amazon Pinpoint, or if you modify or delete existing endpoints, the number of endpoints in that segment may increase or decrease\. For more information about dynamic segments, see [Building segments](segments-building.md)\.
+ **Imported segments** – Segments that are created outside of Amazon Pinpoint and saved in CSV or JSON format\. Imported segments are static—that is, they never change\. When you create a new segment, you can use an imported segment as a base segment, and then refine it by adding filters\. For more information about importing segments, see [Importing segments](segments-importing.md)\.

In this tutorial, you create an imported segment by uploading a file from your computer\. Next, you create a dynamic segment that is based upon the imported segment\.

## Step 2\.1: Download and modify the sample file<a name="gettingstarted-import-customer-data-download-sample-file"></a>

In this section, you download a file that contains fictitious customer data\. You also modify the data to include your own contact information\. Later in this tutorial, you use this data to create a segment\.

1. In a web browser, download the sample file from [https://raw\.githubusercontent\.com/awsdocs/amazon\-pinpoint\-user\-guide/main/examples/Pinpoint\_Sample\_Import\.csv](https://raw.githubusercontent.com/awsdocs/amazon-pinpoint-user-guide/main/examples/Pinpoint_Sample_Import.csv)\. Save the file to your computer\.
**Tip**  
You can quickly save this file to your computer by right\-clicking the link, and then choosing **Save Link As**\.

1. Open the file in a spreadsheet application\. On the last row of the file, replace the items in angle brackets \(`<…>`\) with your own contact information\.

   In the `Address` column, enter the same email address that you verified in [Step 1](gettingstarted-create-project.md)\. The message that you send in this campaign will be sent to that address\.

1. When you finish, save the file\.
**Note**  
If you used a spreadsheet application to modify the file, make sure that you save the modified file in Comma\-Separated Values \(\.csv\) format\. Amazon Pinpoint can't import proprietary file formats, such as \.xlsx\.

## Step 2\.2: Import the sample customer data file<a name="gettingstarted-import-customer-data-import-segment"></a>

Now that you have a file that contains customer data, you can import it into Amazon Pinpoint\. To import customer data, you have to create a new segment\.

**To create an imported segment**

1. In the Amazon Pinpoint console, in the navigation pane, choose **Segments**\.

1. Choose **Create a segment**\.

1. On the **Create a segment** page, choose **Import a segment**\.

1. In the **Specifications** section, under **Import method**, choose **Upload files from your computer**\.

1. Select **Choose files**\. Navigate to the `Pinpoint_Sample_Import.csv` file that you downloaded and modified in the previous section\.

1. Choose **Create segment**\. Amazon Pinpoint copies the file from your computer and creates a segment\. Wait for about 1 minute while the import completes\. 

## Step 2\.3: Create a targeted segment<a name="gettingstarted-import-customer-data-create-targeted-segment"></a>

Your Amazon Pinpoint project now contains some customer data, as well as a segment that contains your entire customer list\. It also contains your contact information\.

In this section, you create a targeted segment\. You add segment criteria that filter the segment so that you're the only member of the segment\.

**To create the segment**

1. On the **Segments** page, choose **Create a segment**\. 

1. On the **Create a segment** page, choose **Build a segment**\.

1. For **Name**, enter a name for the segment\.

1. Under **Segment group 1**, do the following:

   1. Next to **Include audiences that are in any of the following**, choose the **Pinpoint\_Sample\_Import** segment that you created in the previous step\.

   1. Choose **Add criteria**\.

   1. From the menu under **Attribute**, choose **Channel Types > Email**\.

   1. Choose **Add filter**\.

   1. In the new menu that appears in the **Attribute** column, choose **Custom User Attributes > Company**\. Next, in the **Operator** column, choose **Is**\. Finally, in the **Values** column, enter the unique company name that you specified for your own contact record in [Step 2\.1](#gettingstarted-import-customer-data-download-sample-file)\.

   1. Choose **Create segment**\.

**Next:** [Create and schedule a campaign](gettingstarted-create-campaign.md)
