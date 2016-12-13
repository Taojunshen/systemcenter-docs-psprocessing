---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 073F6CD7-0501-4BE5-9298-CC5A1570C4A1
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMReplicaCreationMethod.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMReplicaCreationMethod.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMReplicaCreationMethod.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMReplicaCreationMethod

## SYNOPSIS
Gets the replica creation method for a protection group.

## SYNTAX

```
Get-DPMReplicaCreationMethod [-ProtectionGroup] <ProtectionGroup> [-Reserved] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMReplicaCreationMethod** cmdlet gets the replica creation method for a protection group.
The replica creation method specifies when System Center 2016 - Data Protection Manager (DPM) initiates the creation of a replica.

You can change the replica creation method by using the Set-DPMReplicaCreationMethod cmdlet.

## EXAMPLES

### Example 1: Get the replica creation method
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMReplicaCreationMethod -ProtectionGroup $PGroup
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the group in the $PGroup variable.

The second command gets the replica creation method for the protection group in $PGroup.

## PARAMETERS

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets the replica creation method.
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

### -Reserved
Specifies an internal parameter.
Do not use.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ReplicaCreationMethod

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Set-DPMReplicaCreationMethod](xref:DataProtectionManager/v1/Set-DPMReplicaCreationMethod.md)

