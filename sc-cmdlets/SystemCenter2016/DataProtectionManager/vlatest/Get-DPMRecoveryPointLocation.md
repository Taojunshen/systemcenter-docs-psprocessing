---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2008B021-62C4-4652-B3EC-EF40137847F3
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPointLocation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPointLocation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPointLocation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-DPMRecoveryPointLocation

## SYNOPSIS
Gets the location of a recovery point.

## SYNTAX

```
Get-DPMRecoveryPointLocation [-RecoveryPoint] <RecoverySource> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMRecoveryPointLocation** cmdlet gets the location of a recovery point.
This cmdlet returns an object that indicates whether the recovery point is located on disk or tape.
If the recovery point is on tape, the cmdlet returns information about the tape.

## EXAMPLES

### Example 1: Get a recovery point location
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObject = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> $RPoint = Get-DPMRecoveryPoint -Datasource $PObject
PS C:\> Get-DPMRecoveryPointLocation -RecoveryPoint $RPoint
```

The first command gets the protection group on the System Center 2016 - Data Protection Manager (DPM) server named DPMServer02.
The command stores the protection group in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group in $PGroup.
The command stores the results in the $PObject variable.

The third command gets the recovery point for the data source in $DSource, and then stores the recovery point in the $RPoint variable.

The fourth command gets the location for the recovery point in $RPoint.

## PARAMETERS

### -RecoveryPoint
Specifies a recovery point for which this cmdlet gets the location.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### RecoveryPointLocation

## NOTES

## RELATED LINKS

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md)

[Remove-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryPoint.md)

[New-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryPoint.md)

