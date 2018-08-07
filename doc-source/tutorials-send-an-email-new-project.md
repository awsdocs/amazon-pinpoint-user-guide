# Step 1: Create a New Amazon Pinpoint Project<a name="tutorials-send-an-email-new-project"></a>

In Amazon Pinpoint, a *project* is a collection of settings, segments, campaigns, and analytics for a specific set of customer engagements\. Before you can send email using Amazon Pinpoint, you first have to create a campaign\. 

The procedure in this section shows you how to create a project by using the AWS CLI\.

**To create a new Amazon Pinpoint project**
+ At the command line, type the following command to create a new project\. Replace *My Email Project* with a unique name for your project\. 

  ```
  aws pinpoint create-app --create-application-request Name="My Email Project"
  ```

  When the command runs successfully, you see output similar to the following example:

  ```
  {
      "ApplicationResponse": {
          "Id": "28268e0b68c54257bc66a1085EXAMPLE",
          "Name": "My Email Project"
      }
  }
  ```

**Next:** [Verify an Identity »](tutorials-send-an-email-verify-identity.md)