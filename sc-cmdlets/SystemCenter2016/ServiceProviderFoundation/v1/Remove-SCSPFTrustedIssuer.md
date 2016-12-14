---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: ./Get-SCSPFTrustedIssuer.md
schema: 2.0.0
ms.assetid: D4FC2866-FCDD-4B88-81B5-07EDE5FF649D
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Remove-SCSPFTrustedIssuer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Remove-SCSPFTrustedIssuer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Remove-SCSPFTrustedIssuer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSpfTrustedIssuer

## SYNOPSIS
Removes one or more trusted issuer objects.

## SYNTAX

```
Remove-SCSpfTrustedIssuer -Issuer <Issuer[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSPFTrustedIssuer** cmdlet removes one or more trusted issuers from the Service Provider Foundation database.

## EXAMPLES

### Example 1: Remove a trusted issuer
```
PS C:\>$TrustedIssuer = Get-SCSPFTrustedIssuer -ID "938d2412-ba64-497e-b97d-12991087d66c"
PS C:\> Remove-SCSPFTrustedIssuer -Issuer $TrustedIssuer
```

The first command gets the trusted issuer object by its ID and stores the object in the $TrustedIssuer variable.

The second command removes the trusted issuer.

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

### -Issuer
Specifies one or more trusted issuer objects.
To obtain a trusted issuer object, use the Get-SCSPFTrustedIssuer cmdlet.

```yaml
Type: Issuer[]
Parameter Sets: (All)
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

[Get-SCSPFTrustedIssuer](xref:SystemCenter2016/ServiceProviderFoundation/v1/Get-SCSPFTrustedIssuer.md)

[New-SCSPFTrustedIssuer](xref:SystemCenter2016/ServiceProviderFoundation/v1/New-SCSPFTrustedIssuer.md)

