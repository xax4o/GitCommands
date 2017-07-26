# Creating and uploading NuGet Packages to Local Repo #

- ## Creating new package ##


>The creation of the nuget packages is identical to what Microsoft has to say about it. For additional information you can also check the lecture about Nuget in the Package Managers section. 

What we have created is a simple script that can automate part of the process. At the moment (June 2017) the script is located in the CoreKraft GIT repository at the solution level. It is a Power Shell Script named (“CoreKraftNugetUploader.ps1”). You can start it by starting PowerShell and navigating to it, or by navigation to the file with file explorer and then in the “navigation bat” type “powershell”. When you ate at the correct location just run the script by typing “CoreKraftNugetUploader.ps1” and pressing enter.

The script has several options that are going to cover briefly:

1.	“Create Basic Nuspec Files.”  This is used to create the initial nuspec files to get you started. They have all the default values. That is why we have the nuspec files as part of the GIT repository so nobody has to write them from scratch every time.
2.	“Open All nuspec Files in Notepad.” This option is going to open all the nuspec files located in the directories around it. This is here so you can review and change the nugget packages before creating the packages.
3.	“Create Nuget Packages.”  This will start creating the nugget packages and save them in the “.\NugetPackages” folder.
4.	“Upload Nuget Packages.  This will copy the nugget packages to the local repository (if you have sufficient privileges). There is a default repository location. That can be changed at the beginning of every upload operation.
5.	“Don't bother me and just do it.”  This step will execute steps 3 and 4 without any questions. 
6.	“Exit.”

>NOTE that the plugins folder is read dynamically when creating the nuspec files so any new plugin that is created can be added to the upload que fairly easy. Needed steps are to run the script with opens 1(create the new nuspecs) 2(open all for editing and edit the new nuspec) 3,4 or simply 5. 

- ## Adding the Local repository to Visual Studio ##
	
	We are using Visual studio 2017 for the example.
First you need to add the local repository to the Visual studio nugget repositories.
It can be done in two ways here is the first:
1.	Go to Tools -> Options… 
2.	 Find “Nuget Package Manager” -> “Package Sources”
3.	Add new Source with Some Name – for example “CCF Local Library” (misspelled in the screenshot oopsy dizzy silly me)
and Source – [Local Nuget](http://nuget.cleancode.factory/Nuget/nuget/)   -> http://nuget.cleancode.factory/Nuget/nuget/
4.	 Save and in a project go to the nugget packages and change the source to the newly create repository I this case the “CCF Local Library” 
5.	Install the need package  by “Browsing” it.