---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7F493259-54CA-4F69-90B8-DA49CD797650
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Set-DPMProtectionGroupSla.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Set-DPMProtectionGroupSla.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Set-DPMProtectionGroupSla.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMProtectionGroupSla

## SYNOPSIS
Sets an SLA for a protection group.

## SYNTAX

### ProtectionGroup (Default)
```
Set-DPMProtectionGroupSla [-ProtectionGroup] <ProtectionGroup> [-SLAInHours] <Int32> [<CommonParameters>]
```

### ProtectionGroupId
```
Set-DPMProtectionGroupSla [-ProtectionGroupId] <Guid> [-SLAInHours] <Int32> [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMProtectionGroupSla** cmdlet sets a service level agreement (SLA) for a protection group.
An SLA defines the period, in hours, during which System Center 2016 - Data Protection Manager (DPM) should create at least one recovery point of each data source in the protection group.
An SLA of 24 for a protection group means that each data source in that protection group should have at least one recovery point per day.
If a source does not have a recovery point within that time, DPM raises an SLA violation alert for the data source.
If you configured a backup window by using the Set-DPMBackupWindow cmdlet, the time window for checking SLA violations starts at the start of the backup window.
If you have not configured a backup window, the time window for checking SLA violation starts at midnight.

## EXAMPLES

### Example 1: Set an SLA for a protection group object
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02" | Where {$_.FriendlyName -like "*ContosoPG02*"}
PS C:\> Set-DPMProtectionGroupSla -ProtectionGroup $PGroup -SLAInHours 12
```

The first command gets protection groups on the DPM server named DPMServer02.
This command passes the results to the **Where-Object** cmdlet.
That cmdlet drops all groups except ones that match the specified friendly name.
For more information, type `Get-Help Where-Object`.
The command stores the protection group in the $PGroup variable.

The second command sets an SLA of 12 hours for the protection group in $PGroup.

### Example 2: Set an SLA for a protection group specified by ID
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02" | Where {$_.FriendlyName -like "*ContosoPG02*"}
PS C:\> Set-DPMProtectionGroupSla -ProtectionGroupId $PGroup.ProtectionGroupId -SLAInHours 12
```

The first command gets protection groups on the DPM server named DPMServer02.
This command passes the results to the **Where-Object** cmdlet.
The command stores the protection group in the $PGroup variable.

The second command sets an SLA of 12 hours for the protection group that has the GUID specified by the **ProtectionGroupId** property of $PGroup.

## PARAMETERS

### -ProtectionGroup
Specifies a protection group for which this cmdlet sets an SLA.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: ProtectionGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionGroupId
Specifies the unique identifier for a protection group.
This cmdlet sets the SLA for the protection group that this parameter specifies.

```yaml
Type: Guid
Parameter Sets: ProtectionGroupId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SLAInHours
Specifies the period, in hours, during which DPM should create at least one recovery point of each data source in the protection group.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[Get-DPMProtectionGroupSla](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroupSla.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroup.md)

[Set-DPMBackupWindow](xref:SystemCenter2016/DataProtectionManager/v1.0/Set-DPMBackupWindow.md)

