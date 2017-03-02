---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 364F8A66-19B0-4C34-B753-74590A4AD7CA
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPhysicalComputerProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPhysicalComputerProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPhysicalComputerProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCPhysicalComputerProfile

## SYNOPSIS
Gets a physical computer profile object.

## SYNTAX

### All (Default)
```
Get-SCPhysicalComputerProfile [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### NameParameter
```
Get-SCPhysicalComputerProfile [[-Name] <String>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ID
```
Get-SCPhysicalComputerProfile [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPhysicalComputerProfile** cmdlet gets a physical computer profile object.

## EXAMPLES

### Example 1: Get a physical computer profile by ID
```
PS C:\> $PhysicalComputerProfile = Get-SCPhysicalComputerProfile -ID "d1ce0773-4f50-4f12-a244-38a5a35c5326"
```

This command gets the physical computer profile that has the specified ID, and then stores it in the $PhysicalComputerProfile variable.

### Example 2: Get a physical computer profile by name
```
PS C:\> $PCP = Get-SCPhysicalComputerProfile -Name "Windows Server 2012 R2"
```

This command gets the physical computer profile named Windows Server 2012 R2, and then stores it in the $PCP variable.

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

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: NameParameter
Aliases: 

Required: False
Position: 0
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

### PhysicalComputerProfile
This cmdlet returns a **PhysicalComputerProfile** object.

## NOTES

## RELATED LINKS

[New-SCPhysicalComputerProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerProfile.md)

[Remove-SCPhysicalComputerProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPhysicalComputerProfile.md)

[Set-SCPhysicalComputerProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPhysicalComputerProfile.md)

