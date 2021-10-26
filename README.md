# SpeechtoText
This repo contains a solution for Power Apps, Dynamics 365, and Power Platform.  The solution contains a Power Automate flow that is triggered when a note is created within Dataverse (annotation).  If the note contains a .wav file recording (OOB behavior when recording on mobile apps) the flow will call an Azure Speech to Text service to convert the .wav file to text.  It will then repopulate the note name field with the transcribed text.

![image](https://user-images.githubusercontent.com/86677937/138903711-faeb9b08-4bfe-4ffa-8027-6f7e061ffb7e.png)
