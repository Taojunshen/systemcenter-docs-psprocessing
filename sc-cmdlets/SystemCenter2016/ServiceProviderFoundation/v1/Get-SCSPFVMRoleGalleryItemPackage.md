---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=328316
schema: 2.0.0
ms.assetid: 9EA6B14D-D3BA-40C8-A882-02B00BD54918
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Get-SCSPFVMRoleGalleryItemPackage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Get-SCSPFVMRoleGalleryItemPackage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1/Get-SCSPFVMRoleGalleryItemPackage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfVMRoleGalleryItemPackage

## SYNOPSIS
Gets the package that created an item in the gallery.

## SYNTAX

### FromGalleryItemParameterSetName (Default)
```
Get-SCSpfVMRoleGalleryItemPackage [-VMRoleGalleryItem] <VMRoleGalleryItem> [<CommonParameters>]
```

### FromGalleryItemNameVersionPublisherParameterSetName
```
Get-SCSpfVMRoleGalleryItemPackage -Name <String> -Version <String> -Publisher <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFVMRoleGalleryItemPackage** cmdlet gets an object of type **System.IO.MemoryStream** that contains the resource package for the gallery item of the virtual machine role.

## EXAMPLES

### Example 1: Get the package by name, publisher, and version
```
PS C:\>$GalleryPackage = Get-SCSPFVMRoleGalleryItemPackage -Name "570569955cbfb62b374358b34467020750f65c" -Publisher Microsoft -Version 1.0.0.0
```

This command gets the package for the gallery item by specifying the name, publisher, and version.

### Example 2: Get the package from a gallery item
```
PS C:\>$GalleryItem = Get-SCSPFVMRoleGalleryItem -Name "570569955cbfb62b374358b34467020750f65c"
PS C:\> $GalleryPackage = Get-SCSPFVMRoleGalleryItemPackage -VMRoleGalleryItem $GalleryItem
```

The first command gets a gallery item by its name and stores the gallery item in the $GalleryItem variable.
The next command gets the package by using the *VMRoleGalleryItem* parameter.

## PARAMETERS

### -Name
Specifies the name of the package that installs the gallery item.

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
Specifies the publisher of the gallery package.

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
Specifies an object for the gallery item.

```yaml
Type: VMRoleGalleryItem
Parameter Sets: FromGalleryItemParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Version
Specifies the version of the gallery item.

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

