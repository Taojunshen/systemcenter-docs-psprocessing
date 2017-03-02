---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CFC981FF-B975-47B0-A742-A218B7AB34E5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Find-SCCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Find-SCCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Find-SCCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Find-SCCluster

## SYNOPSIS
Finds the specified failover cluster in a VMM environment.

## SYNTAX

### UserCredentials (Default)
```
Find-SCCluster [-VMMServer <ServerConnection>] [-ComputerName] <String> [-EnumerateFileServers <Boolean>]
 [-NonTrustedDomainHost] -Credential <VMMCredential> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### ServerCredentials
```
Find-SCCluster [-VMMServer <ServerConnection>] -LibraryServer <LibraryServer> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Find-SCCluster** cmdlet queries Virtual Machine Manager (VMM) for the specified failover cluster or one of its nodes.
If the cluster is found, VMM returns an object that contains more information about the failover cluster.
Information returned by **Find-SCCluster** includes cluster name, nodes of the cluster, and highly available file servers hosted by the cluster.

## EXAMPLES

### Example 1: Find all nodes of a failover cluster from the cluster name
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $Cluster = Find-SCCluster -ComputerName "VMHostCluster01.Contoso.com" -Credential $Credential
PS C:\> $Cluster.ClusterNodes
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $Credential variable.

The second command queries VMM for the failover cluster named VMHostCluster01 and stores the cluster object in $Cluster, using $Credential to provide the Run As account to **Find-SCCluster**.
The *ComputerName* parameter treats the name of the cluster as if it were the name of a computer.

The last command displays the FQDNs of the cluster nodes to the user.

### Example 2: Find all nodes of a failover cluster from one of the node names
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $Cluster = Find-SCCluster -ComputerName "VMHostNode02.Contoso.com" -Credential $Credential
PS C:\> $Cluster.Name
PS C:\> $Cluster.ClusterNodes
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $Credential variable.

The second command queries VMM for a failover cluster node named VMHostNode02 and stores the returned cluster object in $Cluster.

The third command displays the FQDN of the cluster to the user.

The last command displays the FQDN of each node in the cluster to the user.

### Example 3: Find, by using the cluster name, all highly available file servers hosted by that failover cluster
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $Cluster = Find-SCCluster -ComputerName "VMHostCluster03.Contoso.com" -Credential $Credential
PS C:\> $Cluster.HAFileServers
```

The first command gets the RunAs account object RunAsAccount01 and stores the object in the $Credential variable.

The second command queries VMM for the failover cluster named VMHostCluster03 and stores the cluster object in $Cluster.

The third command displays the FQDNs of all highly available file servers hosted by the failover cluster stored in $Cluster.
This command assumes that the failover cluster is hosting at least one highly available file server.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
Valid formats are: fully qualified domain name (FQDN), IPv4 or IPv6 address, or NetBIOS name.

```yaml
Type: String
Parameter Sets: UserCredentials
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of the Restart-SCJob cmdlet, has permission to complete a restarted task.

For more information about the **PSCredential** object, type: `Get-Help Get-Credential`.

For more information about Run As accounts, type: `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: UserCredentials
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnumerateFileServers
Indicates whether the file servers are listed.

```yaml
Type: Boolean
Parameter Sets: UserCredentials
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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: ServerCredentials
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonTrustedDomainHost
Indicates that the host to be added to VMM belongs to a non-trusted domain.

```yaml
Type: SwitchParameter
Parameter Sets: UserCredentials
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization (PRO) tip that triggered this action.
This allows for auditing of PRO tips.

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

### Cluster
This cmdlet returns a **Cluster** object.

## NOTES

## RELATED LINKS

[Add-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostCluster.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

[Install-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md)

[Move-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCVMHostCluster.md)

