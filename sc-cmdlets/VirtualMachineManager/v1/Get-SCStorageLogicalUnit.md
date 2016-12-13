---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCStorageLogicalUnit.md
schema: 2.0.0
ms.assetid: E504C9AE-3318-49BF-BC13-2EFE449D85BA
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStorageLogicalUnit.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStorageLogicalUnit.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStorageLogicalUnit.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageLogicalUnit

## SYNOPSIS
Gets a storage logical unit object.

## SYNTAX

### All (Default)
```
Get-SCStorageLogicalUnit [-VMMServer <ServerConnection>] [[-Name] <String>] [-VM <VM[]>] [-All]
 [<CommonParameters>]
```

### ID
```
Get-SCStorageLogicalUnit [-VMMServer <ServerConnection>] [[-Name] <String>] [-VM <VM[]>] [-ID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageLogicalUnit** cmdlet gets a storage logical unit object from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Get a storage logical unit by its name
```
PS C:\>Get-SCStorageLogicalUnit -Name "LUN01"
```

This command gets the storage logical unit object named LUN01 and displays information about the storage logical unit to the user.

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

### -VM
Specifies an array of virtual machine objects.

```yaml
Type: VM[]
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

### StorageLogicalUnit
This cmdlet returns a **StorageLogicalUnit** object.

## NOTES

## RELATED LINKS

[New-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/New-SCStorageLogicalUnit.md)

[Register-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Register-SCStorageLogicalUnit.md)

[Remove-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Remove-SCStorageLogicalUnit.md)

[Set-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Set-SCStorageLogicalUnit.md)

[Unregister-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Unregister-SCStorageLogicalUnit.md)

