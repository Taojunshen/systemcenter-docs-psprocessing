---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=330332
schema: 2.0.0
ms.assetid: 7B3FBD2B-25CF-4CD7-8BBE-0ED7E7E4E601
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/New-SCSPFTenant.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/New-SCSPFTenant.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceProviderFoundation/v1/New-SCSPFTenant.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSpfTenant

## SYNOPSIS
Creates a new tenant for a hoster.

## SYNTAX

### Empty (Default)
```
New-SCSpfTenant -Name <String> [-Stamps <Stamp[]>] [-SubscriptionId <Guid>] [-AccountStatus <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromTenantIssuereParameterSetName
```
New-SCSpfTenant -Name <String> -Key <String> -IssuerName <String> [-Stamps <Stamp[]>] [-SubscriptionId <Guid>]
 [-AccountStatus <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromTenantCertParameterSetName
```
New-SCSpfTenant -Name <String> -Certificate <String> -IssuerName <String> [-Stamps <Stamp[]>]
 [-SubscriptionId <Guid>] [-AccountStatus <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSPFTenant** cmdlet creates a new tenant in Service Provider Foundation.
If you are a service provider, the tenants are your paying customers.
If you are using Service Provider Foundation in a private cloud, the tenants are the business units in your organization.

## EXAMPLES

### Example 1: Create a new tenant
```
PS C:\>$Path = "C:\Temp\ADatum29D.cer"
PS C:\> $Certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2($Path)
PS C:\> $Key = [Convert]::ToBase64String($Certificate.RawData)
PS C:\> $SubscriptionId = [System.Guid]::NewGuid().ToString()
PS C:\> New-SCSPFTenant -IssuerName "Contoso" -Key $Key -Name "ADatum" -SubscriptionID $SubscriptionId
```

The first two commands create the $Certificate variable to contain the issued certificate for the tenant.

The third command creates the $Key variable to contain the public key for the certificate.

The fourth command creates the $SubscriptionId variable to contain the GUID for the subscription.

The fifth command creates the tenant with the name of the trusted issuer of the certificate, the public key, a specified name, and the GUID associated with the subscription.

## PARAMETERS

### -AccountStatus
Specifies the status of a tenant.
Specify 0 for Active, or 1 for Suspended.

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

### -Certificate
Specifies the path to the certificate file for the tenant.

```yaml
Type: String
Parameter Sets: FromTenantCertParameterSetName
Aliases: 

Required: True
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
This parameter is metadata to verify a token submitted by the tenant; do not confuse this parameter with a trusted issuer object.

```yaml
Type: String
Parameter Sets: FromTenantIssuereParameterSetName, FromTenantCertParameterSetName
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

### -Name
Specifies the name to give to the tenant.

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

### -Stamps
Specifies the name of one or more stamp objects to associate with the new tenant.
To obtain a stamp, use the Get-SCSPFStamp cmdlet.

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

### -SubscriptionId
Specifies the GUID for a subscription of a tenant.
This value cannot be changed after the tenant is created.

```yaml
Type: Guid
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

[Get-SCSPFTenant](xref:ServiceProviderFoundation/v1/Get-SCSPFTenant.md)

[Remove-SCSPFTenant](xref:ServiceProviderFoundation/v1/Remove-SCSPFTenant.md)

[Set-SCSPFTenant](xref:ServiceProviderFoundation/v1/Set-SCSPFTenant.md)

