# Preparation

Let's start the excercise and see whether everything is ready to go.
Please make sure you have all the necessary prerequsistes listed below. If not, please raise your voice during the meeting so that we can assist you early in the session.

## Prerequisites
Please keep the following links and resources available:

1. You need a browser, preferably Google Chrome
1. Logon to the Development Lobby  
https://lcapteched2021-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/
1. Your user is your SAP email address
1. Your password is you global SAP password
1. **In almost every chapter of this tutorial there is a reference to a number XXX, so a 3 digit number. Make sure that this number was assigend to you by the moderators / speakers of this course and remember it well.** It is important as we will use these numbers, where every user has a different one, in order to create different names for applications and other artefact. As we will deploy all the the artefacts to the same Business Technology Platform account, it is important that they all differ in the names and identifiers, so there are no clashes 
1. **If you don't have access to the lobby with your SAP email and global password or if you don't know your number, please let the speakers know.**
1. Optional: If you read this before the workshop has actually started you can invoke the following URL: https://lcapteched2021.eu10cf.applicationstudio.cloud.sap/index.html?origin=LCAP&pack=LCAP&gen-type=yo&yo-gen-name=@ext-lcapvsc-npm-dev/lcap&yo-arg1=test&root-dir=test You will then see an image like this:
![](/exercises/ex0/images/LCAP_01.png)
It will take several minutes (5 or so) until it switches to the next view, you have now entered the Business Application Studio and you can just close the browser window again.
What is this good for? When as a user you enter the Business Application Studio for the first time on a BTP account it is set up for you in the background. A so-called dev space is created for you with all the content that is needed for low code applicaion development. You can compare this to a new computer that is handed to you and is now set up, including all the low code software that is needed for development. If you have done this step upfront, the entry time into the Business Application Studio when the real exercises begin is smaller. If you haven't done it, that's not a problem either, you just wait a bit longer for the first time.
1. For the mobile preview app you should install  
iOS: https://apps.apple.com/us/app/sap-appgyver-preview/id1585856868  
Android: https://play.google.com/store/apps/details?id=com.sap.appgyver.preview.release  
You can also just search "AppGvyer Preview" in your app store and install it.

## General troubleshooting

1. If the set up of you Business Appliaction Studio takes exceptionally long and you get a screen that says "t's taking longer than expected to prepare your dev space", you can always invoke this URL to monitor further:
https://lcapteched2021.eu10cf.applicationstudio.cloud.sap/index.html
It shows you your LCAP dev space and in what mode it is. If it says "Starting" it is still starting up. It is says "Running" you are ready to go. If you have a couple of hours of inactivity, the dev space will be shut down (not remved though) and you will see a "Stopped" indicator. Once the dev space was stopped it can take up to 2 minutes again to get it started. The time will be less than the very first access.

1. If you encounter an issue with the Low-Code perspective in the Business Application Studio (BAS) you can check the logs under: File > Open > /home/user/lcap.home.2021-11-17.log (if you encounter the issue at any other day, you need to update the file name with the date of that day)

1. If something does not work in the editor, but it should, you can try restarting the whole workspace. To do so, open this URL: https://lcapteched2021.eu10cf.applicationstudio.cloud.sap/index.html.  
Here you see the so-called Dev Spaces of the Business application studio. Click on the "Stop" button. Once the Dev Space stopped, you can simply restart it. In order to go back to your Low-Code perspective you must go through the lobby - located here:  
https://lcapteched2021-applicationdevelopment.lcnc.cfapps.eu10.hana.ondemand.com/



Continue to - [Exercise 1](../ex1/README.md)
