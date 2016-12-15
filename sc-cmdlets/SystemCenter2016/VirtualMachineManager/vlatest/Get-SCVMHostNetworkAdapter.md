---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHostNetworkAdapter.md
schema: 2.0.0
ms.assetid: A2482B40-6163-41DE-8BE7-D54FD9B73F70
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMHostNetworkAdapter

## SYNOPSIS
Gets physical network adapter objects on a VMM host.

## SYNTAX

### NoFilter (Default)
```
Get-SCVMHostNetworkAdapter [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### ByID
```
Get-SCVMHostNetworkAdapter -ID <Guid> [[-Name] <String>] [<CommonParameters>]
```

### FilterByVMHost
```
Get-SCVMHostNetworkAdapter -VMHost <Host> [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHostNetworkAdapter** cmdlet gets one or more physical network adapter objects on a host managed by Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Get all physical network adapters on the specified host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> $HostAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost
PS C:\> $HostAdapter | select -property Name, ConnectionState
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets all physical network adapter objects from VMHost01 and then stores the objects in the $HostAdapter variable.

The third command displays the name and connection state for each adapter.

### Example 2: Get all physical network adapters in the VMM database
```
PS C:\>Get-SCVMHostNetworkAdapter | Format-List Name, MacAddress, VMHost, MaxBandwidth
```

This command gets all physical network adapter objects on all hosts managed by the VMM server and displays each adapter's name, its MAC address, its host name, and its maximum bandwidth.

### Example 3: Get a physical network adapter by name from a specific host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> $HostAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost -Name "HostAdapter01"
PS C:\> $HostAdapter | Format-List -property Name,VLANEnabled,VLANMode
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the network adapter object named HostAdapter01 from VMHost01 and stores the object in the $HostAdapter variable.

The third command passes the adapter object stored in $HostAdapter to the Format-List cmdlet, which displays the name, whether or not the virtual LAN is enabled, and the current value for the VLAN mode (either Trunk or Access).

### Example 4: Get each host network adapter that includes "Broadcom" in its name
```
PS C:\>Get-SCVMHostNetworkAdapter -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "Broadcom" } | Format-List -Property Name,IPAddresses
```

This command gets host network adapter objects from VMMServer01 that include the string "Broadcom" in their name.
and then displays the name and IP addresses for each adapter.

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

For more information about each type of host, see the Add-SCVMHost cmdlet.

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

### HostNetworkAdapter
The cmdlet returns a **HostNetworkAdapter** object.

## NOTES

## RELATED LINKS

[Add-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostNetworkAdapter.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Remove-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostNetworkAdapter.md)

[Set-SCVMHostNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostNetworkAdapter.md)

