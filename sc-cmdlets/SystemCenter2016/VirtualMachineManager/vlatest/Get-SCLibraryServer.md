---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5F0CC68F-147F-440B-B7EC-E6206F7E90AB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCLibraryServer

## SYNOPSIS
Gets VMM library server objects.

## SYNTAX

```
Get-SCLibraryServer [-VMMServer <ServerConnection>] [[-ComputerName] <String>] [-ID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLibraryServer** cmdlet gets one or more library server objects from the Virtual Machine Manager (VMM) library.

For more information about library servers, type `Get-Help Add-LibraryServer -Detailed`.

## EXAMPLES

### Example 1: Get all library servers
```
PS C:\> Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com"
```

This command gets all library server objects on VMMServer01 and displays information about these library servers to the user.

Note: The name of a library server is the same as its computer name.

### Example 2: Get a specific library server
```
PS C:\> Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" -ComputerName "LibraryServer01.Contoso.com"
```

This command gets the library object named LibraryServer01 on VMMServer01 and displays information about this library server to the user.

### Example 3: Get all library servers that match specified criteria
```
PS C:\> $LibServers = Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "LibraryServer" }
```

This command gets all library server objects on VMMServer01 whose name includes the string "LibraryServer" (such as LibraryServer01 and LIbraryServer02) and stores these library server objects in the $LibServers variable.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
-  NetBIOS name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LibraryServer
This cmdlet returns a **LibraryServer** object.

## NOTES

## RELATED LINKS

[Add-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryServer.md)

[Remove-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLibraryServer.md)

[Set-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLibraryServer.md)

