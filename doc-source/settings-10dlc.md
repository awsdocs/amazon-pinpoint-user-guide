# 10DLC<a name="settings-10dlc"></a>

In the United States, unregistered long codes are designated only for Person\-to\-Person \(P2P\) messaging with low throughput\. The mobile carriers in the US don't support Application\-to\-Person \(A2P\) SMS messaging over unregistered long codes\.

If you use Amazon Pinpoint to send messages to recipients in the United States, you can use 10DLC phone numbers to deliver those messages, rather than using unregistered long codes\. The abbreviation 10DLC stands for "10\-digit long code\." A 10DLC phone number is registered for use by a single sender and for a single use case\. This registration process gives the mobile carriers insight into the approved use cases for each phone number that is used to send A2P messages\. As a result, 10DLC phone numbers can offer high throughput and deliverability rates\.

A message that you send from a 10DLC phone number appears on your recipients' devices as a 10\-digit phone number\. You can use 10DLC to send both transactional and promotional messages\. If you already use short codes or toll\-free numbers to send your messages, you don't need to set up 10DLC\.

To set up 10DLC, you first register your company or brand\. Next, you create a *10DLC campaign*, which is a description of your use case\. This information is then shared with The Campaign Registry, which is a third party that evaluates your registration information and returns a trust score\. After your company and 10DLC campaign are approved, you can purchase a phone number and associate it with your campaign\. Associating a phone number with a 10DLC campaign can take 7–10 days\. Although you can associate multiple phone numbers with a single campaign, you can't use the same phone number across multiple campaigns\. For each campaign you create, you need to have at least one unique phone number\.

**Note**  
For more information about how The Campaign Registry uses your information, see their [FAQ](https://www.campaignregistry.com/faq/) at [campaignregistry\.com](https://www.campaignregistry.com)\.

Amazon Pinpoint customers who have existing unregistered long codes can request that those long codes be enabled for 10DLC\. To do this, complete the registration process, and then create a case in the AWS Support Center\. In some situations, it may not be possible to enable a long code for 10DLC\. In this case, you need to request a new number through the Amazon Pinpoint console and associate it with your 10DLC campaign\. For more information about using 10DLC with existing long codes, see [Associating a long code with a 10DLC campaign](settings-associate-long-code-10dlc.md)\.

## 10DLC capabilities<a name="10dlc-capabilities"></a>

The capabilities of 10DLC phone numbers depend on the mobile carriers of your recipients\. AT&T provides a throughput limit based on the number of message parts that can be sent each minute\. T\-Mobile and Sprint provide a daily limit, with no limitation on the number of message parts that can be sent per minute\. As of April 1, 2021, Verizon hasn't announced its 10DLC throughput policy\.

When you set up 10DLC, you have to register your company\. The Campaign Registry uses this information to calculate a trust score\. Your trust score determines the capabilities of your 10DLC phone number\. The following table shows the 10DLC trust score tiers and the capabilities of 10DLC numbers that fall into those tiers\.


| Tier | 10DLC campaign message parts per minute \(AT&T\) | Maximum daily 10DLC messages per company \(T\-Mobile\) | 
| --- | --- | --- | 
|  High  |  3,600  | 200,000 | 
| Medium\-high | 600 |  40,000  | 
| Medium\-low | 60 | 10,000 | 
| Basic | 12 | 2,000 | 

For a comparison of the different phone number types see [US phone number capabilities](settings-sms.md#10dlc-product-comparison)\.

## Setting up 10DLC<a name="10dlc-request"></a>

You can set up 10DLC directly in the Amazon Pinpoint console\. To set up 10DLC, you must complete all of the following steps\.

1. **Register your company**

   The first step in setting up 10DLC is to register your company or brand\. For information, see [Registering a company](settings-register-company.md)\. Registration is typically instantaneous, but in some cases The Campaign Registry requires more information\. There is a one\-time registration fee to register your company\. This fee is shown on the registration page\.

1. **Register your campaign**

   After you register you company, you create a 10DLC campaign\. A 10DLC campaign contains information about your use case\. Each 10DLC campaign can be associated with one company\. Amazon Pinpoint sends this campaign information to The Campaign Registry for approval\. In most cases, 10DLC campaign approval is instantaneous\. In some cases, The Campaign Registry may require additional information\. For more information, see [Registering a 10DLC campaign](settings-register-campaign-10dlc.md)\. There is a recurring monthly fee for each 10DLC campaign that you register\. The monthly fee varies depending on your use case\. The recurring fee for your campaign is shown on the registration page\.

1. **Request your 10DLC number**

   After your 10DLC campaign is approved, you can request a phone number and associate that number with the approved 10DLC campaign\. Each phone number can only be associated with a single 10DLC campaign\. For more information, see [Requesting a number](settings-request-number.md)\. There is a monthly recurring fee for leasing the phone number\. This fee is shown on the purchase page\.

## 10DLC registration and monthly fees<a name="10dlc-fees"></a>

There are registration and monthly fees associated with using 10DLC, such as registering your company and 10DLC campaign\. These are separate from any other monthly or AWS fees\. For more information about 10DLC fees, see the [Amazon Pinpoint Pricing](https://aws.amazon.com/pinpoint/pricing/) page\.