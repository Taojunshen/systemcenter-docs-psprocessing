---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C4270710-207F-4D09-A2EE-4EFBFC10851B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMwareResourcePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMwareResourcePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMwareResourcePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVMwareResourcePool

## SYNOPSIS
Gets VMware resource pool objects from the VMM database.

## SYNTAX

### NoFilter (Default)
```
Get-SCVMwareResourcePool [<CommonParameters>]
```

### FilterByVMHost
```
Get-SCVMwareResourcePool -VMHost <Host> [<CommonParameters>]
```

### FilterByVMHostCluster
```
Get-SCVMwareResourcePool -VMHostCluster <HostCluster> [<CommonParameters>]
```

### FilterById
```
Get-SCVMwareResourcePool -ID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMWareResourcePool** cmdlet gets VMware resource pool objects from the Virtual Machine Manager (VMM) database.

VMware resource pools are imported when a ESX host or ESX host cluster that owns the resource pools are added to VMM.

VMware uses resource pools to group virtual machines deployed on ESX hosts, or ESX host clusters, into an organizational hierarchy that consists of parent, sibling, and child resource pools.
Resources, such as CPU and memory, are specified for virtual machines assigned to each resource pool.
Administration of sets of resource pools can be delegated, in vCenter Server, to administrators by department, by geographical region, or by some other organizational requirement.

VMware resource pools can provide resources to private clouds.
For more information about creating a private cloud, type `Get-Help New-SCCloud`.

## EXAMPLES

### Example 1: Get the VMware resource pool for a VMware ESX host
```
PS C:\> $ESXHost = Get-SCVMHost -ComputerName "ESXHost01.Contoso.com"
PS C:\> Get-SCVMwareResourcePool -VMHost $ESXHost
```

The first command gets the object that represents the VMware ESX host named ESXHost01.Contoso.com from the VMM database.
This ESX Server is managed by VMM through VMware VirtualCenter Server.
The command stores the host object in the variable $ESXHost.

The last command gets the VMware resource pool information from the VMM database for the ESX host object stored in variable $VMHost and displays information about the resource pool.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: FilterById
Aliases: 

Required: True
Position: Named
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

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: FilterByVMHostCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMwareResourcePool
This cmdlet returns a **VMwareResourcePool** object.

## NOTES

## RELATED LINKS

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

