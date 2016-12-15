---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCService.md
schema: 2.0.0
ms.assetid: 5BA3AA13-3DAC-4857-8109-5051B481872D
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCService

## SYNOPSIS
Gets a VMM service.

## SYNTAX

### All (Default)
```
Get-SCService [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Name
```
Get-SCService [-VMMServer <ServerConnection>] [[-Name] <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Cloud
```
Get-SCService [-VMMServer <ServerConnection>] -Cloud <Cloud> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCService [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCService** cmdlet gets one or more services in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Get all services
```
PS C:\>Get-SCService | Format-Table -Property Name,ID
```

This command gets all services and then displays the values for their name and ID properties in a table format.

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

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: Cloud
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
Parameter Sets: Name
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

### Service
This cmdlet returns a **Service** object.

## NOTES

## RELATED LINKS

[New-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCService.md)

[Read-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCService.md)

[Remove-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCService.md)

[Resume-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCService.md)

[Set-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCService.md)

[Start-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCService.md)

[Stop-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCService.md)

[Suspend-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCService.md)

[Update-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Update-SCService.md)

