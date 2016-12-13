---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Remove-SCSSHKey.md
schema: 2.0.0
ms.assetid: 40EA8A82-7BE5-4487-BBD6-CB036EE626E7
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCSSHKey.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCSSHKey.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCSSHKey.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSSHKey

## SYNOPSIS
Gets Linux Administrator SSHKey objects from the VMM library.

## SYNTAX

### All (Default)
```
Get-SCSSHKey [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### NameParamSet
```
Get-SCSSHKey [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### EquivalentResourceParamSet
```
Get-SCSSHKey [-VMMServer <ServerConnection>] [-Release <String>] -FamilyName <String> [<CommonParameters>]
```

### ID
```
Get-SCSSHKey [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSSHKey** cmdlet gets Linux Administrator **SSHKey** objects from the Virtual Machine Manager (VMM) library.

## EXAMPLES

### Example 1: Get all SSHKey objects in the VMM library
```
PS C:\>$SSHKey = Get-SCSSHKey -All
```

This command gets all **SSHKey** objects in the VMM library and displays information about each to the user.

### Example 2: Get an SSHKey by its name
```
PS C:\>$SSHKey = Get-SCSSHKey -Name "My.sshkey"
PS C:\> $SSHKey
```

The first command gets the **SSHKey** object named My.sshkey, and then stores that object in the $SSHKey variable.

The second command displays information about the **SSHKey** object stored in $SSHKey.

### Example 3: Get all SSHKey objects that share a property
```
PS C:\>Get-SCSSHKey -FamilyName "Family01"
```

This command gets all **SSHKey** objects from the VMM library with the *FamilyName* value of Family01, and displays information about each **SSHKey**.

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
Specifies the unique ID of an **SSHKey** that this cmdlet gets.

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
Specifies the name of an **SSHKey** object that this cmdlet gets.

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

### LinuxAdministratorSshKey
This cmdlet returns a **LinuxAdministratorSshKey** object.

## NOTES

## RELATED LINKS

[Remove-SCSSHKey](xref:VirtualMachineManager/v1/Remove-SCSSHKey.md)

[Set-SCSSHKey](xref:VirtualMachineManager/v1/Set-SCSSHKey.md)

