# JenkinsDemo
Jenkins with github and pytest


## prerequisite 
refer to [install Jenkins on Windows](https://www.jenkins.io/doc/book/installing/windows/)
### - Java JDK
1. download jdk 8 or jdk 11 (from adoptium.net)
2. install jdk 11, setup JAVA_HOME
3. after installation, simply modify env (remove the last '\' on JAVA_HOME; and setup 'path', %JAVA_HOME%\bin)

### - Jenkins
1. download windows LTS version for Jenkins
2. pre-installation, setup service account for Jenkins, Local Security > Local Policies > User Rights Assignment > Log on as a service > Add User or Group..., input "Administrator", and [Check Names], then [OK] ==> XXX not working
3. install Jenkins, follow the setup wizards of Jenkins. (because of above failure, choose Run service as LocalSystem); NOT "Start Service" before config of Jenkins
4. post-installation, edit jenkins.xml if needed for path modification, JENKINS_HOME, executable, arguments,... (you might need to refer the youtube video to setup)
5. open "Services", find Jenkins and start running it

### - Unlocking Jenkins
1. Browse to http://localhost:8080
2. input password from initialAdminPassword
