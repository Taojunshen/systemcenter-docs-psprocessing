---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: ./Get-SCSPFTenant.md
schema: 2.0.0
ms.assetid: C9FD008F-159F-41F0-890A-FB2AC6C6D844
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Remove-SCSPFTenant.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Remove-SCSPFTenant.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Remove-SCSPFTenant.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSpfTenant

## SYNOPSIS
Removes one or more tenant objects.

## SYNTAX

```
Remove-SCSpfTenant -Tenant <Tenant[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSPFTenant** cmdlet removes one or more tenant objects from the Service Provider Foundation database.

## EXAMPLES

### Example 1: Remove a tenant object
```
PS C:\>$Tenant = Get-SCSPFTenant -Name "Contoso"
PS C:\> Remove-SCSPFTenant -Tenant $Tenant
```

The first command gets the tenant object named Contoso and stores the object in the $Tenant variable.

The second command removes the tenant.

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

### -Tenant
Specifies the name of one or more tenant objects.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant[]
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

[Get-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFTenant.md)

[New-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/New-SCSPFTenant.md)

[Set-SCSPFTenant](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/Set-SCSPFTenant.md)

