---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6DE6B297-A8F1-41AF-B423-25FE94C1D5C1
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFStamp.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFStamp.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFStamp.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCSpfStamp

## SYNOPSIS
Associates a stamp with offers, servers, and tenants.

## SYNTAX

```
Set-SCSpfStamp -Stamp <Stamp> [-Servers <Server[]>] [-Tenants <Tenant[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSPFStamp** cmdlet associates a stamp with one or more servers, one or more tenants, and one or more offers in Service Provider Foundation.

If you want to add an offer, server, or tenant to a stamp without changing the currently associated objects, use the Set-SCSPFServer or Set-SCSPFTenant cmdlets.

## EXAMPLES

### Example 1: Associate a stamp with a tenant
```
PS C:\>$Stamp = Get-SCSPFStamp -ID db656655-68ff-4a21-bd1d-0a06bdbc762f
PS C:\> $Tenant = Get-SCSPFTenant -Name "Contoso"
PS C:\> Set-SCSPFStamp -Stamp $Stamp -Tenants $Tenant
```

The first command gets a stamp.
The second command gets a tenant.

The third command associates the tenant with the stamp.

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

### -Servers
Specifies one or more servers to associate with the stamp.
To obtain a server, use the Get-SCSPFServer cmdlet.

```yaml
Type: Server[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stamp
Specifies the stamp object to set to new values by the other parameters in this cmdlet.
To obtain a stamp, use the Get-SCSPFStamp cmdlet.

```yaml
Type: Stamp
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenants
Specifies the name of one or more tenant objects.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant[]
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

[Get-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFStamp.md)

[New-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFStamp.md)

[Remove-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFStamp.md)

