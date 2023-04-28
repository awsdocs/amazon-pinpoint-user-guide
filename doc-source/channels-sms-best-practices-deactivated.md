# Handling deactivated phone numbers<a name="channels-sms-best-practices-deactivated"></a>

A deactivated phone number means the mobile subscriber has terminated their service or transferred their phone number to a different mobile network provider\. Eventually, deactivated numbers are recycled and reassigned to new subscribers\. Therefore, it’s possible to mistakenly send an SMS message to a phone number that now belongs to a different subscriber who has not opted in to your SMS message program\.

Mobile network providers frequently publish deactivation reports that contain a current list of deactivated phone numbers in their networks\. These reports are published to help keep your SMS sending list current and in compliance\.

**Note**  
Many of the mobile phone numbers on deactivation reports are numbers that have been transferred to a different mobile network provider by the subscriber\. Changing mobile network providers requires an opt\-in from the new mobile network provider\. There is a risk of removing a deactivated number that your end user believes should still receive messages\. You can engage with your end users through different channels \(email or voice calls\) if you find their phone number is deactivated\.

## Why is this important?<a name="channels-sms-best-practices-deactivated-why"></a>

In the US, the Federal Communications Commission \(FCC\) considers sending messages to a phone number that belongs to a subscriber who has not opted in to your projects as spam\. This stance can result in end\-user and mobile network provider complaints, which can then lead to audits, and put your SMS message sending at risk of being entirely blocked by mobile network providers\. In the worst\-case scenarios, the FCC can impose fines, or you may be subject to a class action lawsuit\.

Additionally, when you send SMS messages through Amazon Pinpoint, you're billed for each message you send\. By keeping your end\-users lists up to date, you can prevent charges on unnecessary messages\.

Amazon Pinpoint provides a copy of the deactivation reports to allow you to keep your end\-users lists up to date periodically\. These reports originate from mobile network providers and are processed daily\. Each report contains a list of phone numbers that have been deactivated on the mobile network provider networks and should be downloaded and compared to your existing end\-users list\. Delete all phone numbers from your end\-users lists that have been deactivated\.

For more information on managing your existing end\-users lists, see [ Deleting endpoints from Amazon Pinpoint ](https://docs.aws.amazon.com/pinpoint/latest/developerguide/audience-define-remove.html) and [ Managing opt\-out lists ](https://docs.aws.amazon.com/pinpoint/latest/developerguide/sms-voice-v2-opt-out-lists.html#sms-voice-v2-opt-out-lists-putting-destination-ids) in the *Amazon Pinpoint Developer Guide*\.

## Requesting deactivation reports<a name="channels-sms-best-practices-deactivated-request"></a>

Before you can obtain a copy of a deactivation report, you must first request a deactivation report through an Amazon S3 GET OBJECT API request using the REQUESTER PAYS buckets option to download a file\. For more information on Requester Pays buckets, see [ Downloading objects in Requester Pays buckets ](https://docs.aws.amazon.com/AmazonS3/latest/userguide/ObjectsinRequesterPaysBuckets.html) in the *[Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/)*\.

You pay for requests made against S3 buckets and objects requiring the requester pays option\. S3 request costs are based on the request type, and are charged on the quantity of requests\. For more information on S3 request costs, see [Amazon S3 pricing](https://aws.amazon.com/s3/pricing/)\.

**Note**  
The deactivation reports only retrieve United States phone numbers\.

Amazon Pinpoint provides two types of deactivation reports\. For ease of use, if you want the most recent deactivation report, you can submit a request using the latest object format\. If you want a deactivation report for a specific date, you can submit a request using the date specific object format\.

**Note**  
Amazon Pinpoint only stores the last 90 days of date specific objects\.

You can use the following template example to request a deactivation report\.

`Bucket name format: {region}-pinpoint-sms-voice/ `

`Latest object format: /sms-deact-reports/{iso2}/latest-deact-report.csv`

`Date specific object format: /sms-deact-reports/{iso2}/{YYYY}-{MM}-{DD}-deact-report.csv`

To connect programmatically to an AWS service, you use an endpoint\. You want to replace \{region\} with your regional endpoint\. For a list of supported Amazon Pinpoint regions for bucket name, see [ Amazon Pinpoint endpoints and quotas ](https://docs.aws.amazon.com/general/latest/gr/pinpoint.html) in the *AWS General Reference*\.

The following example shows you how to request the latest deactivation report using AWS CLI command\.

`aws s3api get-object --bucket us-east-1-pinpoint-sms-voice --key sms-deact-reports/us/latest-deact-report.csv OUTFILE.csv --request-payer requester`

The following example shows you how to request a date\-specific deactivation report using AWS CLI command\.

`aws s3api get-object --bucket us-east-1-pinpoint-sms-voice --key sms-deact-reports/us/2022-09-28-deact-report.csv OUTFILE.csv --request-payer requester`

After the Amazon S3 GET OBJECT API request is submitted, the deactivation report is downloaded to the OUTFILE\.csv specified in the command\.

Using the Amazon S3 API, you can get a list of deactivation reports\. You can list the deactivation reports only within the embeded `sms-deact-reports/us/` folder\.

The following example shows you how to get the list of deactivation reports available\.

`aws s3api list-objects-v2 --bucket us-east-1-pinpoint-sms-voice --prefix "sms-deact-reports/us/" --request-payer requester`