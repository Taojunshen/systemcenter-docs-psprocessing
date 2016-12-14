---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: ED8CFD12-7460-4422-81E6-7CE563F3D760
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroupSla.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroupSla.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroupSla.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMProtectionGroupSla

## SYNOPSIS
Gets the SLA for a protection group.

## SYNTAX

### ProtectionGroup (Default)
```
Get-DPMProtectionGroupSla [-ProtectionGroup] <ProtectionGroup> [<CommonParameters>]
```

### ProtectionGroupId
```
Get-DPMProtectionGroupSla [-ProtectionGroupId] <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMProtectionGroupSla** cmdlet gets the service level agreement (SLA) for a System Center 2016 - Data Protection Manager (DPM) protection group.
An SLA is an integer value that defines a period, in hours.
For more information, see the Set-DPMProtectionGroupSla cmdlet.

## EXAMPLES

### Example 1: Get the SLA for a protection group object
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMProtectionGroupSLA -ProtectionGroup $PGroup
```

The first command gets the protection group on the DPM server named DPMServer02.
The command stores the protection group in the $PGroup variable.

The second command gets the SLA for the protection group stored in $PGroup.

### Example 2: Get the SLA for a protection group specified by ID
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMProtectionGroupSLA -ProtectionGroupId $PGroup.ProtectionGroupId
```

The first command gets the protection group on the DPM server named DPMServer02.
The command stores the protection group in the $PGroup variable.

The second command gets the SLA for the protection group that has the GUID specified by the **ProtectionGroupId** property of $PGroup.

## PARAMETERS

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets an SLA.
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
This cmdlet gets the SLA for the protection group that this parameter specifies.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-DPMProtectionGroupSla](xref:SystemCenter2016/DataProtectionManager/v1.0/Set-DPMProtectionGroupSla.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroup.md)

