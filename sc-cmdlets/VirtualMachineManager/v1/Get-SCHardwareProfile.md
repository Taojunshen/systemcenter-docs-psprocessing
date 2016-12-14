---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCHardwareProfile.md
schema: 2.0.0
ms.assetid: 38C265F6-FFCF-4BBB-A25D-E49307F1F92E
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCHardwareProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCHardwareProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCHardwareProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCHardwareProfile

## SYNOPSIS
Gets hardware profile objects from the VMM library.

## SYNTAX

### Connection (Default)
```
Get-SCHardwareProfile [-VMMServer <ServerConnection>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### All
```
Get-SCHardwareProfile [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCHardwareProfile [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCHardwareProfile** cmdlet gets one or more hardware profile objects from the Virtual Machine Manager (VMM) library.
You can use a hardware profile repeatedly to create new virtual machines or virtual machine templates.

## EXAMPLES

### Example 1: Get all hardware profiles from the library
```
PS C:\> Get-SCHardwareProfile -VMMServer "VMMServer01.Contoso.com"
```

This command gets all hardware profile objects from the library on VMMServer01 and displays information about these profiles to the user.

### Example 2: Get a specific hardware profile from the library
```
C:\> Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
```

This command gets the hardware profile object named NewHWProfile01 and displays information about this hardware profile to the user.

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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the Get-SCUserRole cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
Parameter Sets: (All)
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

### HardwareProfile
This cmdlet returns a **HardwareProfile** object.

## NOTES

## RELATED LINKS

[New-SCHardwareProfile](xref:VirtualMachineManager/v1/New-SCHardwareProfile.md)

[Remove-SCHardwareProfile](xref:VirtualMachineManager/v1/Remove-SCHardwareProfile.md)

[Set-SCHardwareProfile](xref:VirtualMachineManager/v1/Set-SCHardwareProfile.md)
