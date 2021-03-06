---
title: "Connect to Exchange Online Protection PowerShell"
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 7/10/2017
ms.audience: Admin
ms.topic: article
ms.service: eop
localization_priority: Normal
ms.assetid: 054e0fd7-d465-4572-93f8-a00a9136e4d1
description: "Use remote PowerShell to connect to an Exchange Online Protection organization"
---

# Connect to Exchange Online Protection PowerShell

Exchange Online Protection PowerShell allows you to manage your Exchange Online Protection settings from the command line. You use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online Protection. It's a simple three-step process where you enter your Office 365 credentials, provide the required connection settings, and then import the Exchange Online Protection cmdlets into your local Windows PowerShell session so that you can use them.
  
## What do you need to know before you begin?

- Estimated time to complete: 5 minutes
    
- You can use the following versions of Windows:
    
  - Windows 10
    
  - Windows 8.1
    
  - Windows Server 2016
    
  - Windows Server 2012 or Windows Server 2012 R2
    
  - Windows 7 Service Pack 1 (SP1)\*
    
  - Windows Server 2008 R2 SP1\*
    
  \* You need to install the Microsoft.NET Framework 4.5 or later and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0. For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).
    
- Windows PowerShell needs to be configured to run scripts, and by default, it isn't. You get the following error when you try to connect:
    
     `Files cannot be loaded because running scripts is disabled on this system. Provide a valid certificate with which to sign the files.`
    
    To enable Windows PowerShell to run signed scripts, run the following command in an elevated Windows PowerShell window (a Windows PowerShell window you open by selecting **Run as administrator**):
    
  ```
  Set-ExecutionPolicy RemoteSigned
  ```

    You need to configure this setting only once on your computer, not every time you connect.
    
> [!TIP]
> Having problems? Ask for help in the Exchange forums. Visit the forums at: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## Connect to Exchange Online Protection

1. On your local computer, open Windows PowerShell and run the following command.
    
   ```
   $UserCredential = Get-Credential
   ```

    In the **Windows PowerShell Credential Request** dialog box, type your work or school account and password, and then click **OK**.
    
2. Run the following command.
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

     **Notes**:
    
   - For Office 365 Germany, use the  _ConnectionUri_ value: `https://ps.protection.outlook.de/powershell-liveid/`
    
   - For Exchange Online Protection subscriptions that are Exchange Enterprise CAL with Services (includes data loss prevention (DLP) and reporting using web services), use the  _ConnectionUri_ value: `https://outlook.office365.com/powershell-liveid/`
    
3. Run the following command.
    
   ```
   Import-PSSession $Session
   ```

      [!NOTE]
      Be sure to disconnect the remote PowerShell session when you're finished. If you close the Windows PowerShell window without disconnecting the session, you could use up all the remote PowerShell sessions available to you, and you'll need to wait for the sessions to expire. To disconnect the remote PowerShell session, run the following command: 
  
   ```
   Remove-PSSession $Session
   ```

## How do you know this worked?

After Step 3, the Exchange Online Protection cmdlets are imported into your local Windows PowerShell session and tracked by a progress bar. If you don't receive any errors, you connected successfully. A quick test is to run an Exchange Online Protection cmdlet, for example, **Get-TransportRule**, and see the results.
  
If you receive errors, check the following requirements:
  
- A common problem is an incorrect password. Run the three steps again and pay close attention to the user name and password you enter in Step 1.
    
- To help prevent denial-of-service (DoS) attacks, you're limited to three open remote PowerShell connections to your Exchange Online Protection organization.
    
- TCP port 80 traffic needs to be open between your local computer and Office 365. It's probably open, but it's something to consider if your organization has a restrictive Internet access policy.
    
## See also

The cmdlets that you use in this topic are Windows PowerShell cmdlets. For more information about these cmdlets, see the following topics.
  
- [Get-Credential](https://go.microsoft.com/fwlink/p/?LinkId=389618)
    
- [New-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389621)
    
- [Import-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389619)
    
- [Remove-PSSession](https://go.microsoft.com/fwlink/p/?LinkId=389620)
    
- [Set-ExecutionPolicy](https://go.microsoft.com/fwlink/p/?LinkId=389623)