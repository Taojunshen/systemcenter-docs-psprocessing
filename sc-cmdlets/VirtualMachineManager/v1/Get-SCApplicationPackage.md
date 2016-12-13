---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Remove-SCApplicationPackage.md
schema: 2.0.0
ms.assetid: 36CBE235-3A8E-4C34-8391-BB21D0F3CF0D
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationPackage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationPackage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationPackage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCApplicationPackage

## SYNOPSIS
Gets an application package.

## SYNTAX

### All (Default)
```
Get-SCApplicationPackage [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### NameParamSet
```
Get-SCApplicationPackage [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### EquivalentResourceParamSet
```
Get-SCApplicationPackage [-VMMServer <ServerConnection>] [-Release <String>] -FamilyName <String>
 [<CommonParameters>]
```

### ID
```
Get-SCApplicationPackage [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCApplicationPackage** cmdlet gets an application package from the Virtual Machine Manager (VMM) library.

## EXAMPLES

### Example 1: Get an application package by its name
```
PS C:\>$AppPackage = Get-SCApplicationPackage -Name "WebApp01.zip"
PS C:\> $AppPackage
```

The first command gets the application package object named WebApp01.zip from the VMM library and stores the object in the $AppPackage variable.

The second command displays information about the application package stored in $AppPackage to the user.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FamilyName
Specifies a family name for a physical resource in the VMM library.
This value is used in conjunction with Release, Namespace, and Type to establish equivalency among library resources.

```yaml
Type: String
Parameter Sets: EquivalentResourceParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
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
Parameter Sets: NameParamSet
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
After the resource has been imported, the string can be customized.

```yaml
Type: String
Parameter Sets: EquivalentResourceParamSet
Aliases: 

Required: False
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

### ApplicationPackage
This cmdlet returns an **ApplicationPackage** object.

## NOTES

## RELATED LINKS

[Remove-SCApplicationPackage](xref:VirtualMachineManager/v1/Remove-SCApplicationPackage.md)

[Set-SCApplicationPackage](xref:VirtualMachineManager/v1/Set-SCApplicationPackage.md)

