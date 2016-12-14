---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=330326
schema: 2.0.0
ms.assetid: 3B31C53D-D0EA-4D07-9C04-9E2707EFE93C
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFTenant.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFTenant.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFTenant.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfTenant

## SYNOPSIS
Gets one or more tenant objects.

## SYNTAX

### Empty (Default)
```
Get-SCSpfTenant [<CommonParameters>]
```

### FromTenantNameParameterSetName
```
Get-SCSpfTenant -Name <String[]> [<CommonParameters>]
```

### FromTenantIdParameterSetName
```
Get-SCSpfTenant -ID <Guid[]> [<CommonParameters>]
```

### FromTenantRoleParameterSetName
```
Get-SCSpfTenant -Role <Role> [<CommonParameters>]
```

### FromTenantStampParameterSetName
```
Get-SCSpfTenant -Stamp <Stamp> [<CommonParameters>]
```

### FromTenantIssuerParameterSetName
```
Get-SCSpfTenant -Issuer <Issuer> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFTenant** cmdlet gets one or more tenant objects from Service Provider Foundation.
To create a tenant, use the New-SCSPFTenant cmdlet.

## EXAMPLES

### Example 1: Get all tenants
```
PS C:\>Get-SCSPFTenant | Format-Table -Property ID, Name
```

This command displays the IDs and names of existing tenants.

### Example 2: Get a tenant by ID
```
PS C:\>$Tenant = Get-SCSPFTenant -ID e5310370-ab2d-4d51-8336-176999c9cc1e
```

This command gets a tenant by its ID.

### Example 3: Get the tenant associated with a trusted issuer
```
PS C:\>$TrustedIssuer = Get-SCSPFTrustedIssuer -Name "Contoso"
PS C:\> $Tenant = Get-SCSPFTenant -Issuer $TrustedIssuer
```

The first command gets a trusted issuer.

The second command gets the tenant associated with a trusted issuer.

### Example 4: Get a tenant by name
```
PS C:\>$ContosoTenant = Get-SCSPFTenant -Name "Contoso"
```

This command gets a tenant by its name.

### Example 5: Get the tenants associated with an offer
```
PS C:\>Get-SCSPFOffer -Name "Contoso" | Get-SCSPFTenant
```

This command gets a tenant associated with an offer.
To do this, it first gets the specified offer, and then passes the offer to the Get-SCSPFTenant cmdlet by using the pipeline operator.

### Example 6: Get the tenant associated with a tenant user role
```
PS C:\>$SupervisorRole = Get-SCSPFTenantUserRole -ID e6f9f901-2883-4478-a64e-00c58a423516
PS C:\> $Tenants = Get-SCSPFTenant -Role $SupervisorRole
```

The first command gets a tenant user role.

The second command gets the tenants associated with the tenant user role.

### Example 7: Get the tenants associated with a stamp
```
PS C:\>$ContosoStamp = Get-SCSPFStamp -Name "Contoso"
PS C:\> $Tenants = Get-SCSPFTenant -Stamp $ContosoStamp
```

The first command gets a stamp.

The second command gets the tenants associated with the stamp.

## PARAMETERS

### -ID
Specifies one or more GUIDs for a specific object.

```yaml
Type: Guid[]
Parameter Sets: FromTenantIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Issuer
Specifies an object from a trusted issuer.
To obtain a trusted issuer, use the Get-SCSPFTrustedIssuer cmdlet.

```yaml
Type: Issuer
Parameter Sets: FromTenantIssuerParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of one or more tenants.

```yaml
Type: String[]
Parameter Sets: FromTenantNameParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Role
Specifies a tenant user role for which this cmdlet returns associated tenants.
To obtain a tenant user role, use the Get-SCSPFTenantUserRole cmdlet.

```yaml
Type: Role
Parameter Sets: FromTenantRoleParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Stamp
Specifies a stamp for which this cmdlet returns associated tenants.
To obtain a stamp, use the Get-SCSPFStamp cmdlet.

```yaml
Type: Stamp
Parameter Sets: FromTenantStampParameterSetName
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

[New-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/New-SCSPFTenant.md)

[Remove-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/Remove-SCSPFTenant.md)

[Set-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/Set-SCSPFTenant.md)

