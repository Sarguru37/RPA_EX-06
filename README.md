# RPA-EXPERIMENT-6
### Name : SARGURU K
### Reg No : 212222230134
## AIM:
  To create a UiPath workflow that copies all files from a source folder to a destination folder and renames them by appending a timestamp to each file name.

## ALGORITHM:
Step 1: Create a New Process Open UiPath Studio and create a new process named CopyRenameFiles.

Step 2: Create Input Variables Create the following variables in the Variables panel:

* Name : Type Default Value (optional) sourceFolder : String "C:\Users\YourName\Documents\SourceFiles" destFolder : String "C:\Users\YourName\Documents\RenamedFiles" files : String[] (leave blank)

Step 3 : Get All Files from Source Folder Drag an Assign activity:
files = Directory.GetFiles(sourceFolder)

Step 4: Use For Each to Loop Through Files i. Add a For Each activity. ii. ForEach item: file In files iii. Set TypeArgument to String.

Step 5: Inside the Loop – Generate Timestamp Add an Assign activity inside the loop:
* timeStamp = Now.ToString("yyyyMMdd_HHmmss")
* Create a timeStamp variable of type String.
  
Step 6: Get File Name and Extension
* Add two Assign activities: fileName = Path.GetFileNameWithoutExtension(file) extension = Path.GetExtension(file) (Create fileName and extension variables of type String)

Step 7: Build New File Name Add Assign:
* newFileName = fileName + "_" + timeStamp + extension
(Create newFileName as a String variable)

Step 8: Copy File to Destination Folder
* Add another Assign:
destPath = Path.Combine(destFolder, newFileName)
(Create destPath as a String variable)
* Then use Copy File activity: From: file To: destPath

## PROGRAM:

![image](https://github.com/user-attachments/assets/b4a1d123-702c-4403-a7ec-01229486eda8)
![image](https://github.com/user-attachments/assets/4906fd6b-f060-4357-9882-a50231d24efd)

## OUTPUT:

![image](https://github.com/user-attachments/assets/ee682215-9a9e-4855-8a89-67cdc0b0aa0e)
![image](https://github.com/user-attachments/assets/be01a94f-1b1e-40fe-80ec-f6a2e3ce6e19)

## RESULT:
   The UiPath workflow successfully reads all files from a source folder, appends a timestamp to each file name, and copies them to a new destination folder.
