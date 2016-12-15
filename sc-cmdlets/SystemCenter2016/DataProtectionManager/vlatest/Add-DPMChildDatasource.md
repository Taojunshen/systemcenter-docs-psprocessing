---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMChildDatasource.md
schema: 2.0.0
ms.assetid: 728BDAB4-7B07-4B69-A6AB-635392AED42F
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMChildDatasource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMChildDatasource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMChildDatasource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-DPMChildDatasource

## SYNOPSIS
Adds a data source or a child data source to a protection group.

## SYNTAX

```
Add-DPMChildDatasource [-ProtectionGroup] <ProtectionGroup> [-ChildDatasource] <ProtectableObject[]> [-Online]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DPMChildDatasource** cmdlet adds a data source or a child data source to a System Center 2016 - Data Protection Manager (DPM) protection group.
Child data sources are folders on a protected volume.

You can override a data source that the **Remove-DPMChildDatasource** cmdlet previously excluded from a protection group by adding the data source to the protection group.

## EXAMPLES

### Example 1: Add a child data source to a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup $PGroup[0]
PS C:\> $PObjects = Get-DPMDatasource -ProductionServer "ProductionServer22"
PS C:\> Add-DPMChildDatasource -ProtectionGroup $MPGroup -ChildDatasource $PObjects[8]
```

The first command gets all protection groups from the DPM server named DPMServer07, and then stores these groups in the $PGroup variable.
You cannot edit these protection groups.

The second command gets the first protection group in the $PGroup array in editable mode, and then stores it in the $MPGroup variable.

The third command gets an array of protected and unprotected data on the production server named ProductionServer22, and then stores the array in the $PObjects variable.

The final command uses standard array notation to specify the ninth element of the $PObjects array.
The command adds that data source to the protection group stored in $MPGroup.

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

### -Online
Indicates that online protection is enabled.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies a protection group to which this cmdlet adds data sources.
To obtain a **ProtectionGroup** object, use the **Get-DPMProtectionGroup** cmdlet.

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

[Get-DPMChildDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMChildDatasource.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMModifiableProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMModifiableProtectionGroup.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Remove-DPMChildDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMChildDatasource.md)

