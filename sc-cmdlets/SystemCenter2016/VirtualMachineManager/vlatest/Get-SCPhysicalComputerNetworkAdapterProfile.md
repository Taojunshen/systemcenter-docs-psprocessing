---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C5B7BCD6-F944-45A0-87E2-D770A17B589F
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPhysicalComputerNetworkAdapterProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPhysicalComputerNetworkAdapterProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPhysicalComputerNetworkAdapterProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCPhysicalComputerNetworkAdapterProfile

## SYNOPSIS
Gets a physical computer network adapter object.

## SYNTAX

### All
```
Get-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCPhysicalComputerNetworkAdapterProfile [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPhysicalComputerNetworkAdapterProfile** cmdlet gets a physical computer network adapter object.

## EXAMPLES


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

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### PhysicalComputerNetworkAdapterProfile
This cmdlet returns a **PhysicalComputerNetworkAdapterProfile** object.

## NOTES

## RELATED LINKS

[New-SCPhysicalComputerNetworkAdapterProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCPhysicalComputerNetworkAdapterProfile.md)

[Remove-SCPhysicalComputerNetworkAdapterProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPhysicalComputerNetworkAdapterProfile.md)

