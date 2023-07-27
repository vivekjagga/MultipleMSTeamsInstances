# Multiple MS Teams Instances
Run multiple instances of MS Teams application on a machine
In our office, the people need to be logged into the corporate account and a business (client) for communication in client's network but we can run only 1 instance of MS Teams by default. There is a user voice on the same rum multiple instances on a machine. 

Follow the below listed steps to setup multiple instances on a single machine

Open any text editor, you can use default notepad app of your windows pc
Copy the below code to your editor
@ECHO OFF


SET MSTEAMS_PROFILE=%~n0

ECHO - Using profile "%MSTEAMS_PROFILE%"


SET "OLD_USERPROFILE=%USERPROFILE%"

SET "USERPROFILE=%LOCALAPPDATA%\Microsoft\Teams\CustomProfiles\%MSTEAMS_PROFILE%"
 

ECHO - Launching MS Teams with profile %MSTEAMS_PROFILE%

cd "%OLD_USERPROFILE%\AppData\Local\Microsoft\Teams"

"%OLD_USERPROFILE%\AppData\Local\Microsoft\Teams\Update.exe" --processStart "Teams.exe"
Save the above file on your machine with extension ".bat" or with ".cmd"
Once you have your Teams Application Running with one profile double click on the Batch File second instance of the application will be initiated automatically. You can login with same profile or different profile basis on your need.

**Limitation**:
You are using the multiple instances of the application so you cannot download the documents or files from the second version as the first version is already associated with your drive. We can always edit the document in the Microsoft Teams Application without any issues.

