# Managing Segments<a name="segments-managing"></a>

You can use the Amazon Pinpoint console to create new segments, update the settings for existing segments, duplicate segments, delete segments, and more\.

**To manage a segment**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. On the **Projects** page, choose the project that you want to manage segments for\.

1. On the navigation menu, choose **Segments**\.

1. On the **Segments** page, choose the segment that you want to manage\.

On the **Segment** page, for a segment that's built from segmentation criteria, you can do the following:

+ **Create campaign** – Create a campaign that uses the segment you're managing\.

+ **Copy to new** – Copy the segment to use its settings as a template for a new segment, in which you can change or keep any of the original settings\.

+ **Edit segment** – Change any of the segment's settings, such as the segmentation criteria that define which users belong to the segment\.

+ **Delete segment** – Remove the segment from Amazon Pinpoint\. The segment becomes unavailable for future campaigns, but preexisting campaigns that use the segment are unaffected\.

For an imported segment, you can do the following:

+ **Create campaign** – Create a campaign that uses the segment you're managing\.

+ **Reimport segment** – Update the segment with the endpoint files that are currently stored in the Amazon S3 location that you originally imported the segment from\.

+ **Delete segment** – Remove the segment from Amazon Pinpoint\. The segment becomes unavailable for future campaigns, but preexisting campaigns that use the segment are unaffected\.