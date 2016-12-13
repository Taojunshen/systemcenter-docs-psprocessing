---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageLogicalUnit.md
schema: 2.0.0
ms.assetid: E292BB0D-958D-40A9-A530-6A0C59B731A7
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCStorageLogicalUnit.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCStorageLogicalUnit.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCStorageLogicalUnit.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageLogicalUnit

## SYNOPSIS
Updates the metadata of a storage logical unit object.

## SYNTAX

```
Set-SCStorageLogicalUnit [-VMHostGroup <HostGroup>] [-LogicalUnitCopySource <StorageLogicalUnit>]
 [-StorageLogicalUnit] <StorageLogicalUnit> [-Name <String>] [-Description <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageLogicalUnit** cmdlet updates the metadata of a storage logical unit object.
**Set-SCStorageLogicalUnit** does not modify the data on the logical unit itself.

## EXAMPLES

### Example 1: Update the name of a storage logical unit
```
PS C:\>$LogicalUnit = Get-SCStorageLogicalUnit -Name "LUN01"
PS C:\> Set-SCStorageLogicalUnit -StorageLogicalUnit $LogicalUnit -Name "New Name for Logical Unit"
```

The first command gets the logical unit object named LUN01 and stores the object in the $LogicalUnit variable.

The second command changes the name of the logical unit object stored in $LogicalUnit to New Name for Logical Unit.

### Example 2: Allocate storage to a host group
```
PS C:\>$LU = Get-SCStorageLogicalUnit -Name "LUN01"
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "All Hosts"
PS C:\> Set-SCStorageLogicalUnit -StorageLogicalUnit $LU -VMHostGroup $HostGroup
```

The first command gets the storage logical unit object named LUN01 and stores the object in the $LU variable

The second command gets the host group object named All Hosts and stores the object in the $HostGroup variable.

The last command allocates LUN01 to host group All Hosts.

## PARAMETERS

### -Description
Specifies a description for the storage logical unit.

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

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -LogicalUnitCopySource
Specifies a storage logical unit from which a clone is copied.

```yaml
Type: StorageLogicalUnit
Parameter Sets: (All)
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

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

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageLogicalUnit
Specifies a storage logical unit object.

```yaml
Type: StorageLogicalUnit
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Get-SCStorageLogicalUnit.md)

[Get-SCVMHostGroup](xref:VirtualMachineManager/v1/Get-SCVMHostGroup.md)

[New-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/New-SCStorageLogicalUnit.md)

[Register-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Register-SCStorageLogicalUnit.md)

[Remove-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Remove-SCStorageLogicalUnit.md)

[Unregister-SCStorageLogicalUnit](xref:VirtualMachineManager/v1/Unregister-SCStorageLogicalUnit.md)

