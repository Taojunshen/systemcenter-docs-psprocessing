---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BE8D5E0E-268D-41B7-B935-23F2B0EB85CC
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFTenant.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFTenant.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFTenant.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCSpfTenant

## SYNOPSIS
Sets resources and data for a tenant.

## SYNTAX

### Empty (Default)
```
Set-SCSpfTenant -Tenant <Tenant> [-Stamps <Stamp[]>] [-AccountStatus <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromTenantIssuereParameterSetName
```
Set-SCSpfTenant -Tenant <Tenant> -Key <String> -IssuerName <String> [-Stamps <Stamp[]>]
 [-AccountStatus <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSPFTenant** cmdlet associates a tenant in Service Provider Foundation with an offer, stamps, or values for claims-based authentication.

If you want to add an association of a stamp to a tenant without changing the stamps currently associated with the tenant, use the Set-SCSPFStamp cmdlet.

## EXAMPLES

### Example 1: Set the account status of a tenant
```
PS C:\>Set-SCSPFTenant -Tenant (Get-SCSPFTenant -Name "ADatum") -AccountStatus "1"
```

This command sets the account status of a tenant to 1 for suspended.

### Example 2: Associate a tenant with a collection of stamps
```
PS C:\>$Tenant = Get-SCSPFTenant -Name "Contoso"
PS C:\> $Stamps = Get-SCSPFServer | Where-Object {>> $_.Name -contains "silver">> }
PS C:\> Set-SCSPFTenant -Tenant $Tenant -Stamps $Stamps
```

The first command gets a tenant.
The second command gets a collection of stamps.

The third command associates the tenant with the stamps.

## PARAMETERS

### -AccountStatus
Specifies the status of a tenant.
Specify 0 to set the status to active or specify 1 to set the status to suspended.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -IssuerName
Specifies the name of the party that issued the certificate for the tenant.
This parameter is metadata to verify a token submitted by the tenant; do not confuse this parameter with an object from a trusted issuer.

```yaml
Type: String
Parameter Sets: FromTenantIssuereParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Key
Specifies the public key that validates a signed token submitted by a tenant in claims-based authentication.

```yaml
Type: String
Parameter Sets: FromTenantIssuereParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stamps
Specifies one or more stamps to associate with the tenant.
To obtain a stamp, use the New-SCSPFStamp cmdlet.

```yaml
Type: Stamp[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies the tenant object to set to new values by the other parameters in this cmdlet.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFTenant.md)

[New-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTenant.md)

[Remove-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFTenant.md)

