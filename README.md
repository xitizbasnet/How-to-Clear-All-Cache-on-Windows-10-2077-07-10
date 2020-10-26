# How-to-Clear-All-Cache-on-Windows-10-2077-07-10
How to Clear All Cache on Windows 10 | 2077-07-10

First

Go to the Desktop

....................


Second 

Go to the search button and type "Windows PowerShell ISE (x86)" 

..............................................................


Third 

"Windows PowerShell ISE (x86)" Run it as Administration

..............................................................


Fourth 

Create a New File

..............................................................



Fifth 

Click and paste this code:


$objShell = New-Object -ComObject Shell.Application
	$objFolder = $objShell.Namespace(0xA)
	$WinTemp = "c:\Windows\Temp\*"
	
#1#	Empty Recycle Bin #
	write-Host "Emptying Recycle Bin." -ForegroundColor Cyan 
	$objFolder.items() | %{ remove-item $_.path -Recurse -Confirm:$false}
	
#2# Remove Temp
	write-Host "Removing Temp" -ForegroundColor Green
    Set-Location “C:\Windows\Temp”
	Remove-Item * -Recurse -Force -ErrorAction SilentlyContinue

    Set-Location “C:\Windows\Prefetch”
    Remove-Item * -Recurse -Force -ErrorAction SilentlyContinue

    Set-Location “C:\Documents and Settings”
    Remove-Item “.\*\Local Settings\temp\*” -Recurse -Force -ErrorAction SilentlyContinue

    Set-Location “C:\Users”
    Remove-Item “.\*\Appdata\Local\Temp\*” -Recurse -Force -ErrorAction SilentlyContinue
	
#3# Running Disk Clean up Tool 
	write-Host "Finally now , Running Windows disk Clean up Tool" -ForegroundColor Cyan
	cleanmgr /sagerun:1 | out-Null 
	
	$([char]7)
	Sleep 3
	write-Host "I finished the cleanup task,Bye Bye " -ForegroundColor Yellow 
	Sleep 3
##### End of the Script ##### 

..............................................................


Sixth 

Save it as "CleanFile.ps1" in Desktop

..............................................................



Seventh 

Go to the Desktop

..............................................................



Eight 

Open "CleanFile.ps1" from Desktop By right click and go to the option: "Run with PowerShell" 

..............................................................




Ningth 

Wait for some moment until it will finish the work and close the PowerShell by the windows itself.

..............................................................



Tenth 

Done! Enjoy the system will clean up all the temp file and the system will sun smoothly then prviously.

..............................................................


Bye Bye
