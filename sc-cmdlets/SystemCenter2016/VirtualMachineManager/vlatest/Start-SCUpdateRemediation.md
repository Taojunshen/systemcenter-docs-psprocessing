---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 80FA9786-E651-4F71-A6C8-F5A455E821A9
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCUpdateRemediation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCUpdateRemediation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCUpdateRemediation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Start-SCUpdateRemediation

## SYNOPSIS
Initiates the action of installing one or more updates on a managed server that are required from an assigned baseline.

## SYNTAX

### VMHostCluster
```
Start-SCUpdateRemediation [-VMMServer <ServerConnection>] -VMHostCluster <HostCluster> [-Baseline <Baseline>]
 [-Updates <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]>]
 [-SuspendReboot] [-UseLiveMigration] [-BypassMaintenanceModeCheck] [-RemediateAllClusterNodes]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### ClusterRemediationWithJobgroup
```
Start-SCUpdateRemediation [-VMMServer <ServerConnection>] -VMHostCluster <HostCluster> [-UseLiveMigration]
 [-BypassMaintenanceModeCheck] -JobGroup <Guid> [-StartNow] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### ClusterNodeRemediationWithJobgroup
```
Start-SCUpdateRemediation [-VMMServer <ServerConnection>] -VMHostCluster <HostCluster> [-Baseline <Baseline>]
 [-Updates <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]>]
 [-SuspendReboot] -JobGroup <Guid> -VMHost <Host> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### VMMManagedComputer
```
Start-SCUpdateRemediation [-VMMServer <ServerConnection>] [-Baseline <Baseline>]
 [-Updates <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]>]
 [-SuspendReboot] [-JobGroup <Guid>] [-StartNow] [-EnableMaintenanceMode]
 -VMMManagedComputer <VMMManagedComputer> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCUpdateRemediation** cmdlet initiates the action of installing one or more non-compliant updates on a managed server that are required from an assigned baseline.

## EXAMPLES

### Example 1: Bring a host into compliance with a specified baseline
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $Compliance = Get-SCComplianceStatus -VMMManagedComputer $VMHost.ManagedComputer
PS C:\> $Baseline = Get-SCBaseline -Name "Security Baseline"
PS C:\> $Compliance = Start-SCComplianceScan -VMMManagedComputer $VMHost.ManagedComputer -Baseline $Baseline
PS C:\> Start-SCUpdateRemediation -VMMManagedComputer $VMHost.ManagedComputer -Baseline $Baseline
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the compliance status for host VMHost01 and stores the status object in the $Compliance variable.

The third command gets the baseline object named Security Baseline and stores the object in the $Baseline variable.

The fourth command starts a compliance scan on VMHost01 against the Security Baseline baseline and stores the results in the $Compliance variable.

The last command starts remediation of VMHost01 to bring it into compliance with the Security Baseline baseline.

## PARAMETERS

### -Baseline
Specifies a Virtual Machine Manager (VMM) baseline object.

```yaml
Type: Baseline
Parameter Sets: VMHostCluster, ClusterNodeRemediationWithJobgroup, VMMManagedComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BypassMaintenanceModeCheck
Indicates that cluster patching continues node by node even if a cluster node is already in maintenance mode.
By default, cluster remediation fails if any of the cluster nodes are already in maintenance mode.

```yaml
Type: SwitchParameter
Parameter Sets: VMHostCluster, ClusterRemediationWithJobgroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EnableMaintenanceMode
Enables maintenance mode for a stand-alone VMM management server that also serves as a host.
By default, when remediating a stand-alone host, VMM does not put it into maintenance mode.

```yaml
Type: SwitchParameter
Parameter Sets: VMMManagedComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that run as a group just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: ClusterRemediationWithJobgroup, ClusterNodeRemediationWithJobgroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: VMMManagedComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemediateAllClusterNodes
Indicates that update remediation is performed on all nodes of a cluster.

```yaml
Type: SwitchParameter
Parameter Sets: VMHostCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartNow
Identifies the last command of a jobgroup and starts running the commands within the jobgroup.
This parameter must be used with the *JobGroup* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: ClusterRemediationWithJobgroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: VMMManagedComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuspendReboot
Indicates that the computer that is being updated will not reboot when a reboot is required by a software update.

```yaml
Type: SwitchParameter
Parameter Sets: VMHostCluster, ClusterNodeRemediationWithJobgroup, VMMManagedComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Updates
Specifies one or more software updates.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]
Parameter Sets: VMHostCluster, ClusterNodeRemediationWithJobgroup, VMMManagedComputer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UseLiveMigration
Indicates that live migration is used during a cluster remediation.

```yaml
Type: SwitchParameter
Parameter Sets: VMHostCluster, ClusterRemediationWithJobgroup
Aliases: 

Required: False
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
Parameter Sets: ClusterNodeRemediationWithJobgroup
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
Parameter Sets: VMHostCluster, ClusterRemediationWithJobgroup, ClusterNodeRemediationWithJobgroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMManagedComputer
Specifies a computer object that is managed by VMM.

```yaml
Type: VMMManagedComputer
Parameter Sets: VMMManagedComputer
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ComplianceStatus
This cmdlet returns a **ComplianceStatus** object.

## NOTES

## RELATED LINKS

[Get-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCBaseline.md)

[Get-SCComplianceStatus](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComplianceStatus.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Start-SCComplianceScan](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCComplianceScan.md)

