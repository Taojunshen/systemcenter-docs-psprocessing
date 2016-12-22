---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DF9C47B8-5D06-4A6B-8C3F-BF32AE0633F2
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPerformanceData.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPerformanceData.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPerformanceData.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCPerformanceData

## SYNOPSIS
Gets performance data for host groups, clusters, hosts, and virtual machines.

## SYNTAX

### VM
```
Get-SCPerformanceData [-VM] <VM> [-VMMServer <ServerConnection>] -TimeFrame <String>
 -PerformanceCounter <String> [<CommonParameters>]
```

### Host
```
Get-SCPerformanceData [-VMHost] <Host> [-VMMServer <ServerConnection>] -TimeFrame <String>
 -PerformanceCounter <String> [<CommonParameters>]
```

### Cluster
```
Get-SCPerformanceData [-VMHostCluster] <HostCluster> [-VMMServer <ServerConnection>] -TimeFrame <String>
 -PerformanceCounter <String> [<CommonParameters>]
```

### HostGroup
```
Get-SCPerformanceData [-VMHostGroup] <HostGroup> [-VMMServer <ServerConnection>] -TimeFrame <String>
 -PerformanceCounter <String> [<CommonParameters>]
```

### AllVM
```
Get-SCPerformanceData [-VMMServer <ServerConnection>] -PerformanceCounter <String> [-AllVM]
 [<CommonParameters>]
```

### AllVNIC
```
Get-SCPerformanceData [-VMMServer <ServerConnection>] -PerformanceCounter <String> [-AllVNIC]
 [<CommonParameters>]
```

### AllVMNetworkGateway
```
Get-SCPerformanceData [-VMMServer <ServerConnection>] -PerformanceCounter <String> [-AllVMNetworkGateway]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPerformanceData** cmdlet gets performance data for host groups, clusters, hosts, and virtual machines.
You can request data for the following performance counters: 



- CPU usage

- Memory usage

- Storage IOPS usage

- Network IO usage

- Power savings

## EXAMPLES

### Example 1: Get performance data for a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "HostGroup01"
PS C:\> Get-SCPerformanceData -VMHostGroup $HostGroup -PerformanceCounter "MemoryUsage" -Timeframe "Hour"
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the memory usage data over the last three hours for HostGroup01.

### Example 2: Get performance data for a cluster
```
PS C:\> $Cluster = Get-SCVMHostCluster -Name "Cluster01.Contoso.com"
PS C:\> Get-SCPerformanceData -VMHostCluster $Cluster -PerformanceCounter "MemoryUsage" -Timeframe "Day"
```

The first command gets the cluster object named Cluster01 and stores the object in the $Cluster variable.

The second command gets the memory usage data for the last day (24 hours) for Cluster01.

### Example 3: Get performance data for a specified host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> Get-SCPerformanceData -VMHost $VMHost -PerformanceCounter "MemoryUsage" -Timeframe "Month"
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gerts the memory usage data for the last month (30 days) for VMHost01.

### Example 4: Get performance data for a specified virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Get-SCPerformanceData -VM $VM -PerformanceCounter "MemoryUsage" -Timeframe "Day"
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gerts the memory usage data for the last day (24 hours) for VM01.

### Example 5: Get performance data for all virtual machines
```
PS C:\> Get-SCPerformanceData -AllVM -PerformanceCounter "CPUUsage"
```

This command gets the CPU usage data for all virtual machines.

## PARAMETERS

### -AllVM
Indicates that data for all virtual machines is returned.

```yaml
Type: SwitchParameter
Parameter Sets: AllVM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllVMNetworkGateway
Indicates that data for all network gateways is returned.

```yaml
Type: SwitchParameter
Parameter Sets: AllVMNetworkGateway
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllVNIC
Indicates that data for all virtual network adapters is returned.

```yaml
Type: SwitchParameter
Parameter Sets: AllVNIC
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PerformanceCounter
Specifies the performance counter to use.
The acceptable values for this parameter are:

- CPUUsage
- MemoryUsage
- StorageIOPSUsage
- NetworkIOUsage
- PowerSavings

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: CPUUsage, MemoryUsage, StorageIOPSUsage, NetworkIOUsage, NetworkIOSent, NetworkIOReceived, PowerSavings

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeFrame
Specifies the timeframe in which to gather performance data.
The acceptable values for this parameter are:

- Hour
- Day
- Month

```yaml
Type: String
Parameter Sets: VM, Host, Cluster, HostGroup
Aliases: 
Accepted values: Hour, Day, Month

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
Virtual Machine Manager (VMM) supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: Host
Aliases: 

Required: True
Position: 0
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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: HostGroup
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### double[]
This cmdlet returns an array of double values.

## NOTES

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

