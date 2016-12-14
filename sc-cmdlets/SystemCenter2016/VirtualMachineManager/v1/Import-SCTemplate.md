---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Export-SCTemplate.md
schema: 2.0.0
ms.assetid: 3A9DCB5D-911F-465A-82BE-08597BE2703E
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Import-SCTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Import-SCTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Import-SCTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Import-SCTemplate

## SYNOPSIS
Imports a virtual machine template or service template into the VMM library.

## SYNTAX

### Path
```
Import-SCTemplate -Path <String> [-Name <String>] [-Release <String>] [-Overwrite] [-SettingsIncludePrivate]
 [-PackageMapping <PackageMapping[]>] [-AllowUnencryptedTransfer] [-SharePath <String>] [-Password <String>]
 [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### Package
```
Import-SCTemplate -TemplatePackage <Package> [-Name <String>] [-Release <String>] [-Overwrite]
 [-SettingsIncludePrivate] [-PackageMapping <PackageMapping[]>] [-AllowUnencryptedTransfer]
 [-SharePath <String>] [-Password <String>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SCTemplate** cmdlet imports a virtual machine template or service template into the Virtual Machine Manager (VMM) library.
To export a template from the library, use Export-SCTemplate.

## EXAMPLES

### Example 1: Import a previously exported template package
```
PS C:\>$Package = Get-SCTemplatePackage -Path "C:\TemplateExports\ServiceTemplate01.new.xml"
PS C:\> Import-SCTemplate -TemplatePackage $Package -SettingsIncludePrivate
```

The first command gets the exported template package object at the specified path and stores the object in the $Package variable.

The second command imports the template package object stored in $Package, including all template settings.

### Example 2: Import an export package and specify a new name and release for the imported template
```
PS C:\>Import-SCTemplate -Path "C:\TemplateExports\ServiceTemplate01.new.xml" -SettingsIncludePrivate -Name "New Service Name" -Release "1.0"
```

This command imports the specified template export package with all of the template's settings and specifies a new name and release for the imported template.

### Example 3: Import a template that has some/all resources in the exported package while changing mapping
```
PS C:\>$Mappings = New-SCPackageMapping -Path "C:\TemplateExports\VMTemplate01.xml" -PreferPackageResources
PS C:\> $Mapping = $Mappings | where {$_.PackageID -eq "VHD01.vhd"}
PS C:\> $Resource = Get-SCVirtualHardDisk -Name "VHD01.vhd"
PS C:\> Set-SCPackageMapping -PackageMapping $Mapping -TargetObject $Resource
PS C:\> Set-SCPackageMapping -PackageMapping $Mapping -PackageFile "C:\TemplateExports\Resources\VHD01.vhd"
PS C:\> Import-SCTemplate -Path C:\TemplateExports\VMTemplate01.xml -PackageMapping $Mapping -SharePath "\\LibServer01\Share01"
```

The first command creates a package mapping object for the package stored at the specified path and then stores the package mapping object in the $Mappings variable.

The second command gets a mapping object by package ID and stores the object in the $Mapping variable.

The third command gets the virtual hard disk object named VHD01 and stores the object in the $Resource variable.

The fourth command binds the mapping stored in $Mapping to the object stored in $Resource (VHD01).

The fifth command sets the package file for the mapping stored in $Mapping.

The last command imports the template at the specified path with the specified mappings (in this case, VHD01 imports to Share01).

## PARAMETERS

### -AllowUnencryptedTransfer
Indicates that network file transfers do not require encryption.
If you allow unencrypted network file transfers, it can improve performance if neither the source host nor the destination host requires encryption.

Use this parameter to: 

- Allow unencrypted file transfers into, or out of, the library. 
- Allow unencrypted file transfers into, out of, or within a host group.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Overwrite
Indicates that an import or export operation overwrites an existing file with the same name.
Or, that an import operation overwrites an existing virtual machine template or service template object with the same name.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageMapping
Specifies an array of package mapping objects.

```yaml
Type: PackageMapping[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies a secure string that contains a password.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the destination path for the operation. 



Example formats: 


Local path:       `-Path "F:\"`

UNC path:         `-Path "\\\\Library\Templates"`

Volume GUID path: `-Path "\\\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`

VMware ESX path:  `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`

Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Release
Specifies a string that describes the release of a library resource.
VMM automatically creates a release value for every resource imported into the library.
After the resource has been imported, you can customize the string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsIncludePrivate
Indicates that sensitive template settings are included in an import or export operation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePath
Specifies a path to a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path.

Example format: `-SharePath "\\\\LibServer01\LibShare"`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemplatePackage
Specifies an exported template package that contains serialized settings of a service or virtual machine template.

```yaml
Type: Package
Parameter Sets: Package
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### SCTemplate
This cmdlet returns a **SCTemplate** object.

## NOTES

## RELATED LINKS

[Export-SCTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Export-SCTemplate.md)

[Get-SCTemplatePackage](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCTemplatePackage.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualHardDisk.md)

[New-SCPackageMapping](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCPackageMapping.md)

