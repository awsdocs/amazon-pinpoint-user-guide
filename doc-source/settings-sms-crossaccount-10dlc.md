# 10DLC cross\-account access<a name="settings-sms-crossaccount-10dlc"></a>

You can register the same tax ID and brand across multiple AWS accounts\. Alternatively, you can register a single AWS account, and use AWS Identity and Access Management \(IAM\) roles to associate other accounts with your main account\. Then, delegate access permissions from the main account to the other accounts by granting them access to the 10DLC numbers in the main account\.

**To grant access to the 10DLC numbers in your main account**

1. Sign in to the AWS Management Console and open the Amazon Pinpoint console at [https://console\.aws\.amazon\.com/pinpoint/](https://console.aws.amazon.com/pinpoint/)\.

1. Under **Account Settings**, **SMS and voice**, choose the **10DLC** tab\.

1. Register your company and campaign on the main account that will use the 10DLC phone number\. For example, your main account might be a `Production` account, but you want your `Development` account to use a 10DLC number\. 

1. Create the IAM role in your main account\. This allows another account to call the `SendMessages` API operation\. For this operation, you must specify the 10DLC number to use for the originating identity\. For more information on creating roles, see [Creating IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create.html) in the *IAM User Guide*\. 

1. Delegate and test access permission from your main account using IAM roles with any of your other accounts that need to use your 10DLC numbers\. For example, you might delegate access permission from your `Production` account to your `Development` account\. See [Delegate access across AWS accounts using IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html) in the *IAM User Guide* for more information about delegating and testing\.

1. Using the new role, send a message using a 10DLC number from the main account\. See [Using IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use.html) in the *IAM User Guide* for more information on using a role\. 
**Important**  
A sent message from the secondary account is treated as if it were sent from your main account\. Quotas and billing are counted against this account and not any secondary accounts\.