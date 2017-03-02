---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D1493BBA-1B91-41A7-A4FE-F93621439D0F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitorState.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitorState.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitorState.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCPROMonitorState

## SYNOPSIS
Gets the state of a specified PRO monitor on a specific VMM object.

## SYNTAX

### VMHost (Default)
```
Get-SCPROMonitorState [-VMMServer <ServerConnection>] -VMHost <Host> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### Cloud
```
Get-SCPROMonitorState [-VMMServer <ServerConnection>] -Cloud <Cloud> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### VM
```
Get-SCPROMonitorState [-VMMServer <ServerConnection>] -VM <VM> [-PROMonitor <PROMonitor>] [<CommonParameters>]
```

### HostCluster
```
Get-SCPROMonitorState [-VMMServer <ServerConnection>] -VMHostCluster <HostCluster> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### Service
```
Get-SCPROMonitorState [-VMMServer <ServerConnection>] -Service <Service> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### VMMServer
```
Get-SCPROMonitorState [-VMMServer <ServerConnection>] [-VMMServerScope] [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

### ComputerTier
```
Get-SCPROMonitorState [-VMMServer <ServerConnection>] -ComputerTier <ComputerTier> [-PROMonitor <PROMonitor>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPROMonitorState** cmdlet gets the state of a specified Performance and Resource Optimization (PRO) monitor on a specific Virtual Machine Manager (VMM) object.

## EXAMPLES

### Example 1: Get the state of a PRO monitor for a specific host
```
PS C:\> $VMHost = Get-VMHost "VMHost01.Contoso.com"
PS C:\> $PROMonitor = Get-SCPROMonitor -Name "System Center Virtual Machine Manager Maximum Dynamic Memory Monitor" -ManagementPackName "System Center Virtual Machine Manager PRO V2 HyperV Host Performance"
PS C:\> $PROMonitorState = Get-SCPROMonitorState -PROMonitor $PROMonitor -VMHost $VMHost
PS C:\> $PROMonitorState
```

The first command gets the virtual machine host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the PRO monitor object with the specified name and management pack name and stores the object in the $PROMonitor variable.

The third command gets the PRO monitor state for the PRO monitor object stored in $PROMonitor for VMHost01 and stores the state in the $PROMonitorState variable.

The last command displays the state information stored in $PROMonitorState.

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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Service
Specifies a VMM service object.

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

### PROMonitorState
This cmdlet returns a **PROMonitorState** object.

## NOTES

## RELATED LINKS

[Get-SCPROMonitor](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitor.md)

[Reset-SCPROMonitorState](xref:SystemCenter2016/VirtualMachineManager/vlatest/Reset-SCPROMonitorState.md)

