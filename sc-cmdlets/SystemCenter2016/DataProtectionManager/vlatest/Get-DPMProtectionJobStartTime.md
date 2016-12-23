---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0BAF26EE-6946-4FF0-BD7C-B8A0F021D236
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionJobStartTime.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionJobStartTime.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionJobStartTime.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMProtectionJobStartTime

## SYNOPSIS
Gets the start time of a protection job.

## SYNTAX

```
Get-DPMProtectionJobStartTime [-ProtectionGroup] <ProtectionGroup> [-JobType] <ProtectionJobType>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMProtectionJobStartTime** cmdlet gets the start time of a protection job.

## EXAMPLES

### Example 1: Get a job start time
```
PS C:\> $PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMProtectionJobStartTime -ProtectionGroup $PGroup -JobType ConsistencyCheck
```

The first command gets the protection group on the System Center 2016 - Data Protection Manager (DPM) server named DPMServer02, and then stores the group in the $PGroup variable.

The second command gets the job start time for the consistency check on the protection group stored in the $PGroup variable.

## PARAMETERS

### -JobType
Specifies the type of job for which options are being set.
The only valid value for this parameter is ConsistencyCheck.

```yaml
Type: ProtectionJobType
Parameter Sets: (All)
Aliases: 
Accepted values: ConsistencyCheck

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group on which this cmdlet operates.
To obtain a **ProtectionGroup** object, use the [Get-DPMProtectionGroup](./Get-DPMProtectionGroup.md) cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DateTime

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Set-DPMProtectionJobStartTime](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionJobStartTime.md)
