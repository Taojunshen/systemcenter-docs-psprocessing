---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 66ED0FF8-64F5-41E2-973E-DEF5467F6A80
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Import-SCSpfVMRoleGalleryItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Import-SCSpfVMRoleGalleryItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Import-SCSpfVMRoleGalleryItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Import-SCSpfVMRoleGalleryItem

## SYNOPSIS
Imports a gallery item for use by applications hosted on the Azure portal.

## SYNTAX

### FromGalleryItemPackageParameterSetName (Default)
```
Import-SCSpfVMRoleGalleryItem [-Package <Stream>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGalleryItemPackageFilePathParameterSetName
```
Import-SCSpfVMRoleGalleryItem [-PackageFilePath <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SCSpfVMRoleGalleryItem** cmdlet imports a gallery item for use by applications hosted on the portal.
The gallery item for the virtual machine role is imported into Virtual Machine Manager (VMM).
The Service Provider Foundation database manages the gallery item.

## EXAMPLES

### Example 1: Import an item
```
PS C:\> $Path = "C:\Packages\Create.resdefpkg"
PS C:\> $FStream = New-Object IO.FileStream $Path, Open
PS C:\> Import-SCSPFVMRoleGalleryItem -Package $FStream
```

The first command gets the path to the resource package and stores it in the $Path variable.

The second command gets a **System.IO.FileStream** object of the package.

The third command imports the package.

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
Specifies a **System.IO.FileStream** object that contains the resource package.

```yaml
Type: Stream
Parameter Sets: FromGalleryItemPackageParameterSetName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageFilePath
Specifies the full path, including the .resdefpkg extension, to the resource package file.

```yaml
Type: String
Parameter Sets: FromGalleryItemPackageFilePathParameterSetName
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

[Get-SCSPFVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFVMRoleGalleryItem.md)

[Remove-SCSPFVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFVMRoleGalleryItem.md)

[Set-SCSPFVMRoleGalleryItem](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFVMRoleGalleryItem.md)

