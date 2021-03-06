---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3F25DB2B-C0A1-44EC-8A60-2319F0650800
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCPROTip

## SYNOPSIS
Gets PRO tip objects from the VMM database.

## SYNTAX

### AllTips (Default)
```
Get-SCPROTip [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### VMTips
```
Get-SCPROTip [-VMMServer <ServerConnection>] -VM <VM> [<CommonParameters>]
```

### HostTips
```
Get-SCPROTip [-VMMServer <ServerConnection>] -VMHost <Host> [<CommonParameters>]
```

### CloudTips
```
Get-SCPROTip [-VMMServer <ServerConnection>] -Cloud <Cloud> [<CommonParameters>]
```

### ServiceTips
```
Get-SCPROTip [-VMMServer <ServerConnection>] -Service <Service> [<CommonParameters>]
```

### VMMServerTips
```
Get-SCPROTip [-VMMServer <ServerConnection>] [-VMMServerScope] [<CommonParameters>]
```

### ClusterTips
```
Get-SCPROTip [-VMMServer <ServerConnection>] -VMHostCluster <HostCluster> [<CommonParameters>]
```

### GetById
```
Get-SCPROTip [-VMMServer <ServerConnection>] -PROTipID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPROTip** cmdlet gets one or more Performance and Resource Optimization (PRO) tip objects from the Virtual Machine Manager (VMM) database.

If PRO is enabled, a PRO tip recommends an action in response to an alert generated by Operations Manager for hosts that are members of a host group or for hosts configured in a host cluster, as well as for the virtual machines deployed on those hosts.
A recommended action might be to move a virtual machine to a new host or to add a CPU to a virtual machine.

PRO provides workload and application-aware resource optimization within host groups or host clusters that are managed by both VMM and Operations Manager.
To receive PRO tips for these hosts, you must first configure PRO for VMM.
This includes deploying Operations Manager, which generates the PRO tips based on monitors provided by PRO-enabled management packs.
PRO tip recommendations are based on policies implemented through Operations Manager.

You can use **Get-SCPROTip** and the other PROTip cmdlets only on Hyper-V, VMware, or Citrix XenServer hosts that belong to a host group, that are configured in a host cluster, or that belong to a private cloud.

## EXAMPLES

### Example 1: Get all PRO tips for all hosts and all virtual machines managed by VMM
```
PS C:\> Get-SCPROTip
```

This command gets all PRO tips from the VMM database and displays information about each PRO tip.

### Example 2: Get all active PRO tips for a specific host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> Get-SCPROTip -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets all active PRO tips for VMHost01 and displays information about each tip.

## PARAMETERS

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: CloudTips
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: GetById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Service
Specifies a VMM service object.

```yaml
Type: Service
Parameter Sets: ServiceTips
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VMTips
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: HostTips
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
Parameter Sets: ClusterTips
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
Parameter Sets: VMMServerTips
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

### PROTip
This cmdlet returns a **PROTip** object.

## NOTES

## RELATED LINKS

[Add-PROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-PROTip.md)

[Clear-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md)

[Invoke-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md)

[Set-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md)

[Test-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md)

