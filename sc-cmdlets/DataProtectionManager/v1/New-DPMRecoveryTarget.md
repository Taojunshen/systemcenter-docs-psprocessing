---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7A80C32C-DFFB-49F1-AF26-A0592898DBB6
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/New-DPMRecoveryTarget.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/New-DPMRecoveryTarget.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/New-DPMRecoveryTarget.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
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

[Add-DPMRecoveryTarget](xref:DataProtectionManager/v1/Add-DPMRecoveryTarget.md)

[Get-DPMRecoveryTarget](xref:DataProtectionManager/v1/Get-DPMRecoveryTarget.md)

[Remove-DPMRecoveryTarget](xref:DataProtectionManager/v1/Remove-DPMRecoveryTarget.md)

