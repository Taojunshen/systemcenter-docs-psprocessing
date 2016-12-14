---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: ./Get-SCSPFStamp.md
schema: 2.0.0
ms.assetid: E1107693-68A8-4876-A160-2F5388E93AD1
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Remove-SCSPFStamp.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Remove-SCSPFStamp.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Remove-SCSPFStamp.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSpfStamp

## SYNOPSIS
Removes one or more stamps.

## SYNTAX

### Empty (Default)
```
Remove-SCSpfStamp [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromStampParameterSetName
```
Remove-SCSpfStamp -Stamp <Stamp[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSPFStamp** cmdlet removes one or more stamp objects from the Service Provider Foundation database.

## EXAMPLES

### Example 1: Remove a stamp
```
PS C:\>$ContosoStamp = Get-SCSPFStamp -Name "Contoso"
PS C:\> Remove-SCSPFStamp -Stamp $ContosoStamp
```

The first command gets the stamp object named Contoso and stores it in the $Stamp variable.

The second command removes the stamp.

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

### -Stamp
Specifies the name of one or more stamp objects.
To obtain a stamp, use the Get-SCSPFStamp cmdlet.

```yaml
Type: Stamp[]
Parameter Sets: FromStampParameterSetName
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

[Get-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/v1/Get-SCSPFStamp.md)

[New-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/v1/New-SCSPFStamp.md)

[Set-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/v1/Set-SCSPFStamp.md)

