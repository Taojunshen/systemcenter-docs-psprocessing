---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 821CA22E-26B4-45F1-9E0C-864CED56AAA1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitorConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitorConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitorConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCPROMonitorConfiguration

## SYNOPSIS
Gets a PRO monitor configuration object for a specified scope.

## SYNTAX

### HostGroup (Default)
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] -VMHostGroup <HostGroup>
 [-PROMonitor <PROMonitor>] [<CommonParameters>]
```

### Cloud
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] -Cloud <Cloud> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### HostCluster
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] -VMHostCluster <HostCluster>
 [-PROMonitor <PROMonitor>] [<CommonParameters>]
```

### Service
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] -Service <Service> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### VMMServer
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] [-VMMServerScope] [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### VMHost
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] -VMHost <Host> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### VM
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] -VM <VM> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### ComputerTier
```
Get-SCPROMonitorConfiguration [-VMMServer <ServerConnection>] -ComputerTier <ComputerTier>
 [-PROMonitor <PROMonitor>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPROMonitorConfiguration** cmdlet gets one or more Performance and Resource Optimization (PRO) monitor configuration objects for a specified scope.

## EXAMPLES

### Example 1: Get all PRO monitor configuraiton objects on a specified host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "Production"
PS C:\> $PROMonitorConfig = Get-SCPROMonitorConfiguration -VMHostGroup $HostGroup
PS C:\> $PROMonitorConfig
```

The first command gets the host group object named Production and stores the object in the $HostGroup variable.

The second command gets the PRO monitor configuration objects on the host group stored in $HostGroup (Production) and stores the objects in the $PROMonitorConfig variable.

The last command displays information about the PRO monitor configuration objects stored in $PROMonitorConfig to the user.

## PARAMETERS

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

### -ComputerTier
Specifies a computer tier object.

```yaml
Type: ComputerTier
Parameter Sets: ComputerTier
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROMonitor
Specifies a PRO monitor object.

```yaml
Type: PROMonitor
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Specifies a Virtual Machine Manager (VMM) service object.

```yaml
Type: Service
Parameter Sets: Service
Aliases: 

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
Parameter Sets: VMHost
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: HostCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: HostGroup
Aliases: 

Required: True
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

### -VMMServerScope
Indicates that the PRO information returned is scoped to the entire VMM server.

```yaml
Type: SwitchParameter
Parameter Sets: VMMServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PROMonitorConfiguration
This cmdlet returns a **PROMonitorConfiguration** object.

## NOTES

## RELATED LINKS

[Set-SCPROMonitorConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROMonitorConfiguration.md)

