---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMDatasource.md
schema: 2.0.0
ms.assetid: 5A508EC8-952C-49FE-82FA-7B3F1982C86F
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Dismount-DPMRecoveryPoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Dismount-DPMRecoveryPoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Dismount-DPMRecoveryPoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Dismount-DPMRecoveryPoint

## SYNOPSIS
Dismounts the replica or recovery point VHD of a data source.

## SYNTAX

```
Dismount-DPMRecoveryPoint [-Datasource] <Datasource> [[-RecoveryPoint] <RecoverySource>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Dismount-DPMRecoveryPoint** cmdlet dismounts a previously mounted replica or recovery point VHD of the specified data source.
Keeping the VHDs mounted can result in backup job failures.

## EXAMPLES

### Example 1: Dismount a replica VHD
```
PS C:\>$ProtectionGroup = Get-DPMProtectionGroup
PS C:\> $DataSource = Get-DPMDatasource -ProtectionGroup $ProtectionGroup[0]
PS C:\> Dismount-DPMRecoveryPoint -Datasource $DataSource
```

The first command uses the Get-DPMProtectionGroup cmdlet to get the protection groups on the Data Protection Manager (DPM) server, and then stores them in the $ProtectionGroup variable.

The second command uses the Get-DPMDatasource cmdlet to get the data sources in the first protection group of the $ProtectionGroup array.
The command stores the data sources in the $DataSource variable.

The third command dismounts the replica VHD of the first data source in the $DataSource array.

### Example 2: Dismount a recovery point VHD
```
PS C:\>$ProtectionGroup = Get-DPMProtectionGroup
PS C:\> $DataSource = Get-DPMDatasource -ProtectionGroup $ProtectionGroup[0]
PS C:\> $RecoveryPoints = Get-DPMRecoveryPoint -Datasource $Datasource[0]
PS C:\> Dismount-DPMRecoveryPoint -Datasource $DataSource[0] -RecoveryPoint $RecoveryPoints[0]
```

The first command uses the Get-DPMProtectionGroup cmdlet to get the protection groups on the Data Protection Manager (DPM) server, and then stores them in the $ProtectionGroup variable.

The second command uses the Get-DPMDatasource cmdlet to get the data sources in the first protection group in the $ProtectionGroup array.
The command stores the data sources in the $DataSource variable.

The third command uses the Get-DPMRecoveryPoint cmdlet to get the recovery points of the first data source in the $DataSource array, and then stores them in the $RecoveryPoints variable.

The fourth command dismounts the VHD corresponding to the first recovery point in the $RecoveryPoints array.

## PARAMETERS

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

### -Datasource
Specifies the data source whose replica or recovery point VHD you want to dismount.

```yaml
Type: Datasource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPoint
Specifies a recovery point of the data source.
If this parameter is specified, the VHD corresponding to this recovery point is dismounted.

```yaml
Type: RecoverySource
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
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

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMRecoveryPoint.md)

[Mount-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/v1/Mount-DPMRecoveryPoint.md)

[New-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/v1/New-DPMRecoveryPoint.md)

[Remove-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/v1/Remove-DPMRecoveryPoint.md)

