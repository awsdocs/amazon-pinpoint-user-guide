# 10DLC<a name="settings-sms-10dlc"></a>

If you use Amazon Pinpoint to send messages to recipients in the United States, you can use 10DLC phone numbers to deliver those messages\. The abbreviation *10DLC* stands for "10\-digit long code\." A 10DLC phone number is registered for use by a single sender and for a single use case\. This registration process gives the mobile carriers insight into the approved use cases for each phone number that is used to send messages\. As a result, 10DLC phone numbers can offer high throughput and deliverability rates\.

A message that you send from a 10DLC phone number appears on the devices of your recipients as a 10\-digit phone number\. You can use 10DLC phone numbers to send both transactional and promotional messages\. If you already use short codes or toll\-free numbers to send your messages, then you don't need to set up 10DLC\.

To set up 10DLC, you first register your company or brand\. Next, you create a *10DLC campaign*, which is a description of your use case\. This information is then shared with the Campaign Registry, an industry organization that collects 10DLC registration information\.

**Note**  
For more information about how the Campaign Registry uses your information, see the FAQ on the [Campaign Registry website](https://www.campaignregistry.com/faq/)\.

After your company and 10DLC campaign are approved, you can purchase a phone number and associate it with your 10DLC campaign\. Associating a phone number with a 10DLC campaign can take approximately 14 days to complete\. Although you can associate multiple phone numbers with a single campaign, you can't use the same phone number across multiple 10DLC campaigns\. For each 10DLC campaign that you create, you must have at least one unique phone number\. Throughput for 10DLC phone numbers is based on the company and campaign registration information that you provide\. Associating multiple phone numbers with a 10DLC campaign doesn't provide any additional throughput\.

If you have an existing unregistered long code in your Amazon Pinpoint account, you can request that it be converted to a 10DLC number\. To convert an existing long code, complete the registration process, and then create a case in the AWS Support Center\. In some situations, it isn't possible to convert an unregistered long code to a 10DLC phone number\. In this case, you must request a new number through the Amazon Pinpoint console and associate it with your 10DLC campaign\. For more information about using 10DLC with existing long codes, see [Associating an existing long code with a 10DLC campaignUsing an existing long code with 10DLC](settings-sms-10dlc-associate-long-code.md)\.

## 10DLC capabilities<a name="settings-sms-10dlc-capabilities"></a>

The capabilities of 10DLC phone numbers depend on which mobile carriers your recipients use\. AT&T provides a limit on the number of message parts that can be sent each minute for each campaign\. T\-Mobile provides a daily limit of messages that can be sent for each company, with no limit on the number of message parts that can be sent per minute\. Verizon hasn't published throughput limits, but uses a filtering system for 10DLC that is designed to remove spam, unsolicited messages, and abusive content, with less emphasis on the actual message throughput\.

New 10DLC campaigns that are associated with *unvetted* companies can send 75 message parts per minute to recipients who use AT&T, and 2,000 messages per day to recipients who use T\-Mobile\. The company limit is shared across all of your 10DLC campaigns\. For example, if you have registered one company and two campaigns, the daily allotment of 2,000 messages to T\-Mobile customers is shared across those campaigns\. Similarly, if you register the same company in more than one AWS account, the daily allotment is shared across those accounts\.

If your throughput needs exceed these limits, you can request that your company registration be vetted\. When you vet your company registration, a third\-party verification provider analyzes your company details\. The verification provider then provides a vetting score, which determines the capabilities of your 10DLC campaigns\. There is a one\-time charge for the vetting service\. For more information, see [Vetting your 10DLC registration](settings-sms-10dlc-register-company.md#settings-sms-10dlc-register-company-vetting)\.

Your actual throughput rate will vary depending on various factors, such as whether or not your company has been vetted, your campaign types, and your vetting score\. The following flowchart shows the throughput rates for various situations\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/settings-sms-10dlc-capabilities.png)

Throughput rates for 10DLC are determined by the US mobile carriers in cooperation with the Campaign Registry\. Neither Amazon Pinpoint nor any other SMS sending service can increase 10DLC throughput beyond these rates\. If you need high throughput rates and high deliverability rates across all US carriers, we recommend that you use a short code\. For more information about obtaining a short code, see [Requesting short codes for SMS messaging with Amazon Pinpoint](channels-sms-awssupport-short-code.md)\. 

## Setting up 10DLC<a name="settings-sms-10dlc-setup"></a>

You can set up 10DLC directly in the Amazon Pinpoint console\. To set up 10DLC, you must complete all of the following steps\.

1. **Register your company**

   The first step in setting up 10DLC is to register your company or brand\. For information about company registration, see [Registering a company or brand for use with 10DLC](settings-sms-10dlc-register-company.md)\. There is a one\-time registration fee to register your company\. This fee is shown on the registration page\.

1. **\(Optional, but recommended\) Apply for vetting**

   If your company registration is successful, you can begin creating low\-volume, mixed\-use 10DLC campaigns\. These campaigns can send 75 messages per minute to recipients who use AT&T, and your registered company can send 2,000 messages per day to recipients who use T\-Mobile\. If your use case requires a throughput rate that exceeds these values, you can apply for vetting of your company registration\. Vetting your company registration can increase the throughput rates for your companies and campaigns, but it isn't guaranteed to do so\. For more information about vetting, see [Vetting your 10DLC registration](settings-sms-10dlc-register-company.md#settings-sms-10dlc-register-company-vetting)\.

1. **Register your campaign**

   If the Campaign Registry is able to verify the company information that you provided, you can create a 10DLC campaign\. A 10DLC campaign contains information about your use case\. Each 10DLC campaign can be associated with one company\. Amazon Pinpoint sends this campaign information to the Campaign Registry for approval\. In most cases, 10DLC campaign approval is instantaneous\. In some cases, the Campaign Registry may require additional information\. For more information, see [Registering a 10DLC campaign](settings-sms-10dlc-register-campaign.md)\. You're charged a recurring monthly fee for each 10DLC campaign that you register\. The monthly fee varies depending on your use case\. The recurring fee for your campaign is shown on the registration page\.

1. **Request your 10DLC number**

   After your 10DLC campaign is approved, you can request a phone number and associate that number with the approved 10DLC campaign\. Each phone number can only be associated with a single 10DLC campaign\. For more information, see [Requesting a number](settings-sms-request-number.md)\. There is a monthly recurring fee for leasing the phone number\. This fee is shown on the purchase page\.

## 10DLC registration and monthly fees<a name="settings-sms-10dlc-fees"></a>

There are registration and monthly fees associated with using 10DLC, such as registering your company and 10DLC campaign\. These are separate from any other monthly or AWS fees\. For more information about 10DLC fees, see the [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/) page\.