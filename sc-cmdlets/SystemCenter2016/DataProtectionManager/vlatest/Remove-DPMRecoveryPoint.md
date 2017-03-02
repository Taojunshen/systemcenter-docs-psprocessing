---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A7EAB595-94EC-4F04-9D48-443C5089B200
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryPoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryPoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryPoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-DPMRecoveryPoint

## SYNOPSIS
Removes a recovery point from tape or disk.

## SYNTAX

```
Remove-DPMRecoveryPoint [-RecoveryPoint] <RecoverySource> [-ForceDeletion] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMRecoveryPoint** cmdlet removes a recovery point from tape or disk.
If a recovery point exists in multiple locations, for example, on disk and tape, or two tapes, use the Get-DPMRecoveryPointLocation cmdlet to get the location of the recovery point.

## EXAMPLES

### Example 1: Remove a recovery point
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> $RPoint = Get-DPMRecoveryPoint -Datasource $PObjects
PS C:\> Remove-DPMRecoveryPoint -RecoveryPoint $RPoint
```

The first command gets the protection group on the DPM server named DPMServer02, and stores the results in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group stored in $PGroup.
The command stores the results in the $PObject variable.

The third command gets the recovery point for the for the data source stored in $PObjects, and stores the results in the $RPoint variable.

The final command removes the recovery point stored in $RPoint.

## PARAMETERS

### -ForceDeletion
Indicates that System Center 2016 - Data Protection Manager (DPM) prunes the data source regardless if it is currently running a backup job.

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

### -RecoveryPoint
Specifies a recovery point that this cmdlet removes.
To obtain a recovery point location object, use the Get-DPMRecoveryPoint cmdlet.

```yaml
Type: RecoverySource
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

## NOTES

## RELATED LINKS

[Dismount-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Dismount-DPMRecoveryPoint.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md)

[Mount-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Mount-DPMRecoveryPoint.md)

[New-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryPoint.md)

