# JenkinsDemo
Jenkins with github and pytest


## prerequisite 
refer to https://youtu.be/XuMrEDA8cAI
### - Java JDK
1. download jdk 8 or jdk 11 (from adoptium.net)
2. install jdk 11, setup JAVA_HOME
3. after installation, simply modify env (remove the last '\' on JAVA_HOME; and setup 'path', %JAVA_HOME%\bin)

### - Jenkins
1. download windows LTS version for Jenkins
2. before installation, setup service account for Jenkins, Local Security > Local Policies > User Rights Assignment > Log on as a service > Add User or Group..., input "Administrator", and [Check Names], then [OK] ==> XXX not working
3. install Jenkins, follow the setup wizards of Jenkins. (because of above failure, choose Run service as LocalSystem); NOT "Start Service" before config of Jenkins
4. 

