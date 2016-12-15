---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCVMHostFibreChannelVirtualSAN.md
schema: 2.0.0
ms.assetid: D2FC4E93-FDB8-42A2-BBE5-48C24B82AF70
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostFibreChannelVirtualSAN.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostFibreChannelVirtualSAN.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostFibreChannelVirtualSAN.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMHostFibreChannelVirtualSAN

## SYNOPSIS
Gets a virtual Fibre Channel SAN object.

## SYNTAX

### All (Default)
```
Get-SCVMHostFibreChannelVirtualSAN [-VMMServer <ServerConnection>] [[-Name] <String>] [-All]
 [<CommonParameters>]
```

### ID
```
Get-SCVMHostFibreChannelVirtualSAN [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHostFibreChannelVirtualSAN** cmdlet gets a virtual Fibre Channel storage area network (SAN) object.

## EXAMPLES

### 1:
```

```

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
Parameter Sets: (All)
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

### VMHostFibreChannelVirtualSAN
This cmdlet returns a **VMHostFibreChannelVirtualSAN** object.

## NOTES

## RELATED LINKS

[New-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHostFibreChannelVirtualSAN.md)

[Remove-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostFibreChannelVirtualSAN.md)

[Set-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostFibreChannelVirtualSAN.md)
