---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DF506A78-51D6-4DC2-A10F-816B16EEE852
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Install-SCVMHostCluster

## SYNOPSIS
Creates a failover cluster from Hyper-V hosts managed by VMM.

## SYNTAX

### CreateCluster
```
Install-SCVMHostCluster -VMHost <Host[]> -ClusterName <String> -Credential <VMMCredential>
 [-ClusterIPAddress <String[]>] [-ClusterIPAddressPool <StaticIPAddressPool[]>] [-ClusterReserve <Int32>]
 [-Description <String>] [-VMMServer <ServerConnection>] [-SetQuorumNodeMajority]
 [-SetQuorumDisk <ClientObject>] [-SkipValidation] [-JobGroup <Guid>] [-EnableS2D] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddNodes
```
Install-SCVMHostCluster -VMHost <Host[]> -VMHostCluster <HostCluster> -Credential <VMMCredential>
 [-VMMServer <ServerConnection>] [-SkipValidation] [-JobGroup <Guid>] [-EnableS2D] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddNodesFromBareMetal
```
Install-SCVMHostCluster -PhysicalComputerConfig <PhysicalComputerConfig[]> -VMHostCluster <HostCluster>
 -Credential <VMMCredential> [-VMMServer <ServerConnection>] [-SkipValidation] [-JobGroup <Guid>] [-EnableS2D]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### CreateClusterFromBareMetal
```
Install-SCVMHostCluster -PhysicalComputerConfig <PhysicalComputerConfig[]> -ClusterName <String>
 -Credential <VMMCredential> [-ClusterIPAddress <String[]>] [-ClusterIPAddressPool <StaticIPAddressPool[]>]
 [-ClusterReserve <Int32>] [-Description <String>] [-VMMServer <ServerConnection>] [-SetQuorumNodeMajority]
 [-SkipValidation] [-JobGroup <Guid>] [-EnableS2D] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Install-SCVMHostCluster** cmdlet creates a failover cluster from Hyper-V hosts managed by Virtual Machine Manager (VMM).
**Install-SCVMHostCluster** can also add a node to an existing cluster.

## EXAMPLES

### Example 1: Create a cluster from managed hosts
```
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "New York"
PS C:\> $Nodes = Get-SCVMHost | where {$_.Name -like "HostClus*" -and $_.VMHostGroup -eq $HostGroup} 
PS C:\> Install-SCVMHostCluster -VMHost $Nodes -ClusterName "Cluster01" -Credential $RunAsAcct
```

The first command gets the Run As account named RunAsAccount01 and stores it in the $RunAsAcct variable.

The second command gets the host group object named New York and stores the object in the $HostGroup variable.

The third command gets the cluster nodes that begin with the name HostClus in the host group stored in $HostGroup.
The command then stores the nodes in the $Nodes variable.

The last command creates the cluster and names it Cluster01.

### Example 2: Create a hyper converge cluster from managed hosts
```
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "New York"
PS C:\> $Nodes = Get-SCVMHost | where {$_.Name -like "HostClus*" -and $_.VMHostGroup -eq $HostGroup} 
PS C:\> Install-SCVMHostCluster -VMHost $Nodes -ClusterName "Cluster01" -Credential $RunAsAcct -EnableS2D
```

The first command gets the Run As account named RunAsAccount01, and then stores it in the $RunAsAcct variable.

The second command gets the host group object named New York, and then stores it in the $HostGroup variable.

The third command gets the cluster nodes that begin with the name HostClus in the host group stored in $HostGroup.
The command stores the nodes in the $Nodes variable.

The last command creates hyper converged cluster and names it Cluster01.

## PARAMETERS

### -ClusterIPAddress
Specifies one or more IP addresses to use as a cluster IP address.

```yaml
Type: String[]
Parameter Sets: CreateCluster, CreateClusterFromBareMetal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterIPAddressPool
Specifies a static IP address pool to use as a cluster IP address pool.

```yaml
Type: StaticIPAddressPool[]
Parameter Sets: CreateCluster, CreateClusterFromBareMetal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
Specifies the name of a cluster.

```yaml
Type: String
Parameter Sets: CreateCluster, CreateClusterFromBareMetal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterReserve
Specifies the number of host failures that a host cluster can sustain before VMM designates the cluster as over-committed.
The default value is 1.

```yaml
Type: Int32
Parameter Sets: CreateCluster, CreateClusterFromBareMetal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.
For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the host cluster.

```yaml
Type: String
Parameter Sets: CreateCluster, CreateClusterFromBareMetal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableS2D


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

### -PhysicalComputerConfig
Specifies an array of host configuration objects.

For information about host configuration objects, see the **New-SCVMHostConfig** cmdlet.

```yaml
Type: PhysicalComputerConfig[]
Parameter Sets: AddNodesFromBareMetal, CreateClusterFromBareMetal
Aliases: 

Required: True
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
Parameter Sets: CreateCluster
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
Parameter Sets: CreateCluster, CreateClusterFromBareMetal
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipValidation
Skips cluster validation tests when creating a cluster.

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

### -VMHost
Specifies an array of virtual machine host objects.

```yaml
Type: Host[]
Parameter Sets: CreateCluster, AddNodes
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
Parameter Sets: AddNodes, AddNodesFromBareMetal
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

[Move-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCVMHostCluster.md)

