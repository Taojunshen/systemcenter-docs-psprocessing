---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D6599E18-E2CA-4104-A3DB-AEA7E1EBE8AE
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMChildDatasource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMChildDatasource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMChildDatasource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-DPMChildDatasource

## SYNOPSIS
Removes a data source or child data source from a protection group.

## SYNTAX

### StopProtection (Default)
```
Remove-DPMChildDatasource [-ProtectionGroup] <ProtectionGroup> [-ChildDatasource] <ProtectableObject[]>
 [-KeepDiskData] [-KeepTapeData] [-KeepOnlineData] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RejectCloud
```
Remove-DPMChildDatasource [-ProtectionGroup] <ProtectionGroup> [-ChildDatasource] <ProtectableObject[]>
 [-Online] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMChildDatasource** cmdlet removes a data source or child data source from a System Center 2016 - Data Protection Manager (DPM) protection group.
Child data sources are files or folders on a protected volume.

If you remove a data source using this cmdlet, it is equivalent to setting an exclusion.

## EXAMPLES

### Example 1: Remove a child data source
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup $PGroup[0]
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> Remove-DPMChildDatasource -ProtectionGroup $MPGroup -ChildDatasource $PObjects[8]
```

The first command gets all protection groups from the DPM server named DPMServer07, and then stores these groups in the $PGroup variable.
You cannot edit these protection groups.

The second command gets the first member of the $PGroup array in editable mode, and then stores this protection group in the $MPGroup variable.

The third command gets the data source for the list of protection groups in $PGroup, and then stores this data source in the $PObjects variable.

The final command uses standard array notation to specify the ninth element of the $PObjects array.
The command removes that data source from the protection group stored in $MPGroup.

## PARAMETERS

### -ChildDatasource
Specifies an array of data sources, such as folders in a file system, that DPM can protect individually.

```yaml
Type: ProtectableObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeepDiskData
Indicates that the cmdlet keeps existing data on a disk.

```yaml
Type: SwitchParameter
Parameter Sets: StopProtection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepOnlineData
Indicates that the cmdlet keeps replicas even after protection ends.
You must also specify the *KeepDiskData* parameter to enable this parameter.

```yaml
Type: SwitchParameter
Parameter Sets: StopProtection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeepTapeData
Indicates that the cmdlet keeps existing data on a tape.

```yaml
Type: SwitchParameter
Parameter Sets: StopProtection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Online
Indicates that online protection is enabled.

```yaml
Type: SwitchParameter
Parameter Sets: RejectCloud
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ProtectionGroup
Specifies a protection group from which this cmdlet removes data sources.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ProtectionGroup

## NOTES

## RELATED LINKS

[Add-DPMChildDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMChildDatasource.md)

[Get-DPMChildDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMChildDatasource.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMModifiableProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMModifiableProtectionGroup.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

