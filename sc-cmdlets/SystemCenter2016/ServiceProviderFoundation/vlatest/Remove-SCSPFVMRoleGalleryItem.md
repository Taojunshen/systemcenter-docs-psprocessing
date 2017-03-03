---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 78389B33-43F1-42CD-91C2-39C50F371135
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFVMRoleGalleryItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFVMRoleGalleryItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFVMRoleGalleryItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCSpfVMRoleGalleryItem

## SYNOPSIS
Removes an item from the gallery.

## SYNTAX

### FromGalleryItemParameterSetName (Default)
```
Remove-SCSpfVMRoleGalleryItem [-VMRoleGalleryItem] <VMRoleGalleryItem[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromGalleryItemNameVersionPublisherParameterSetName
```
Remove-SCSpfVMRoleGalleryItem -Name <String> -Version <String> -Publisher <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSPFVMRoleGalleryItem** cmdlet removes a gallery item from the vmm12sp1_long or the Service Provider Foundation database.

## EXAMPLES

### Example 1: Remove a gallery item
```
PS C:\>$Item = Get-SCSPFVMRoleGalleryItem -Name "570569955cbfb62b374358b34467
020750f65c"
PS C:\> Remove-SCSPFVmRoleGalleryItem -VMRoleGalleryItem $Item
```

The first command gets an item by name and stores it in the $Item variable.
The next command removes the item.

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
Specifies the publisher of the gallery item to remove.

```yaml
Type: String
Parameter Sets: FromGalleryItemNameVersionPublisherParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the item to remove.

```yaml
Type: String
Parameter Sets: FromGalleryItemNameVersionPublisherParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMRoleGalleryItem
Specifies one or more gallery items to remove.

```yaml
Type: VMRoleGalleryItem[]
Parameter Sets: FromGalleryItemParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Version
Specifies the version of the item to remove.

```yaml
Type: String
Parameter Sets: FromGalleryItemNameVersionPublisherParameterSetName
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

[Get-SCSPFVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItem.md)

[Import-SCSpfVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Import-SCSpfVMRoleGalleryItem.md)

[Set-SCSPFVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFVMRoleGalleryItem.md)

