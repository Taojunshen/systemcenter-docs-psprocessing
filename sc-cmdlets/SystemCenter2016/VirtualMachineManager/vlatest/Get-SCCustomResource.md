---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Remove-SCCustomResource.md
schema: 2.0.0
ms.assetid: A9F2D1B4-33D8-4184-8210-4CABC06DF3B1
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCustomResource

## SYNOPSIS
Gets a custom resource from the VMM library.

## SYNTAX

### All (Default)
```
Get-SCCustomResource [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### NameParamSet
```
Get-SCCustomResource [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### EquivalentResourceParamSet
```
Get-SCCustomResource [-VMMServer <ServerConnection>] [-Release <String>] -FamilyName <String>
 [<CommonParameters>]
```

### ID
```
Get-SCCustomResource [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCustomResource** cmdlet gets a custom resource from the Virtual Machine Manager (VMM) library.
A custom resource is a folder-based library object in VMM.
The resource is declared at the folder level, and the contents of the folder are unknown to VMM.

To add a custom resource to the library, create a folder with a .CR extension, place content in the folder, and then use the VMM console to drag the folder to a VMM library share.
VMM discovers and imports the folder into the library as a custom resource.

## EXAMPLES

### Example 1: Get a specific custom resource
```
PS C:\>$CR = Get-SCCustomResource -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "Folder.CR" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
```

This command gets the custom resource object named Folder.CR on LibraryServer01 from the VMM library on VMMServer01 and then stores the object in the $CR variable.

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
Specifies the numerical identifier as a globally unique identifier, or GUID, for an object.

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

### CustomResource
This cmdlet returns a **CustomResource** object.

## NOTES

## RELATED LINKS

[Remove-SCCustomResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomResource.md)

[Set-SCCustomResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomResource.md)

