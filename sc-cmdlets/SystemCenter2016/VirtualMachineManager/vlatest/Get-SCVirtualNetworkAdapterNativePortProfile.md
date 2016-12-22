---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2A196DA3-DBA5-4960-B806-3EDF4D2C66B6
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterNativePortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterNativePortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterNativePortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualNetworkAdapterNativePortProfile

## SYNOPSIS
Gets a virtual network adapter native port profile.

## SYNTAX

### All (Default)
```
Get-SCVirtualNetworkAdapterNativePortProfile [-VMMServer <ServerConnection>] [[-Name] <String>]
 [<CommonParameters>]
```

### ById
```
Get-SCVirtualNetworkAdapterNativePortProfile [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualNetworkAdapterNativePortProfile** cmdlet gets one or more virtual network adapter native port profiles.
You can retrieve all profiles, or a single profile by its name or ID.

## EXAMPLES

### Example 1: Get a virtual network adapter native port profile by its name
```
PS C:\> Get-SCVirtualNetworkAdapterNativePortProfile -Name "VirtualNetworkAdapterNativePortProf01"
```

This command retrieves the virtual network adapter native port profile object named VirtualNetworkAdapterNativePortProf01.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ById
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

## NOTES

## RELATED LINKS

[New-SCVirtualNetworkAdapterNativePortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterNativePortProfile.md)

[Remove-SCVirtualNetworkAdapterNativePortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapterNativePortProfile.md)

[Set-SCVirtualNetworkAdapterNativePortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterNativePortProfile.md)

