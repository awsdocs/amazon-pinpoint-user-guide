# Viewing a list of dedicated IP addresses that are associated with your account<a name="channels-email-dedicated-ips-viewing"></a>

You can view a list of dedicated IP addresses that are associated with your Amazon Pinpoint account in the current AWS Region\. These IP addresses are available for use with both Amazon Pinpoint and Amazon Simple Email Service \(Amazon SES\)\. 

You can also use the Amazon Pinpoint console to quickly determine if any of your dedicated IP addresses have been listed on Domain Name System\-based Blackhole Lists \(*DNSBLs*\)\. DNSBLs are also called *Realtime Blackhole Lists* \(*RBLs*\), *deny lists*, *blocklists*, or *blacklists*\)\. DNSBLs are lists of IP addresses that are suspected of sending spam, malicious content, or other unsolicited messages\. Different DNSBLs have different impacts on email deliverability\. The lists offered by Spamhaus have the most serious impact on email delivery\.

**To view a list of dedicated IPs in your account**

1. Open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. In the navigation pane, under **Email**, choose **Dedicated IPs**\.

   The list of IP addresses also includes the following information:  
**Listing date**  
If the IP address is currently listed on a DNSBL, this field shows the date when it was most recently added\.  
**Reputation**  
A description of the health of the IP address\.  
**Blacklist name**  
If the IP address is currently listed on a DNSBL, this field shows the name of the list that it's listed on\.  
**Blacklist reason**  
If the IP address is currently listed on a DNSBL, this field displays the reason that the address was added to the list\. This text is provided by the list providers themselves\. Some providers offer detailed explanations, while others offer generic information\.