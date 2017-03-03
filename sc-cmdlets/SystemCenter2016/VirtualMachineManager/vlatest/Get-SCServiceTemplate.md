---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9A6A0EEC-2003-442A-939E-A4E2BF411F36
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCServiceTemplate

## SYNOPSIS
Gets a service template stored in the VMM library.

## SYNTAX

### All (Default)
```
Get-SCServiceTemplate [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCServiceTemplate [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCServiceTemplate** cmdlet gets one or more service templates stored in the Virtual Machine Manager (VMM) library.

## EXAMPLES

### Example 1: Get all service template objects in the library
```
PS C:\> $SvcTemplates = Get-SCServiceTemplate -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "Service" }
PS C:\> $SvcTemplates
```

The first command gets all service template objects on VMMServer01, selects from the results the service template objects that contain Service in their name, and then stores the objects in the $SvcTemplates variable.

The second command displays information about the service template objects to the user.

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
Specifies the name of a VMM object.

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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### ServiceTemplate
This cmdlet returns a **ServiceTemplate** object.

## NOTES

## RELATED LINKS

[New-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCServiceTemplate.md)

[Read-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCServiceTemplate.md)

[Remove-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServiceTemplate.md)

[Resolve-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resolve-SCServiceTemplate.md)

[Set-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCServiceTemplate.md)

[Test-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCServiceTemplate.md)

