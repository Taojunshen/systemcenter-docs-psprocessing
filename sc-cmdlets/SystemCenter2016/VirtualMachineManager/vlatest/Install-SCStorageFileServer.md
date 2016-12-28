---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: ED9211A5-DA9A-43B5-BDB4-10550866EE7B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Install-SCStorageFileServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Install-SCStorageFileServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Install-SCStorageFileServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Install-SCStorageFileServer

## SYNOPSIS
Installs failover clustering and a file server on a set of computers.

## SYNTAX

### UseBareMetalMachines
```
Install-SCStorageFileServer -PhysicalComputerConfig <PhysicalComputerConfig[]> -ClusterName <String>
 -ScaleoutFileServerName <String> [-ClusterIPAddress <String[]>] [-SkipClusterValidation] [-EnableS2D]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddNodesUsingBareMetalMachines
```
Install-SCStorageFileServer -PhysicalComputerConfig <PhysicalComputerConfig[]>
 -StorageFileServer <StorageFileServer> [-SkipClusterValidation] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### AddNodesUsingExistingServers
```
Install-SCStorageFileServer -AddExistingComputer <String[]> -StorageFileServer <StorageFileServer>
 [-SkipClusterValidation] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### UseExistingServers
```
Install-SCStorageFileServer -AddExistingComputer <String[]> -ClusterName <String>
 -ScaleoutFileServerName <String> [-ClusterIPAddress <String[]>] -RunAsAccount <RunAsAccount>
 [-SkipClusterValidation] [-EnableS2D] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Install-SCStorageFileServer** cmdlet installs failover clustering and a file server on a set of computers.
The computers can be provisioned by Virtual Machine Manager (VMM) by using an Open Software Descriptor (OSD) or they can already have an operating system installed.

## EXAMPLES

### Example 1: Create file server with shared storage
```
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Install-SCStorageFileServer -ClusterName "Cluster01" -ScaleoutFileServerName "SOFS01" -RunAsAccount $RunAsAcct -AddExistingComputer @("node1", "node2") -RunAsynchronously
```

The first command gets the Run As account named RunAsAccount01, and then stores it in the $RunAsAcct variable.

The second command creates file server with the cluster named Cluster01 and file server role SOFS01.

### Example 2: Create file server with storage spaces direct
```
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Install-SCStorageFileServer -ClusterName "Cluster01" -ScaleoutFileServerName "SOFS01" -RunAsAccount $RunAsAcct -AddExistingComputer @("node1", "node2") -RunAsynchronously -EnableS2D
```

The first command gets the Run As account named RunAsAccount01, and then stores it in the $RunAsAcct variable.

The second command creates a file server with the cluster named Cluster01 and file server role SOFS01.
The command includes the *EnableS2D* parameter.

## PARAMETERS

### -AddExistingComputer
Specifies an array of computers that this cmdlet adds.
Specify the fully qualified domain names (FQDN), NetBIOS names, or IP addresses of servers on the network that have an operating system.

```yaml
Type: String[]
Parameter Sets: AddNodesUsingExistingServers, UseExistingServers
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterIPAddress
Specifies an array of IP addresses to use as a cluster IP address.

```yaml
Type: String[]
Parameter Sets: UseBareMetalMachines, UseExistingServers
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
Specifies the name for the cluster.

```yaml
Type: String
Parameter Sets: UseBareMetalMachines, UseExistingServers
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableS2D


```yaml
Type: SwitchParameter
Parameter Sets: UseBareMetalMachines, UseExistingServers
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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
Parameter Sets: UseBareMetalMachines, AddNodesUsingBareMetalMachines
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
Parameter Sets: UseExistingServers
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

### -ScaleoutFileServerName
Specifies the name of a scale-out file server role.

```yaml
Type: String
Parameter Sets: UseBareMetalMachines, UseExistingServers
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipClusterValidation
Indicates that this cmdlet skips cluster validation tests when it creates a cluster.

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

### -StorageFileServer
Specifies a storage file server object.

```yaml
Type: StorageFileServer
Parameter Sets: AddNodesUsingBareMetalMachines, AddNodesUsingExistingServers
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

### StorageFileServer
This cmdlet returns a **StorageFileServer** object.

## NOTES

## RELATED LINKS

[Get-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileServer.md)

[Set-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServer.md)

[Uninstall-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCStorageFileServer.md)

