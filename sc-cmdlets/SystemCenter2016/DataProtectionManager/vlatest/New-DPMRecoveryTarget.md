---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7A80C32C-DFFB-49F1-AF26-A0592898DBB6
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryTarget.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryTarget.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryTarget.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-DPMRecoveryTarget

## SYNOPSIS

## SYNTAX

### Restricted (Default)
```
New-DPMRecoveryTarget [-Type] <AmDatasourceType> [-RecoveryTarget] <String> [-RecoveredFilesPath] <String>
 [<CommonParameters>]
```

### Unrestricted
```
New-DPMRecoveryTarget [-Type] <AmDatasourceType> [-RecoveryTarget] <String> [-Unrestricted]
 [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### 1:
```
PS C:\>
```

### 2:
```
PS C:\>
```

## PARAMETERS

### -RecoveredFilesPath


```yaml
Type: String
Parameter Sets: Restricted
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryTarget


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type


```yaml
Type: AmDatasourceType
Parameter Sets: (All)
Aliases: 
Accepted values: SqlDatabase, SqlInstance

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unrestricted


```yaml
Type: SwitchParameter
Parameter Sets: Unrestricted
Aliases: 

Required: True
Position: 3
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

[Add-DPMRecoveryTarget](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryTarget.md)

[Get-DPMRecoveryTarget](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryTarget.md)

[Remove-DPMRecoveryTarget](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryTarget.md)

