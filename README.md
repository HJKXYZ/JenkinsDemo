# JenkinsDemo
Jenkins with github and pytest


## prerequisite 
refer to [install Jenkins on Windows](https://www.jenkins.io/doc/book/installing/windows/)
### - Java JDK (OpenJDK11U-jdk_x64_windows_hotspot_11.0.15_10.msi)
1. download jdk 8 or jdk 11 (from adoptium.net)
2. install jdk 11, setup JAVA_HOME
3. after installation, simply modify env (remove the last '\\' on JAVA_HOME; and setup 'path', %JAVA_HOME%\bin)

### - pre-installation Jenkins (Setup user account to logon as service)
1. Add service account for Jenkins, Local Security Policy > Local Policies > User Rights Assignment > Log on as a service > Add User or Group..., input "Administrator", and [Check Names], then [OK]
2. (optional) if above **1.** not working to add "Administrator", refer to troubleshooting

### - Jenkins (jenkins.msi)
1. download windows LTS version for Jenkins
2. install Jenkins, follow the setup wizards of Jenkins. (if failure on add user account, choose Run service as LocalSystem); **NOT "Start Service" before config of Jenkins**
3. post-installation, edit jenkins.xml if needed for path modification, JENKINS_HOME, executable, arguments, and pidfile (you MIGHT need to refer the youtube video to setup)
4. open "Services", find Jenkins and start running it
5. if necessary, try to troubleshoot the issue by check the jenkins log under Jenkins folder, jenkins.err, jenkins.out, jenkins.wrapper

### - Unlocking Jenkins
0. make sure **Jenkins service** is running (ton of files will grow under JENKINS_HOME)
1. Browse to http://localhost:8080
2. input password from initialAdminPassword
3. Install suggested plugins, as we set on jenkins.xml
4. step by step then, Jenkins is ready


# Uninstall Jenkins on Windows
1. open "Control Panel\Programs\Programs and Features", choose **Jenkins**, then **uninstall** it
2. Remove the rest of Jenkins files, depends on the file path that setup in **jenkins.xml**, find those paths and delete them




--------------------------------------------------
## troubleshooting
### refer to comment on https://www.youtube.com/watch?v=XuMrEDA8cAI
“Run service as local or domain user”: (If you get stock at this stage of the installation process, follow the steps below to resolve)

1) Create a local user or domain user to proceed further:
Type “User accounts” in the windows start menu, select the options which reads as “Add, edit or remove other users”. 
2) Add a new user under “Other user” and select option “I don't have this person's sign-in information”. Note: You can give any custom name and your choice of password and proceed without a MS Outlook account (Add a user without a Microsoft account).
3) Once this user created, if you forgot to assign admin role to the newly created user then you will see an error inside the Jenkins dialog.
4) If you experience the Jenkins error dialog box, go to the dialog where you created a local user previously, click on the new local user and assign them administrator role/priviledges.
5) Open the ‘Administrative Tools’ and open the ‘Local Security Policy’:
Hold "win" key and press "r" to open "Run" and type the following "secpol.msc".
6) Expand "Local Policy" and click on "User Rights Assignment"
7) In the right pane, scrol down to locate "Log on as a service" right-click and select properties or double click to open "Log on as a service" properties box.
8) Click on the "Add User or Group…" button to add the new user that you added earlier under “User accounts”.
9) Click on "Check name" for Windows to resolve/add new user name to Local Policy group and click OK to close the dialogue box. 
10) In the "Select Users or Groups" dialogue, find the user you added, click on the name, click "Apply" => "OK" to save changes in the "Log on as a service Properties".
11) Now its time to go back to Jenkins window and try it again. Input the local user details (logon name & password) in the specified fields and click on “Test credentials”. This time a tick must appear.
12) Click next to proceed with Jenkins installation.
