---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=328347
schema: 2.0.0
ms.assetid: 4E288FBA-2D5B-4C10-B2BD-B4E6022001DA
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFVMRoleGalleryItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFVMRoleGalleryItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFVMRoleGalleryItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSpfVMRoleGalleryItem

## SYNOPSIS
Sets the publishing status of an item in the gallery.

## SYNTAX

### FromGalleryItemParameterSetName (Default)
```
Set-SCSpfVMRoleGalleryItem -VmRoleGalleryItem <VMRoleGalleryItem> -PublishingStatus <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromGalleryItemPackageParameterSetName
```
Set-SCSpfVMRoleGalleryItem -VmRoleGalleryItem <VMRoleGalleryItem> -Package <Stream> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSPFVMRoleGalleryItem** cmdlet sets the publishing status of an item in the gallery to either publish or un-publish.

## EXAMPLES

### Example 1: Set a gallery item to publish
```
PS C:\>Set-SCSPFVmRoleGalleryItem -VmRoleGalleryItem $GalleryItem -PublishingStatus "published"
```

This command sets the publishing status of an item in the gallery to "published".

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

### -Package
Specifies an object of type System.IO.MemoryStream that contains the resource package of the gallery item.

```yaml
Type: Stream
Parameter Sets: FromGalleryItemPackageParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublishingStatus
Specifies either published or un-published.

```yaml
Type: String
Parameter Sets: FromGalleryItemParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VmRoleGalleryItem
Specifies the gallery item of which to set the publishing status.

```yaml
Type: VMRoleGalleryItem
Parameter Sets: FromGalleryItemParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: VMRoleGalleryItem
Parameter Sets: FromGalleryItemPackageParameterSetName
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

[Get-SCSPFVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItem.md)

[Import-SCSpfVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Import-SCSpfVMRoleGalleryItem.md)

