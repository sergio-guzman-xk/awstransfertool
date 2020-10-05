# AWS Transfer Tool
This tool has been created to help users to move data from one Amazon S3 bucket to their local machine or another Amazon S3 bucket. Even thought Amazon has a direct way to do this, sometimes it is not possible due to security restrictions in any of the parties involved.

Please have in mind that none of the tasks are recurse and will only work on files and not folders (except for the Inspect buttin which will show folder at the current location). It will skip any subfolder at the Chose S3 location. If you want to download the files in a subrfolder then just make sure to specify it in the AWS Source Path box.

# Requirements
You need the latest version of Python which can be download at https://www.python.org/downloads/ (Make sure to add it to the path). You also need to install awscli by opening powershell and running: pip3 install awscli.

This program just automates the process of running cli commands and gives you the option to choose how many items you want to work with if so desired. That being said, the program uses shell commands and scripts. The code already executes and modifies all the privileges it needs to function. You can see those in the source code. To be precise:

Set-ExecutionPolicy RemoteSigned -Scope CurrentUser -force ; 
Set-ExecutionPolicy RemoteSigned -Scope LocalMachine -force;

Which just allows you to run local scripts.

# Usage
You just need to download the .exe file and run it as an administrator.

Once open you have 6 buttons. 

## 1. Check Tools - Optional

This will allow you to check the status of the tools you should have installed and that are listed in the requirements section on this readme. The use of this button is not a must.

## 2. AWS Profile Config - Optional

This is for you to create the AWS profiles. These are needed to access the AWS s3 bucket and you need to add a Profile Name (of your choice), an ACCOUNT_KEY and a SECRET_KEY (Both provided by the AWS services). You can create as many as you want but you cannot use the same Profile Name twice unless you manually remove the data of the already existing profile. You can do so manually by going to the aws local folder at C:\Users\%localuser%\.aws\

Once there you have to manually modify both the config and credentials file using a text editor. Check AWS documentation to understand how to interact with these files.

Even through it is not mandatory to use this button to create the profiles, it is mandatory the use of them to run this program.

## 3. Inspect s3 -Optional

This button will list all the files and folders in the Origin S3 location. For this to work you need to fill the following boxes:
### Mandatory:
- Origin Profile
- AWS Source Path: Have in mind that it should end with '/'

## 4. Save Configuration - Mandatory

This button will save the configuration you have on screen and create the files needed to run the program. It will also display the list of the files it will work with so that you are aware of what will be moved. This requires the following boxes:
### Mandatory
- Origin Profile
- AWS Source Path: Have in mind that it should end with '/'
- Local Path: Have in mind that it should end with '\' and must be the absolute Path.
### IF THE AWS CHECKBOX IS SELECTED
- Destination Profile
- AWS Destination Path: Have in mind that it should end with '/'

### Optional
- Package Size: If you don't want to move all the content at the current S3 Source location then you can specify how many files you want to work with. 
                If left empty the system will just work with the all the files at the Souce Location. 
                
### IMPORTANT!!!
The program will work with what you saved. If you perform any changes and do not click on the button to save them, the program will work with the previously saved configuration. 

## 5. Estimate Packet Size - Optional

This will show you how much data will be moved. That will help you control what you will be putting in your local machine or in your aws S3.

## 6. Start - mandatory

This will start the process based on the last configuration you saved. If the AWS checkbox is checked then the program will transfer the files from the source S3 to the destination S3 using the local path folder as a bridge. This will move the files one by one so the only storage being use locally will be for the file that is being worked on at the time (one at a time).

If the AWS checkbox was not checked then the program will store the files locally.

Either of these options will move the data. Which means that the file will be deleted from the source as soon as the file is in the destination.

# Source Code
The source code can be found at https://github.com/sergio-guzman-xk/awstransfertoolProject.git

# Possible Features
I may add a way to do Amazon S3 to Azure Storage Solution. Depending on the demand, however, it will not happen in the near future.
