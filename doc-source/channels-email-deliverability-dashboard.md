# The Amazon Pinpoint Deliverability Dashboard<a name="channels-email-deliverability-dashboard"></a>

The Deliverability dashboard helps you identify and address issues that could have an impact on the delivery of the email that you send using Amazon Pinpoint\. Addressing the issues identified in this dashboard can increase the chances that the emails you send from Amazon Pinpoint arrive in your customers' inboxes, as opposed to their junk mail folders\.

**Important**  
There are additional fees associated with using the Deliverability dashboard\. To learn more about these fees, see the [Amazon Pinpoint Pricing page](https://aws.amazon.com/pinpoint/pricing/)\.

You can access the Deliverability dashboard by using the Amazon Pinpoint console\.

**To view the Deliverability dashboard**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, choose **Deliverability dashboard**\.

The Deliverability dashboard is made up of three parts, which are described in the following sections:
+ [Domain Reputation](#channels-email-deliverability-dashboard-domain)
+ [IP Address Reputation](#channels-email-deliverability-dashboard-ip-address)
+ [Predictive Inbox Placement Tests](#channels-email-deliverability-dashboard-pipt)

## Domain Reputation<a name="channels-email-deliverability-dashboard-domain"></a>

The **Domain reputation** tab contains information about the domains that you use to send email, including their engagement rates, inbox placement rates, and blacklist activities\.

### Deliverability Overview<a name="channels-email-deliverability-dashboard-domain-overview"></a>

This section contains information about the percentage of emails from your domain that arrived in your customers' inboxes\. It also provides information about the percentage of emails that your customers engaged with by opening them or by clicking links in them\. Finally, it shows the number of blacklists that the IP addresses associated with the domain are on\.

**Note**  
The information in this section contains general guidance, as opposed to exact metrics\. If you need precise metrics related to the delivery of your mail and engagement with it, you should set up [event streams](settings-event-streams.md)\.

To view data in this section, use the filters to choose a domain and a range of dates, as shown in the following image\. When you choose a domain and date range, data appears in the **Deliverability overview**, **Inbox placement by email provider**, and **Blacklist activities** sections\.

**Note**  
You can use the date filter to choose a date range that contains up to 30 days\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-email-deliverability-dashboard-overview.png)

When you choose a domain and a date range, the **Deliverability overview** section shows the following information:
+ **Engagement rate** – The percentage of email sent from the selected domain that recipients opened or clicked links in\. When determining whether to deliver your email to recipient's inboxes, many email providers \(especially larger ones\) consider how often recipients engaged with email sent from your domain in the past month or two\. For this reason, you should try to maintain an engagement rate of at least 25%\.
+ **Inbox placement rate** – The percentage of email sent from the selected domain that arrived in recipients' inboxes\. An inbox placement rate of around 80% is considered average\.
+ **Blacklist activities** – The number of blacklists that IP addresses associated with the domain appear on\. To learn more about blacklists, see [Blacklist Activities](#channels-email-deliverability-dashboard-domain-blacklist)\.

### Inbox Placement by Email Provider<a name="channels-email-deliverability-dashboard-domain-inbox-placement"></a>

This section shows you how different email providers handled the email that was sent from your domain during the selected time period\. The email providers analyzed in this section include Gmail, Hotmail, Yahoo, and AOL\. This section also contains a category called **Others**\. This category includes internet service providers and regional providers\. When combined, the delivery metrics in this section represent a vast majority of all consumer email sent worldwide\.

This section includes average rates for inbox placement and spam folder placement for each email provider\. It also includes a chart, shown in the following image, that displays the inbox placement rate for each provider for every day in the analysis period\. You can use the information in this chart to help identify campaigns that resulted in poor delivery rates\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-email-deliverability-dashboard-domain-reputation.png)

### Blacklist Activities<a name="channels-email-deliverability-dashboard-domain-blacklist"></a>

This section helps you to quickly identify blacklist events that could impact the delivery of emails sent from your domain\. A *blacklist* is a list of IP addresses that are suspected of sending unsolicited or malicious email\. Different blacklist providers have different criteria for adding IP addresses to their lists, and for removing \("delisting"\) IP addresses from their lists\. Additionally, each email provider uses a different blacklist or set of blacklists\. Also, each provider weighs blacklisting events differently\. If one of your dedicated IP addresses is listed in this section, it doesn't necessarily mean that there will be any impact on the delivery of your email\.

If one of your dedicated IP addresses appears in this section, you should contact the organization that manages the blacklist, and request that your IP address be removed\. The following table includes a list of blacklist operators that are considered in this section, and includes links to their procedures for delisting an IP address\.


| Blacklist Operator | Link to Delisting Procedures | 
| --- | --- | 
| Spamhaus | [Spamhaus website](https://www.spamhaus.org/lookup/)  | 
| Barracuda | [Barracuda website](http://www.barracudacentral.org/rbl/removal-request)  | 
| Cloudmark Sender Intelligence \(CSI\) | [Cloudmark Sender Intelligence website](https://csi.cloudmark.com/en/reset/)  | 
| Composite Blocking List \(CBL\) | [Composite Blocking List website](https://www.abuseat.org/lookup.cgi)  | 
| LashBack | [LashBack website](https://blacklist.lashback.com/)  | 
| Passive Spam Block List \(PSBL\) | [Passive Spam Block List website](https://psbl.org/remove)  | 
| SORBS | [SORBS website](http://www.sorbs.net/delisting/overview.shtml)  | 
| SpamCop | [SpamCop website](https://www.spamcop.net/fom-serve/cache/298.html)  | 

## IP Address Reputation<a name="channels-email-deliverability-dashboard-ip-address"></a>

The **IP address reputation** tab contains information about the blacklist activities for the dedicated IP addresses that you use to send email by using Amazon Pinpoint\. Every IP address that's associated with your Amazon Pinpoint account is listed in the table on this page, as shown in the following image\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-email-deliverability-dashboard-ip-address.png)

If the value in the **Reputation** column is *High*, then there are no blacklist activities that impact the reputation of that IP address\. If the IP address does appear on a blacklist, the name of that blacklist is shown in the **Blacklist name** column\.

If one of your dedicated IP addresses appears in this section, you should contact the organization that manages the blacklist, and request that your IP address be removed\. The following table includes a list of blacklist operators that are considered in this section, and includes links to their procedures for delisting an IP address\.


| Blacklist Operator | Link to Delisting Procedures | 
| --- | --- | 
| Spamhaus | [Spamhaus website](https://www.spamhaus.org/lookup/)  | 
| Barracuda | [Barracuda website](http://www.barracudacentral.org/rbl/removal-request)  | 
| Invaluement | [Invaluement website](https://www.invaluement.com/removal/)  | 
| LashBack | [LashBack website](https://blacklist.lashback.com/)  | 
| Passive Spam Block List \(PSBL\) | [Passive Spam Block List website](https://psbl.org/remove)  | 
| SORBS | [SORBS website](http://www.sorbs.net/delisting/overview.shtml)  | 

## Predictive Inbox Placement Tests<a name="channels-email-deliverability-dashboard-pipt"></a>

On the **Predictive inbox placement tests** tab of the Deliverability dashboard, you can perform tests that can help you predict how your messages will be handled by various email providers around the world\. When you perform a predictive inbox placement test, you provide a sample message that contains the content that you plan to send to your customers\. Amazon Pinpoint then sends that message to special email addresses spread across several major email providers\. After about 24 hours, the test is complete, and you can view the results of the test\.

**Note**  
Typically, we charge you for each message that you send using Amazon Pinpoint\. However, when you perform a predictive inbox placement test, we don't charge you for the emails that we send to these test email addresses\.

Predictive inbox placement tests show you how different email providers handle specific messages\. Compare this to the information on the **Domain reputation** tab, which measures general trends related to all of the email sent from a specific domain\.

The test results tell you how many of your messages arrived in these test recipients' inboxes on the various email providers\. It also tells you how many messages were sent to recipients' junk mail folders, and how many weren't delivered at all\. Performing predictive inbox placement tests help you identify deliverability problems that could arise as a result of the content of your email\.

**To create a new predictive email placement test**

1. On the **Predictive email placement tests** tab, choose **Create a test**\.

1. For **Name**, enter a name that helps you easily identify this specific test\.

1. For **From address**, choose either an **Email address** or a **Domain**, and then specify the email address that you plan to use to send the email\.

1. For **Subject**, enter the subject line that you plan to use for the email\.

1. For **HTML content**, enter the HTML\-formatted content of the message\.

1. Choose **Submit**\. The predictive inbox placement test begins\.

It takes approximately 24 hours for the test to complete\. When the test is finished, complete the following procedure to view the results\.

**To view the results of a predictive inbox placement test**
+ On the **Predictive email placement tests** tab, choose the test that you want to view, and then choose **View test results**, as shown in the following image\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-email-deliverability-dashboard-pipt-view-results.png)

### Test Results<a name="channels-email-deliverability-dashboard-pipt-results"></a>

Predictive inbox placement tests contain two sections: a **Deliverability overview** and an **ISP Overview**\.

**Deliverability Overview**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/channels-email-deliverability-dashboard-pipt-results.png)

This section contains a summary of the predictive inbox placement test\. It includes the following information:
+ **From identity** – The sender email address for the test email\.
+ **Subject** – The subject line of the email\.
+ **Inbox** – The percentage of test messages that arrived in recipients' inboxes\.
+ **Spam** – The percentage of test messages that were sent to recipients' junk mail folders\.
+ **Missing** – The percentage of test messages that weren't delivered to recipients at all\.
+ **DKIM rate** – The percentage of test messages that were authenticated by the recipient's mail providers by using DomainKeys Identified Mail\.
+ **SPF rate** – The percentage of test messages that were authenticated by the recipient's mail provider by using Sender Policy Framework\.

You can also view the body of the email by choosing **View HTML content**\.

**ISP Overview**

This section contains a list of all of the email providers that we sent your test message to during the test\. For each provider in this list, we provide the same five metrics shown in the **Deliverability overview** section \(**Inbox**, **Spam**, **Missing**, **SPF**, and **DKIM**\)\.