---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=330327
schema: 2.0.0
ms.assetid: 9E6AAD51-2BBF-4F7C-B219-E0B4F61CB28E
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFTenantUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFTenantUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFTenantUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfTenantUserRole

## SYNOPSIS
Gets one or more tenant user roles.

## SYNTAX

### Empty (Default)
```
Get-SCSpfTenantUserRole [<CommonParameters>]
```

### FromRoleTenantParameterSetName
```
Get-SCSpfTenantUserRole [-Tenant] <Tenant> [[-Name] <String[]>] [<CommonParameters>]
```

### FromRoleIdParameterSetName
```
Get-SCSpfTenantUserRole [-ID] <Guid[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFTenantUserRole** cmdlet gets one or more tenant user roles in Service Provider Foundation.
To create a new user role for a tenant, use the New-SCSPFTenantUserRole cmdlet.

## EXAMPLES

### Example 1: Get all tenant user roles
```
PS C:\>Get-SCSPFTenantUserRole
```

This command gets all tenant user roles.

### Example 2: Get a tenant user role by ID
```
PS C:\>$TenantUserRoles = Get-SCSPFTenantUserRole -ID e6f9f901-2883-4478-a64e-00c58a423516
```

This command gets a tenant user role by its ID.

### Example 3: Get the tenant user roles associated with a tenant
```
PS C:\>$Tenant = Get-SCSPFTenant -Name "Contoso"
PS C:\> $TenantUserRoles = Get-SCSPFTenantUserRole -Tenant $Tenant
```

The first command gets a tenant.

The second command gets the tenant user roles associated with the tenant.

## PARAMETERS

### -ID
Specifies one or more GUIDs for a specific object.

```yaml
Type: Guid[]
Parameter Sets: FromRoleIdParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of one or more tenant user roles.

```yaml
Type: String[]
Parameter Sets: FromRoleTenantParameterSetName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies a tenant for which this cmdlet returns associated tenant user roles.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant
Parameter Sets: FromRoleTenantParameterSetName
Aliases: 

Required: True
Position: 0
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

[New-SCSPFTenantUserRole](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/New-SCSPFTenantUserRole.md)

[Remove-SCSPFTenantUserRole](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/Remove-SCSPFTenantUserRole.md)

