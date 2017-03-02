---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DE66667B-EE2E-4295-A418-9EA53DA4E0EF
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTrustedIssuer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTrustedIssuer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTrustedIssuer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCSpfTrustedIssuer

## SYNOPSIS
Creates a trusted issuer for claims-based authentication.

## SYNTAX

```
New-SCSpfTrustedIssuer -Key <String> -Name <String> [-Tenant <Tenant>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSPFTrustedIssuer** cmdlet creates certification credentials for claims-based authentication in Service Provider Foundation.
The hoster obtains the public key of the key-value pair of the certificate from the tenant or on behalf of the tenant.
Then, the trusted issuer object can validate signed tokens from the tenant so that access to resources can be granted.

## EXAMPLES

### Example 1: Create a trusted issuer
```
PS C:\>New-SCSPFTrustedIssuer -Key $Key -Name "Contoso"
```

This command creates a trusted issuer with a previously defined key and a specified name.

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

### -Key
Specifies the public key that validates a signed token submitted by a tenant in claims-based authentication.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name to give to the trusted issuer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies a tenant object to associate with the new trusted issuer.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Get-SCSPFTrustedIssuer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFTrustedIssuer.md)

[Remove-SCSPFTrustedIssuer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFTrustedIssuer.md)

