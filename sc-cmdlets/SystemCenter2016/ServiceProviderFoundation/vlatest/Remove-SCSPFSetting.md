---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8EFBA1FB-0F31-4650-9234-8571B10D9401
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCSpfSetting

## SYNOPSIS
Removes a setting from a database or a portal endpoint.

## SYNTAX

### Empty (Default)
```
Remove-SCSpfSetting [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromSettingParameterSetName
```
Remove-SCSpfSetting -SpfSetting <SpfSetting[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSPFSetting** cmdlet removes a setting from a database connection string or a portal endpoint connection string.

## EXAMPLES

### Example 1: Remove a setting
```
PS C:\>$Setting = Get-SCSPFSetting -Name "ContosoSetting" | Remove-SCSPFSetting
```

This command obtains a setting by name and then passes it to the **Remove-SCSPFSetting** cmdlet by using the pipeline operator.

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

### -SpfSetting
Specifies one or more settings to remove.

```yaml
Type: SpfSetting[]
Parameter Sets: FromSettingParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[Get-SCSPFSetting](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFSetting.md)

[New-SCSPFSetting](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFSetting.md)

