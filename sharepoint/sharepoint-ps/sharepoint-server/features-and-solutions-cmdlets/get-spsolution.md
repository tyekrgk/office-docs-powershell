---
title: "Get-SPSolution"
ms.author: laurawi
author: LauraWi
manager: laurawi
ms.date: 12/3/2015
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 88111c7a-9d56-40da-a766-a8ea1945c697

description: "Returns a specified SharePoint solution."
---

# Get-SPSolution

Returns a specified SharePoint solution.
  
```
Get-SPSolution [[-Identity] <SPSolutionPipeBind>] [-AssignmentCollection <SPAssignmentCollection>]
```

## Detailed Description

The **Get-SPSolution** cmdlet returns a specified SharePoint solution. If the **Identity** parameter is not specified, this cmdlet returns the collection of all installed SharePoint solutions in the farm. 
  
For permissions and the most current information about Windows PowerShell for SharePoint Products, see the online documentation at [Windows PowerShell for SharePoint Server 2016 reference](https://go.microsoft.com/fwlink/p/?LinkId=671715).
  
## Parameters

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|**Identity** <br/> |Optional  <br/> |Microsoft.SharePoint.PowerShell.SPSolutionPipeBind  <br/> |Specifies the SharePoint solution to get.  <br/> The type must be a valid GUID, in the form 12345678-90ab-cdef-1234-567890bcdefgh; a valid name of a SharePoint solution (for example, SPSolution1); or an instance of a valid **SPSolution** object.  <br/> |
|**AssignmentCollection** <br/> |Optional  <br/> |Microsoft.SharePoint.PowerShell.SPAssignmentCollection  <br/> |Manages objects for the purpose of proper disposal. Use of objects, such as **SPWeb** or **SPSite**, can use large amounts of memory and use of these objects in Windows PowerShell scripts requires proper memory management. Using the **SPAssignment** object, you can assign objects to a variable and dispose of the objects after they are needed to free up memory. When **SPWeb**, **SPSite**, or **SPSiteAdministration** objects are used, the objects are automatically disposed of if an assignment collection or the **Global** parameter is not used.  <br/> > [!NOTE]> When the **Global** parameter is used, all objects are contained in the global store. If objects are not immediately used, or disposed of by using the **Stop-SPAssignment** command, an out-of-memory scenario can occur.           |
   
## AutoGenParams

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|**Identity** <br/> |Optional  <br/> |Microsoft.SharePoint.PowerShell.SPSolutionPipeBind  <br/> ||
|**AssignmentCollection** <br/> |Optional  <br/> |Microsoft.SharePoint.PowerShell.SPAssignmentCollection  <br/> ||
   
## Example

------------------EXAMPLE------------------
  
```
Get-SPSolution
```

This example returns the collection of all installed SharePoint solutions in the farm.
  
## See also

#### 

[Get-SPSolution](get-spsolution.md)
  
[Add-SPSolution](add-spsolution.md)
  
[Update-SPSolution](update-spsolution.md)
  
[Uninstall-SPSolution](uninstall-spsolution.md)
  
[Remove-SPSolution](remove-spsolution.md)
  
[Install-SPSolution](install-spsolution.md)
  
[Remove-SPSolutionDeploymentLock](remove-spsolutiondeploymentlock.md)
