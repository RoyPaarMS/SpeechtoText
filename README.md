# SpeechtoText
This repo contains a solution for Power Apps, Dynamics 365, and Power Platform.  The solution contains a Power Automate flow that is triggered when a note is created within Dataverse (annotation).  If the note contains a .wav file recording (OOB behavior when recording on mobile apps) the flow will call an Azure Speech to Text service to convert the .wav file to text.  It will then repopulate the note name field with the transcribed text.

![image](https://user-images.githubusercontent.com/86677937/138903711-faeb9b08-4bfe-4ffa-8027-6f7e061ffb7e.png)

## Prerequisites
This Power Automate flow uses the http connector.  The following prerequisites must be met in order for this flow to run successfully.
1. Environment must have Dataverse
2. Data Loss Prevention Policies (DLPs) must allow use of http connector
3. You must have an Azure Speech to Text service provisioned in your Azure tenant.  The service must be available to the public.  There is a free tier.
4. The flow is currently set at the User scope.  If you want other users to be able to use this functionality, consider setting the trigger step in the flow at a broader scope.
5. Recording audio from one of the D365 mobile apps (field service mobile, etc.) will automatically add a .wav file to your note.  I have not tried this in a canvas app - there may be some conversion required.
6. There are three environment variables to set when publishing - language (i.e. en-US), region (i.e. cenralus), and you Azure Speech to Text key (you must get this from Azure after you provision your service).  Key 1 or Key 2 should work.
