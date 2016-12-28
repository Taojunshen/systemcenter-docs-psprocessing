---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 709863A0-809E-4F86-8D0C-A6389C7BC3D1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMHostProfile

## SYNOPSIS
Gets a host profile.

## SYNTAX

### All (Default)
```
Get-SCVMHostProfile [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### NameParameter
```
Get-SCVMHostProfile [[-Name] <String>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ID
```
Get-SCVMHostProfile [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHostProfile** cmdlet gets one or more host profiles.

## EXAMPLES

### Example 1: Get all host profiles
```
PS C:\> Get-SCVMHostProfile -All
```

This command returns information about all host profiles in the VMM library.

### Example 2: Get a host profile by its name
```
PS C:\> Get-SCVMHostProfile -Name "HostProfile01"
```

This command returns information about the host profile named HostProfile01.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
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
Parameter Sets: NameParameter
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

### HostProfile[]
This cmdlet returns one or more **HostProfile** objects.

## NOTES

## RELATED LINKS

[New-SCVMHostProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHostProfile.md)

[Remove-SCVMHostProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostProfile.md)

[Set-SCVMHostProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostProfile.md)

