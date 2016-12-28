---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 60A239D8-69D3-405B-B2D9-CFDCE3D92C98
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTenantUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTenantUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFTenantUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSpfTenantUserRole

## SYNOPSIS
Creates an association between a tenant and one or more self-service user roles.

## SYNTAX

```
New-SCSpfTenantUserRole -Tenant <Tenant> -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSPFTenantUserRole** cmdlet creates an association between a tenant and one or more self-service user roles in Service Provider Foundation.
The self-service roles must already have been created in Virtual Machine Manager (VMM), or by using the New-SCUserRole cmdlet in the "virtualmachinemanager" Windows PowerShell module.

You cannot use this cmdlet to create an association with a tenant administrator user role.
The New-SCSPFTenant cmdlet automatically creates the tenant administrator user role when it creates the tenant.

## EXAMPLES

### Example 1: Create a tenant user role
```
PS C:\>$Roles = "Assistant", "Admin", "Developer"
PS C:\> $Tenant = Get-SCSPFTenant -Name "Contoso"
PS C:\> New-SCSPFTenantUserRole -Name $Roles -Tenant $Tenant
```

The first command defines an array of self-service user roles.

The second command gets a tenant.

The third command creates the user role for the tenant with its individual self-service user roles.

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

### -Name
Specifies the name of one or more tenant user roles.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies a tenant object to associate with the new tenant user role.
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

[Get-SCSPFTenantUserRole](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFTenantUserRole.md)

[Remove-SCSPFTenantUserRole](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFTenantUserRole.md)

