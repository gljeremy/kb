[[AAD Module]]


PoC code repo: https://wtwdst.visualstudio.com/HRPortal/_git/dnn.azureadprovider

A PowerShell function creates app registration with logon name claim for DNN Azure AD Provider

## App Registration

App Registration: https://portal.azure.com/#view/Microsoft_AAD_RegisteredApps/ApplicationMenuBlade/~/Overview/appId/019ff00f-ce1a-49c9-910f-5a36a6d9ea39/isMSAApp~/false

Request => Service Principal => Microsoft Graph API

## Service Principal
Configuration responsible for giving domain/username
Single Sign-On => Edit => Manage Claim

https://portal.azure.com/#view/Microsoft_AAD_IAM/ManagedAppMenuBlade/~/Overview/objectId/2c282fa8-df0b-4701-8505-0a86045d069e/appId/019ff00f-ce1a-49c9-910f-5a36a6d9ea39

## AAD Module Setup
One time setup of all settings
![[Pasted image 20230725102213.png]]


Willis login => GetOrCreateOnRoot(User) => Redirect to tenant


Logout code to add in HRPortalAuth
![[Pasted image 20230725101810.png]]



AAD Module code does the logging out for you
![[Pasted image 20230725101918.png]]
HRPortalAuth references new package for Logout procedure.  If auth is AAD, then logout of AAD.
1. Cookie gives a clue on which auth type.
2. Property gives a clue on which auth type

