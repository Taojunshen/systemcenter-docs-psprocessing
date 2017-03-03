---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C4BB8E0C-6D4D-4777-AED6-549CE65BC6EA
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCGuestOSProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCGuestOSProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCGuestOSProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCGuestOSProfile

## SYNOPSIS
Gets a guest operating system profile object from the VMM library.

## SYNTAX

### Connection (Default)
```
Get-SCGuestOSProfile [-VMMServer <ServerConnection>] [[-Name] <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### SysprepScript
```
Get-SCGuestOSProfile -AnswerFile <Script> [-OperatingSystem <OperatingSystem>] [[-Name] <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCGuestOSProfile** cmdlet gets one or more guest operating system profile objects from the Virtual Machine Manager (VMM) library.

## EXAMPLES

### Example 1: Get all guest operating system profiles from the library
```
PS C:\> Get-SCGuestOSProfile -VMMServer "VMMServer01.Contoso.com"
```

This command gets all guest OS profile objects from the library on VMMServer01 and displays information about these profiles to the user.

### Example 2: Get a specific guest operating system profile from the library
```
PS C:\> Get-GuestOSProfile -Name "NewOSProfile01"
```

This command gets the guest OS profile object named NewOSProfile01 and displays information about this profile to the user.

## PARAMETERS

### -AnswerFile
Specifies a script object stored in the VMM library to use as an answer file.
The name of the answer file script depends on the operating system that you want to install on a virtual machine: 

- Sysprep.inf.
Windows XP, Windows Server 2000, or Windows Server 2003
- Unattend.xml.
Windows Vista, Windows 7, or Windows Server 2008

```yaml
Type: Script
Parameter Sets: SysprepScript
Aliases: SysPrepFile

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -OperatingSystem
Specifies the type of operating system for a virtual machine.
To list the names of all available operating systems in VMM, type `Get-SCOperatingSystem`.

```yaml
Type: OperatingSystem
Parameter Sets: SysprepScript
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
Parameter Sets: Connection
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

### GuestOSProfile
This cmdlet returns a **GuestOSProfile** object.

## NOTES

## RELATED LINKS

[New-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCGuestOSProfile.md)

[Remove-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCGuestOSProfile.md)

[Set-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCGuestOSProfile.md)

