---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AC331158-7AA0-473A-8896-1A6C8B2EEDBB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVirtualNetwork

## SYNOPSIS
Gets virtual network objects configured on a VMM host.

## SYNTAX

### NoFilter (Default)
```
Get-SCVirtualNetwork [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### Cluster
```
Get-SCVirtualNetwork -VMHostCluster <HostCluster> [[-Name] <String>] [<CommonParameters>]
```

### ByID
```
Get-SCVirtualNetwork -ID <Guid> [[-Name] <String>] [<CommonParameters>]
```

### FilterByVMHost
```
Get-SCVirtualNetwork -VMHost <Host> [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualNetwork** cmdlet gets one or more virtual network objects configured on a host managed by Virtual Machine Manager (VMM).

For information about virtual networks in VMM, type `Get-Help New-SCVirtualNetwork -Detailed`.

## EXAMPLES

### Example 1: Get all virtual networks in the VMM database
```
PS C:\> $VirtualNetworks = Get-SCVirtualNetwork 
PS C:\> $VirtualNetworks | Format-List Name,VMHost,VMHostNetworkadapters
```

The first command gets all virtual network objects on all hosts managed by VMM and stores the virtual network objects in $VirtualNetworks.

The second command displays a subset of information about each virtual network object in $VirtualNetworks: the name of each virtual network, the physical host on which each virtual network is configured, and the physical network adapters configured on the host for each virtual network.

### Example 2: Get all virtual networks on a specific host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> Get-SCVirtualNetwork -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets all virtual network objects on VMHost01 and displays information about each virtual network.

### Example 3: Get a virtual network by name from a specific host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com" 
PS C:\> $VN = Get-SCVirtualNetwork -VMHost $VMHost -Name "InternalVNet01"
PS C:\> $VN
```

The first command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The second command gets the virtual network object named InternalVNet01 from VMHost02 and stores the object in the $VN variable.

The last command displays information about the virtual network stored in $VN to the user.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ByID
Aliases: 

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
Parameter Sets: Cluster
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

### VirtualNetwork
This cmdlet returns a **VirtualNetwork** object.

## NOTES

## RELATED LINKS

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[New-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetwork.md)

[Remove-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetwork.md)

[Repair-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetwork.md)

[Set-SCVirtualNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetwork.md)

