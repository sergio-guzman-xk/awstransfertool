# AWS Transfer Tool
This tool has been created to help users to move data from one Amazon S3 bucket to their local machine or another Amazon S3 bucket. Even thought Amazon has a direct way to do this, sometimes it is not possible due to security restrictions in any of the parties involved.

# Requirements
You need the latest version of Python which can be download at https://www.python.org/downloads/ (Make sure to add it to the path). You also need to install awscli by opening powershell and running: pip3 install awscli.

This program just automates the process of running cli commands and gives you the option to choose how many items you want to work with if so desired. That being said, the program uses shell commands and scripts. The code already executes and modifies all the privileges it needs to function. You can see those in the source code. To me precise:

Set-ExecutionPolicy RemoteSigned -Scope CurrentUser -force ; 
Set-ExecutionPolicy RemoteSigned -Scope LocalMachine -force;

# Usage
You just need to download the .exe file and run it as an administrator.

Placeholder

# Course Code
The source code can be found at https://github.com/sergio-guzman-xk/awstransfertoolProject.git

# Possible Features
I may add a way to do Amazon S3 to Azure Storage Solution. Depending on the demand, however, it will not happen in the near future.
