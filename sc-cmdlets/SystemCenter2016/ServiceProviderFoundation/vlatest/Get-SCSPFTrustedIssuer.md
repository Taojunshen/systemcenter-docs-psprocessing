---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9EEC1EE8-3928-4799-A39A-8C2BECD79D19
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFTrustedIssuer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFTrustedIssuer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFTrustedIssuer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSpfTrustedIssuer

## SYNOPSIS
Gets one or more trusted issuer objects.

## SYNTAX

### Empty (Default)
```
Get-SCSpfTrustedIssuer [<CommonParameters>]
```

### FromIssuerNameParameterSetName
```
Get-SCSpfTrustedIssuer -Name <String[]> [<CommonParameters>]
```

### FromIssuerIdParameterSetName
```
Get-SCSpfTrustedIssuer -ID <Guid[]> [<CommonParameters>]
```

### FromIssuerTenantParameterSetName
```
Get-SCSpfTrustedIssuer -Tenant <Tenant> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFTrustedIssuer** cmdlet gets one or more trusted issuer objects in Service Provider Foundation.
To create a trusted issuer, use the New-SCSPFTrustedIssuer cmdlet.

## EXAMPLES

### Example 1: Get all trusted issuers
```
PS C:\>Get-SCSPFTrustedIssuer
```

This command gets all trusted issuers.

### Example 2: Get a trusted issuer by ID
```
PS C:\>$TrustedIssuer = Get-SCSPFTrustedIssuer -ID c9f59be2-dce5-4221-ad60-2204dc457bd8
```

This command gets a trusted issuer by its ID.

### Example 3: Get a trusted issuer by name
```
PS C:\>$TrustedIssuer = Get-SCSPFTrustedIssuer -Name "Contoso"
```

This command gets a trusted issuer by its name.

### Example 4: Get the trusted issuer associated with a tenant
```
PS C:\>$Contoso = Get-SCSPFTenant -Name "Contoso"
PS C:\> $TrustedIssuer = Get-SCSPFTrustedIssuer -Tenant $Contoso
```

The first command gets a tenant.

The second command gets the trusted issuer associated with the tenant.

## PARAMETERS

### -ID
Specifies one or more GUIDs for a specific object.

```yaml
Type: Guid[]
Parameter Sets: FromIssuerIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of one or more trusted issuers.

```yaml
Type: String[]
Parameter Sets: FromIssuerNameParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies a tenant for which this cmdlet returns associated trusted issuers.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant
Parameter Sets: FromIssuerTenantParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-SCSPFTrustedIssuer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTrustedIssuer.md)

[Remove-SCSPFTrustedIssuer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFTrustedIssuer.md)

