---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 774FE71B-F84F-490B-9BCC-2F2D86670AFC
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfVMRoleGalleryItem

## SYNOPSIS
Gets a gallery item.

## SYNTAX

### Empty (Default)
```
Get-SCSpfVMRoleGalleryItem [<CommonParameters>]
```

### FromGalleryItemNameVersionPublisherParameterSetName
```
Get-SCSpfVMRoleGalleryItem -Name <String> -Version <String> -Publisher <String> [<CommonParameters>]
```

### FromGalleryItemNameParameterSetName
```
Get-SCSpfVMRoleGalleryItem -Name <String> [<CommonParameters>]
```

### FromGalleryItemPublisherParameterSetName
```
Get-SCSpfVMRoleGalleryItem -Publisher <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFVMRoleGalleryItem** cmdlet gets a previously imported gallery item.

## EXAMPLES

### Example 1: Get a gallery item
```
PS C:\>$GalleryItem = Get-SCSPFVMRoleGalleryItem -Name "570569955cbfb62b374358b34467020750f65c"
```

This command gets an item from the gallery by its name and stores it in the $GalleryItem variable.

## PARAMETERS

### -Name
Specifies the name of the item.

```yaml
Type: String
Parameter Sets: FromGalleryItemNameVersionPublisherParameterSetName, FromGalleryItemNameParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the item.

```yaml
Type: String
Parameter Sets: FromGalleryItemNameVersionPublisherParameterSetName, FromGalleryItemPublisherParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of the item.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Import-SCSpfVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Import-SCSpfVMRoleGalleryItem.md)

[Remove-SCSPFVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFVMRoleGalleryItem.md)

