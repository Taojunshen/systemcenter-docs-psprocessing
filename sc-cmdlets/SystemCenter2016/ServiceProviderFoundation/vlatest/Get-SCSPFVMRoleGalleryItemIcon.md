---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C466F55D-276E-4057-9D83-73C720A76B31
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItemIcon.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItemIcon.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItemIcon.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSpfVMRoleGalleryItemIcon

## SYNOPSIS
Gets the icon associated with a gallery item.

## SYNTAX

### FromGalleryItemParameterSetName (Default)
```
Get-SCSpfVMRoleGalleryItemIcon [-VMRoleGalleryItem] <VMRoleGalleryItem> -IconFileName <String>
 [<CommonParameters>]
```

### FromGalleryItemNameVersionPublisherParameterSetName
```
Get-SCSpfVMRoleGalleryItemIcon -Name <String> -Version <String> -Publisher <String> -IconFileName <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFVMRoleGalleryItemIcon** cmdlet gets a **System.IO.MemoryStream** object for the icon that is associated with a gallery item used by a virtual machine role.

## EXAMPLES

### Example 1: Get the icon associated with a gallery item
```
PS C:\>$GalleryItem = Get-SCSPFVMRoleGalleryItem -Name 570569955cbfb62b374358b34467020750f65c
PS C:\> $GalleryItemIcon = Get-SCSPFVMRoleGalleryItemIcon -Name $GalleryItem.Name -Publisher $GalleryItem.Publisher -Version $GalleryItem.Version -IconFilename "Contoso.ico"
```

The first command gets a gallery item and stores it in $GalleryItem.

The second command gets the icon object by specifying the required parameters with the variable.
Specify the *IconFileName* parameter explicitly in case the variable has a null value for the icon file name.

## PARAMETERS

### -IconFileName
Specifies the file name of the icon.

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

### -Name
Specifies the name of the item.

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
Specifies the publisher of the item.

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
Specifies the gallery item associated with the icon.

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

