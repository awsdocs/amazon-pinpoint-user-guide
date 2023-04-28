# Tracking open and click events in email<a name="channels-email-open-click-tracking"></a>

Amazon Pinpoint automatically tracks how many of your emails were opened or clicked by their recipients\. In order to track the number of opens and clicks, Amazon Pinpoint makes minor changes to the emails that you send\.

First, Amazon Pinpoint adds a tiny, transparent image to the end of each email that you send\. This image is hosted on an AWS server\. The file name of this image is unique for each recipient\. When a recipient opens an email, their email client downloads this file from our servers\. When an email client downloads a tracking image from our servers, we count it as an open event\.

Second, Amazon Pinpoint replaces all links in your emails with links that refer to a domain that is hosted by AWS\. This link includes a parameter that is unique for each recipient\. When a recipient clicks one of these links, they are first sent to the AWS\-hosted domain, and then immediately redirected to their intended destination\. When a recipient visits one of these redirect links, we count it as a click event\.

If a message recipient clicks multiple links in a message or clicks the same link more than once, those clicks will be counted as one click if they occur within the same hour\. Multiple clicks taking place at different hours will be counted as separate clicks\. For example, a link is clicked at 8:30 AM and 8:45 AM it will count as one click but if the link is clicked at 8:30 AM and 9:05 AM it will count as two clicks because the hour has changed\. Email opens are counted the same way as clicks\.

In order to view open and click events, you have to set up event streaming\. For more information about creating event streams, see [Event stream settings](settings-event-streams.md)\.

**Note**  
If you have event streaming enabled you will still receive duplicate events and should handle such duplicates in your workflows accordingly\.