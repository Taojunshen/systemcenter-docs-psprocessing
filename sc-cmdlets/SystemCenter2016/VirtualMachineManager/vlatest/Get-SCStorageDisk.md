---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E4F18A94-998D-4374-8789-2EEAE7D39E83
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageDisk

## SYNOPSIS
Gets a storage disk object for the specified host from the VMM database.

## SYNTAX

### NoFilter (Default)
```
Get-SCStorageDisk [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### FilterByVMHost
```
Get-SCStorageDisk -VMHost <Host> [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageDisk** cmdlet gets storage disk objects for a host from the Virtual Machine Manager (VMM) database.
You can use this cmdlet with the **New-SCVirtualDiskDrive** cmdlet to attach a pass-through disk on a virtual machine to a physical hard disk on the host on which that virtual machine is deployed.

## EXAMPLES

### Example 1: Get all hard disk drives on a host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> Get-SCStorageDisk -VMHost $VMHost
```

The first command gets the host object named VMHost01 by using the **Get-SCVMHost** cmdlet.
The command stores that object in the $VMHost variable.

The second command gets all hard disk drive objects from the host stored in $VMHost.

### Example 2: Get a specific hard disk drive on the host by name
```
PS C:\> $StorageDisk = Get-SCVMHost -ComputerName "VMHost02.Contoso.com" | Get-SCStorageDisk -Name "\\.\PhysicalDrive0"
PS C:\> $StorageDisk
```

The first command gets the host object named VMHost02, and uses the pipeline operator to pass VMHost02 to the current cmdlet.
That cmdlet gets the hard disk drive object named PhysicalDrive0 for the host.
The command then stores the hard disk drive object in the $StorageDisk variable.

The second command displays the contents of $StorageDisk.

## PARAMETERS

### -Name
Specifies the name of a storage disk that this cmdlet gets.

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

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.
For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: FilterByVMHost
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
Parameter Sets: NoFilter
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

### StorageDisk
This cmdlet returns a **StorageDisk** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Mount-SCStorageDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Mount-SCStorageDisk.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDiskDrive.md)

[Set-SCStorageDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageDisk.md)

