---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 2AC262AA-B1A6-487C-A1E6-7A76C98089E6
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionJobStartTime.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionJobStartTime.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionJobStartTime.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMProtectionJobStartTime

## SYNOPSIS
Sets the start time of a protection job.

## SYNTAX

### Edit
```
Set-DPMProtectionJobStartTime [-ProtectionGroup] <ProtectionGroup> [-JobType] <ProtectionJobType>
 [-StartTime] <DateTime> [-MaximumDurationInHours] <Int32> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Remove
```
Set-DPMProtectionJobStartTime [-ProtectionGroup] <ProtectionGroup> [-JobType] <ProtectionJobType> [-Remove]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### OffsetSchedule
```
Set-DPMProtectionJobStartTime [-ProtectionGroup] <ProtectionGroup> [-CatalogOffset] <Int32> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMProtectionJobStartTime** cmdlet sets the start time of a protection job.
The only type of protection job that is currently available is consistency check.
Use the *Remove* parameter to stop a protection job.

## EXAMPLES

### Example 1: Schedule a consistency check on a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup 
PS C:\> Set-DPMProtectionJobStartTime -ProtectionGroup $MPGroup -JobType ConsistencyCheck -StartTime 02:00
PS C:\> Set-DPMProtectionGroup ProtectionGroup $MPGroup
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores it in the $PGroup variable.

The second command makes the protection group in $PGroup modifiable, and stores the result in the $MPGroup variable.

The third command sets the start time of the protection job in $MPGroup.
The command schedules for a consistency check to run on the protection group at 2:00 AM every day.

The final command uses the **Set-DPMProtectionGroup** cmdlet to save your changes.

## PARAMETERS

### -CatalogOffset
Specifies the number of minutes, after the first scheduled recovery point creation time of the SharePoint farm, that System Center 2016 - Data Protection Manager (DPM) creates the catalog.

```yaml
Type: Int32
Parameter Sets: OffsetSchedule
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobType
Specifies the type of job for which options are being set.
The only valid value for this parameter is ConsistencyCheck.

```yaml
Type: ProtectionJobType
Parameter Sets: Edit, Remove
Aliases: 
Accepted values: ConsistencyCheck

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumDurationInHours
Specify the maximum number of hours that DPM can run a job.

```yaml
Type: Int32
Parameter Sets: Edit
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: Edit, Remove
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group.
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

### -Remove
Indicates that DPM stops the protection job.

```yaml
Type: SwitchParameter
Parameter Sets: Remove
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies a start time for the protection job.

```yaml
Type: DateTime
Parameter Sets: Edit
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
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

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMModifiableProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMModifiableProtectionGroup.md)

[Set-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionGroup.md)

