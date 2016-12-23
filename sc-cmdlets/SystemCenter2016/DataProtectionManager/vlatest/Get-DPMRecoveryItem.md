---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5C9275E7-C29E-495E-80DE-D8EA68ED427C
updated_at: 12/23/2016 8:49 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/9548fb95a3c4060e9bbb3fa5f39ca1ed43a4f218/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMRecoveryItem

## SYNOPSIS
Gets a DPM Recovery item.

## SYNTAX

```
Get-DPMRecoveryItem [-DpmRole] <DpmRole> [-Type] <AmDatasourceType> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMRecoveryItem** cmdlet gets a DPM Recovery item.

## EXAMPLES

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-DPMRecoveryItem](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryItem.md)

[Remove-DPMRecoveryItem](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryItem.md)
