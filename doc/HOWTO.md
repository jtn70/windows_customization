# HOWTO
# Progams to install

## Create Symbolic link to code 
```powershell
new-item -ItemType SymbolicLink -Path Code -Target "E:\Code"
```

## WinGet
Install powershell module:
https://github.com/microsoft/winget-cli 

```powershell
Install-Module -Name Microsoft.WinGet.Client
```
Get Winget package Ids into a file:
```powershell
Get-WinGetPackage | Select-Object Id | Out-File -FilePath .\packages.txt
```


## OpenSSH key management
https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement

```powershell
# Commands must be run elevated
Get-Service ssh-agent | Set-Service -StartupType Automatic
Start-Service ssh-agent
Get-Service ssh-agent   # Should return running
Start-Service ssh-agent
```