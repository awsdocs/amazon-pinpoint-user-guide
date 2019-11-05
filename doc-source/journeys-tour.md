# Take a Tour of Journeys<a name="journeys-tour"></a>

Journeys includes some new concepts and terminology that you might not be familiar with\. This section explores these concepts in detail\.

## Journeys Terminology<a name="journeys-tour-terminology"></a>

**Journey workspace**  
The area of the journeys page where you create your journey by adding activities\.

**Activity**  
A step in a journey\. Different things can happen when participants arrive on different types of activities\. In Amazon Pinpoint, you can create the following types of activities:    
**Send email**  
When a participant arrives on a **Send email** activity, Amazon Pinpoint sends them an email\. When you create a **Send email** activity, you specify an [email template](message-templates-creating-email.md)\. Email templates can include substitution values, helping you to create a more personalized experience\.  
**Wait**  
When a participant arrives on a **Send email** activity, they remain on that activity until a certain date, or for a specific amount of time\.  
**Yes/no split**  
Sends participants down one of two paths based criteria that you define\. For example, you can send all participants who read an email down one path, and send everyone else down the other path\.  
**Multivariate split**  
Sends participants down one of up to four paths, based on criteria that you define\. Participants who don't meet any of the criteria proceed down an "Else" path\.  
**Holdout**  
Ends the journey for a specified percentage of participants\.  
**Random split**  
Randomly sends participants down one of up to five paths\.

**Path**  
A connector that joins one activity to another\. A split activity might create several paths\.

**Participant**  
A person who is traveling through the steps in a journey\.

## Parts of the Journeys Interface<a name="journey-tour-interface"></a>

This section contains information about the components of the journeys interface\. When you create or edit a journey, you see the journey workspace\. The following image shows an example of the journey workspace\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-workspace.png)

The following table includes descriptions of several of the buttons that are used in the journey workspace\.


****  

| Appearance | Button name | Description | 
| --- | --- | --- | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-info-button.png) | **Info** button | Opens the help panel, which shows additional information about individual journey activities\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-delete-action-button.png) | **Delete activity** button | Deletes the highlighted activity\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-undo-button.png) | **Undo** button | Reverts the most recent action\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-redo-button.png) | **Redo** button | Restores an action that was previously undone by using the **Undo** button\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-center-button.png) | **Center** button | Moves to the top of the journey and centers the **Entry trigger** step on the journey workspace\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-zoom-out-button.png) | **Zoom out** button | Reduces the size of objects in the journey workspace\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-zoom-in-button.png) | **Zoom in** button | Increases the size of objects in the journey workspace\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-add-activity.png) | **Add activity** button | This button appears at every point where you can insert another step in the journey\. When you choose this button, you see a menu that lets you choose an activity type\. | 
| ![\[Image NOT FOUND\]](http://docs.aws.amazon.com/pinpoint/latest/userguide/images/journeys-feedback-button.png) | **Feedback** button | A quick and easy way to provide feedback about your experience using journeys\. We review all of the feedback that we receive through this button, and we might contact you for additional information if we have any additional questions\. | 