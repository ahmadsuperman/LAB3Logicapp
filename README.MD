ChatWatch Content Moderation Service Report
Introduction
This report details the design, implementation, testing, and challenges of the "ChatWatch" Logic App, developed to monitor Microsoft Teams messages for inappropriate content and notify administrators.

Design Choices
Logic App and Microsoft Teams Integration
Trigger: The Logic App is triggered by new messages in specific Microsoft Teams channels, scanning for keywords like "Bad," "Fat," and "Hell."
Channels Monitored: Selected channels are based on their relevance and likelihood of containing critical communications needing moderation.
Email Notification System
Email Service: Office 365 is used to send email notifications, leveraging its reliability and integration ease.
Email Content: Notifications contain details about the message, including the content, channel ID, and Teams ID.
Implementation Process
Logic App Configuration
Trigger Setup: A webhook trigger in Logic App starts the process when specified keywords are mentioned in the Teams channels.
Email Action: The 'Send_an_email_(V2)' action is configured to dispatch emails through Office 365 when the trigger condition is met.
Azure Environment
Resource Group: Lab3
Location: Canada Central
Subscription ID: Used for tracking and billing purposes.
Testing Strategy
Keyword Detection
Test Cases: Messages containing the specified keywords ("Bad," "Fat," "Hell") were sent in the monitored channels.
Trigger Verification: Ensured that each instance of the keywords triggered the Logic App.
Email Notification
Recipient Validation: Tested with the email address AddYourUserName@algonquinlive.com to ensure prompt receipt of notifications.
Content Accuracy: Checked the details in the email body for correctness and completeness.
Challenges Faced
Configuration Issues
Connection IDs: Initially faced difficulties in locating and setting up the correct connectionId for Teams and Office 365 in the Logic App.
Keyword Trigger Sensitivity: Tuning the Logic App to respond accurately to keywords without generating false positives.
Integration Complexities
Teams Channel Identification: Determining the correct channel identifiers (channelId and groupId) for the trigger required careful verification.
Conclusion
The "ChatWatch" Logic App now effectively monitors specified Teams channels for inappropriate language and sends alerts through email. This system enhances our ability to maintain a professional and respectful communication environment in Microsoft Teams.