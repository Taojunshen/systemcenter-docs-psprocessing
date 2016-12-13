---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=330336
schema: 2.0.0
ms.assetid: F214AF39-5A90-4A48-A89F-D5F0EEC148E7
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/Remove-SCSPFTenantUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/Remove-SCSPFTenantUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceProviderFoundation/v1/Remove-SCSPFTenantUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSpfTenantUserRole

## SYNOPSIS
Removes one or more tenant user roles.

## SYNTAX

```
Remove-SCSpfTenantUserRole -UserRole <Role[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSPFTenantUserRole** cmdlet removes one or more tenant user roles from the Service Provider Foundation database.

## EXAMPLES

### Example 1: Remove a tenant user role
```
PS C:\>$TenantUserRole = Get-SCSPFTenantUserRole -ID 9adb708d-f47e-4dda-9e56-91e1eb2808df
PS C:\> Remove-SCSPFTenantUserRole -UserRole $TenantUserRole
```

The first command gets the tenant user role by its ID and stores the object in the $TenantUserRole variable.

The second command removes the tenant user role.

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

### -UserRole
Specifies the name of one or more tenant user roles.
To obtain a tenant user role, use the Get-SCSPFTenantUserRole cmdlet.

```yaml
Type: Role[]
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

[Get-SCSPFTenantUserRole](xref:ServiceProviderFoundation/v1/Get-SCSPFTenantUserRole.md)

[New-SCSPFTenantUserRole](xref:ServiceProviderFoundation/v1/New-SCSPFTenantUserRole.md)

