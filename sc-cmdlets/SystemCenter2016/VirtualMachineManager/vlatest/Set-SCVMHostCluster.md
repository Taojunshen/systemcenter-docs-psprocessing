---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 54BB0C0C-A038-4A8C-9ABB-31B83F527CA3
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVMHostCluster

## SYNOPSIS
Modifies the properties of a virtual machine host cluster managed by VMM.

## SYNTAX

```
Set-SCVMHostCluster [-VMHostCluster] <HostCluster> [-Description <String>] [-ClusterReserve <UInt32>]
 [-JobGroup <Guid>] [-SetQuorumNodeMajority] [-SetQuorumDisk <ClientObject>]
 [-VMHostManagementCredential <VMMCredential>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMHostCluster** cmdlet modifies the properties of a host cluster managed by Virtual Machine Manager (VMM).
Properties that you can modify include changing the cluster reserve setting.

The *ClusterReserve* parameter specifies the number of host failures that a host cluster can sustain before VMM considers the cluster to be over-committed.
An over-committed host cluster is one that cannot withstand the specified number of host failures and keep all of the virtual machines in the cluster running.

VMM uses the following processes to determine over-commitment: 

- Host Placement.
The placement process calculates whether adding a new virtual machine to the host cluster will over-commit the host cluster and, if so, placement stops recommending the deployment of additional virtual machines on hosts in that cluster. 
- Cluster Refresher.
The host cluster refresher calculates, at periodic  intervals, whether a host cluster is over-committed or not based on the following events: 

 - A change in the value specified for the *ClusterReserve* parameter. 
 - The failure or removal of nodes from the host cluster. 
 - The addition of nodes to the host cluster. 
 - The discovery of new virtual machines on nodes in the host cluster.

The following examples illustrate how over-commitment works.

Example 1: Over-commitment when all nodes are functioning

If you specify a cluster reserve of 2 for an 8-node host cluster, and all 8 nodes are functioning, the host cluster is over-committed if any combination of 6 (8 minus 2) nodes lacks the capacity to accommodate existing virtual machines.

Example 2: Over-commitment when some nodes are not functioning

If you specify a cluster reserve of 2 for an 8-node host cluster, but only 5 nodes are functioning, the host cluster is over-committed if any combination of 3 (5 minus 2) nodes lacks the capacity to accommodate existing virtual machines.

## EXAMPLES

### Example 1: Change the setting for the cluster reserve for a host cluster
```
PS C:\> $VMHostCluster = Get-SCVMHostCluster -Name "VMHostCluster01.Contoso.com"
PS C:\> Set-SCVMHostCluster -VMHostCluster $VMHostCluster -ClusterReserve 2
```

The first command gets the host cluster object named VMHostCluster01.Contoso.com and stores the object in the $VMHostCluster variable.

The second command changes the value for the cluster reserve for host cluster VMHostCluster01 to 2.

## PARAMETERS

### -ClusterReserve
Specifies the number of host failures that a host cluster can sustain before VMM designates the cluster as over-committed.
The default value is 1.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
States a description for the specified object.

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -SetQuorumDisk
Specifies a disk to use as the quorum disk for the cluster.

```yaml
Type: ClientObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SetQuorumNodeMajority
Sets the quorum mode to Node Majority for the cluster.

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

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostManagementCredential
This parameter is obsolete.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMHostCluster
This cmdlet returns a **VMHostCluster** object.

## NOTES

## RELATED LINKS

[Add-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostCluster.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

[Install-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md)

[Move-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCVMHostCluster.md)

