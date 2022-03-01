layout: page
title: "PowerShell export ACL"
permalink: /export-acl/

# EXPORT ACL TO EXCEL FILE 
* * *

## About
Simple and standalone script to export folder's ACL to an Excel file. I tried to make a straightforward syntax, to be the easiest to use.

## Features
 - Fetches the AD Security Groups, prints their names as well as the list of their members
 - Customizable search depth
 - Takes a single folder path or a file text with all paths to scan
 - Adds a Table Style (you can change it in source code in the Export function) 

## Prerequisites
 - You need to have installed the RSAT tools on your computer, as this scripts uses some cmdlets included in those. 
 - You need of course access rights to the directories you want to scan.
 - The ImportExcel module is automatically imported if you do not have it installed.

## How to use 

### Paremeters
`-out` is where you want to save the Excel file. For example : C:\document.xlsx    

`-scan` is either :    
  - the path to the directory you want to scan    
  - the path to a txt file with the list of all the directories you want to scan      
  
`-depth` is the recursive depth. Default : 1.     

`-help` to print help and command examples

### txt file
To scan several folders in one shot, you can create a txt file containing all those folders separated by a line break
For example :
 
*folders.txt*
```
K:\first\fold\to\scan
C:\second\folder
M:\
```

## Examples 
```powershell
.\export-acl.ps1 -scan M:\path\to\directory -out C:\document.xlsx
.\export-acl.ps1 -scan C:\path\to\list.txt -out C:\document.xlsx
.\export-acl.ps1 -scan C:\path\to\list.txt -out C:\document.xlsx -depth 2
.\export-acl.ps1 -help
``` 
## Links
[GitHub repository](https://github.com/ouiouiallez/export-acl)     
[ImportExcel GitHub repo](https://github.com/dfinke/ImportExcel)
    
## Improvements
I will try to improve this script, however if you have any questions or ideas on how to improve the code with new features or redesigning the functions, structure or in general code quality you are more than welcome :)
