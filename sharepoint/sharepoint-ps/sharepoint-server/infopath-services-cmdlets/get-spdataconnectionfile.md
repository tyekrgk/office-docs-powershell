---
title: "Get-SPDataConnectionFile"
ms.author: laurawi
author: LauraWi
manager: laurawi
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3bb713ab-3824-4113-9086-0f9624f23544

description: "Returns a data connection file or a collection of data connection files."
---

# Get-SPDataConnectionFile

Returns a data connection file or a collection of data connection files.
  
```
Get-SPDataConnectionFile [[-Identity] <SPDataConnectionFilePipeBind>] [-AssignmentCollection <SPAssignmentCollection>]
```

## Detailed Description

The **Get-SPDataConnectionFile** cmdlet gets a specified data connection file or a collection of data connection files. If the **Identity** parameter is not specified, the cmdlet returns the collection of data connection files for the farm. 
  
For permissions and the most current information about Windows PowerShell for SharePoint Products, see the online documentation at [Windows PowerShell for SharePoint Server 2016 reference](https://go.microsoft.com/fwlink/p/?LinkId=671715).
  
## Parameters

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|**Identity** <br/> |Optional  <br/> |Microsoft.Office.InfoPath.Server.Cmdlet.SPDataConnectionFilePipeBind  <br/> |Specifies the data file connection to get.  <br/> The type must be a valid GUID, in form 12345678-90ab-cdef-1234-567890bcdefgh; a valid name of a data connection file (for example, DataConnectionFileName1.udcx); or an instance of a valid **SPDataConnectionFile** object.  <br/> |
|**AssignmentCollection** <br/> |Optional  <br/> |Microsoft.SharePoint.PowerShell.SPAssignmentCollection  <br/> |Manages objects for the purpose of proper disposal. Use of objects, such as **SPWeb** or **SPSite**, can use large amounts of memory and use of these objects in Windows PowerShell scripts requires proper memory management. Using the **SPAssignment** object, you can assign objects to a variable and dispose of the objects after they are needed to free up memory. When **SPWeb**, **SPSite**, or **SPSiteAdministration** objects are used, the objects are automatically disposed of if an assignment collection or the **Global** parameter is not used.  <br/> > [!NOTE]> When the **Global** parameter is used, all objects are contained in the global store. If objects are not immediately used, or disposed of by using the **Stop-SPAssignment** command, an out-of-memory scenario can occur.           |
   
## AutoGenParams

|**Parameter**|**Required**|**Type**|**Description**|
|:-----|:-----|:-----|:-----|
|**Identity** <br/> |Optional  <br/> |Microsoft.Office.InfoPath.Server.Cmdlet.SPDataConnectionFilePipeBind  <br/> ||
|**AssignmentCollection** <br/> |Optional  <br/> |Microsoft.SharePoint.PowerShell.SPAssignmentCollection  <br/> ||
   
## Example

---------------EXAMPLE 1--------------
  
```
Get-SPDataConnectionFile
```

This example lists the **Identity**, **DisplayName**, and **WebAccessible** properties ofeach .udcx file. 
  
---------------EXAMPLE 2--------------
  
```
"Sample.udcx" | Get-SPDataConnectionFile
```

This example lists the **Identity**, **DisplayName**, and **WebAccessible** properties of the specified file, named  `Sample.udcx`.
  
---------------EXAMPLE 3--------------
  
```
Get-SPDataConnectionFile | where {$_.Category -eq "Category1"}
```

This example lists the **Identity**, **DisplayName**, and **WebAccessible** properties of all .udcx files with the specified  `Category`.
  
## See also

#### 

[Install-SPDataConnectionFile](install-spdataconnectionfile.md)
  
[Set-SPDataConnectionFile](set-spdataconnectionfile.md)
  
[Uninstall-SPDataConnectionFile](uninstall-spdataconnectionfile.md)
