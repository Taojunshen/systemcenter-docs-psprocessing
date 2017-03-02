---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A4231AB4-10C8-41CD-9380-80099BA9FC93
updated_at: 12/20/2016 10:56 PM
ms.date: 12/20/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/39ebc8b68768998222371964f8e90b8160cbfe0a/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-DPMRecoveryItem

## SYNOPSIS
Adds a DPM recovery item.

## SYNTAX

### SqlInstances
```
Add-DPMRecoveryItem [-DpmRole] <DpmRole> [-Type] <AmDatasourceType> [-SqlInstances] <String[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Datasources
```
Add-DPMRecoveryItem [-DpmRole] <DpmRole> [-Type] <AmDatasourceType> [-Datasources] <SQLDataSource[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DPMRecoveryItem** cmdlet adds a recovery item to a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

## PARAMETERS

### -Datasources


```yaml
Type: SQLDataSource[]
Parameter Sets: Datasources
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DpmRole
Specifies a DPM role that this cmdlet modifies.
To obtain a DPM role object, use the [Get-DPMRole](./Get-DPMRole.md) cmdlet.

```yaml
Type: DpmRole
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlInstances


```yaml
Type: String[]
Parameter Sets: SqlInstances
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies an array of DPM job types.

```yaml
Type: AmDatasourceType
Parameter Sets: (All)
Aliases: 
Accepted values: SqlDatabase, SqlInstance

Required: True
Position: 2
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

## NOTES

## RELATED LINKS

[Get-DPMRecoveryItem](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryItem.md)

[Remove-DPMRecoveryItem](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryItem.md)
