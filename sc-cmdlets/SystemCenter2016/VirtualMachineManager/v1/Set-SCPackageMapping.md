---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCTemplatePackage.md
schema: 2.0.0
ms.assetid: CCEFAF04-0600-46A4-8A63-FF75F2E3C88A
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCPackageMapping.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCPackageMapping.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCPackageMapping.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCPackageMapping

## SYNOPSIS
Updates a package mapping object.

## SYNTAX

### LocalFile
```
Set-SCPackageMapping -PackageMapping <PackageMapping> -LocalFile <String> [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

### PackageFile
```
Set-SCPackageMapping -PackageMapping <PackageMapping> [-UsePackageFileMapping] [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

### TargetObject
```
Set-SCPackageMapping -PackageMapping <PackageMapping> [-TargetObject <ClientObject>]
 [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCPackageMapping** cmdlet updates a package mapping object.
To create a package mapping object, see New-SCPackageMapping.

## EXAMPLES

### Example 1: Update a package mapping object
```
PS C:\>$TemplatePackage = Get-SCTemplatePackage -Path "C:\TemplateExports\ServiceTemplate01.new.xml"
PS C:\> $Mappings = New-SCPackageMapping -TemplatePackage $TemplatePackage
PS C:\> $Mapping = $Mappings | where {$_.PackageID -eq "VHD01.vhd"}
PS C:\> $Resource = Get-SCVirtualHardDisk -Name "VHD01.vhd"
PS C:\> Set-SCPackageMapping -PackageMapping $Mapping -TargetObject $Resource
```

The first command gets the template package at the specified path.

The second command creates a package mapping object for the package stored in $TemplatePackage and stores the object in the $Mappings variable.

The third command gets a mapping object by package ID and stores the object in the $Mapping variable.

The fourth command gets the virtual hard disk object named VHD01 and stores the object in the $Resource variable.

The last command binds the mapping stored in $Mapping to the object stored in $Resource (VHD01).

## PARAMETERS

### -LocalFile
Specifies the location of an exported package.

```yaml
Type: String
Parameter Sets: LocalFile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageMapping
Specifies a package mapping object.

```yaml
Type: PackageMapping
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetObject
Specifies the object to which you want to map a resource.

```yaml
Type: ClientObject
Parameter Sets: TargetObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsePackageFileMapping
Indicates that the package file is uploaded.

```yaml
Type: SwitchParameter
Parameter Sets: PackageFile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCTemplatePackage](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCTemplatePackage.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualHardDisk.md)

[New-SCPackageMapping](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCPackageMapping.md)

