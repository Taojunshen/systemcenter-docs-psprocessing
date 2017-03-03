---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D82190A7-0E00-4D9E-A2BA-9CCA543063DB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCVMHostCluster

## SYNOPSIS
Adds a Windows Server failover cluster, VMware ESX host cluster, or Citrix XenServer resource pool to VMM.

## SYNTAX

```
Add-SCVMHostCluster [-VMHostGroup <HostGroup>] [-VirtualizationManager <VirtualizationManager>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-ClusterReserve <UInt32>]
 -Credential <VMMCredential> [-AddVMHostJobsListVariable <String>] [-VMPaths <String>]
 [-BaseDiskPaths <String>] [-RemoteConnectEnabled <Boolean>] [-RemoteConnectPort <UInt32>]
 [-EnableLiveMigration <Boolean>] [-LiveMigrationMaximum <UInt32>] [-LiveStorageMigrationMaximum <UInt32>]
 [-UseAnyMigrationSubnet <Boolean>] [-MigrationSubnet <String[]>]
 [-MigrationAuthProtocol <MigrationAuthProtocolType>]
 [-MigrationPerformanceOption <MigrationPerformanceOptionType>] [-Reassociate <Boolean>]
 [-NonTrustedDomainHost] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCVMHostCluster** cmdlet adds an existing Windows Server failover cluster, VMware ESX host cluster, or a Citrix XenServer resource pool to the Virtual Machine Manager (VMM) database so that VMM can manage the host cluster.

Before you can use the **Add-SCVMHostCluster** cmdlet to add a Windows Server cluster to VMM, you must use the Failover Cluster Management tool to create and configure the host cluster.
To create a host cluster by using VMM, use the **Install-SCVMHostCluster** cmdlet.

Before you can use the **Add-SCVMHostCluster** cmdlet to add a Citrix XenServer resource pool to VMM, you must use Citrix XenCenter to create and configure the resource pool.

Before using **Add-SCVMHostCluster** to add ESX host clusters, you must use the **Add-SCVirtualizationManager** cmdlet to add a VMware vCenter Server to your VMM environment and import its data.
After you add the vCenter Server to VMM, you can add and manage VMware ESX clusters using VMM.

## EXAMPLES

### Example 1: Add a failover cluster to VMM
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $VMHostGroup = Get-SCVMHostGroup | where {$_.Path -eq "All Hosts"}
PS C:\> Add-SCVMHostCluster -Name "VMHostCluster01.Contoso.com" -VMHostGroup $VMHostGroup -RemoteConnectEnabled $True -RemoteConnectPort 5900 -Credential $Credential
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $Credential variable.
The Run As account used for this operation must be a domain account with administrator rights on all the nodes of the failover cluster that you want to add.

The second command gets the host group object All Hosts.
This is the host group that will be the container for the nodes in this host cluster.

The last command adds the failover cluster VMHostCluster01 to the VMM database, specifies All Hosts as the host group, enables remote connections, and specifies TCP port 5900 for remote connections to each node of the cluster.
As the last command is processed, the $Credential variable provides the stored Run As account to **Add-SCVMHostCluster**.

## PARAMETERS

### -AddVMHostJobsListVariable
Returns an array of job variable objects for jobs that are created for each node when hosts in a host cluster are added to VMM.
VMM uses these job variables to track the progress of each job individually.

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

### -BaseDiskPaths
Specifies the paths to base disks.

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLiveMigration
Indicates whether live migration is enabled on the host.

```yaml
Type: Boolean
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

### -LiveMigrationMaximum
Specifies the maximum number of simultaneous live migrations.

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

### -LiveStorageMigrationMaximum
Specifies the maximum number of simultaneous live storage migrations.

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

### -MigrationAuthProtocol
Specifies the authorization protocol used for migration.
The acceptable values for this parameter are: CredSSP, Kerberos.

```yaml
Type: MigrationAuthProtocolType
Parameter Sets: (All)
Aliases: 
Accepted values: CredSSP, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationPerformanceOption
Specifies the migration performance option type.
The acceptable values for this parameter are:

- Standard
- UseCompression
- UseSmbTransport

```yaml
Type: MigrationPerformanceOptionType
Parameter Sets: (All)
Aliases: 
Accepted values: Standard, UseCompression, UseSmbTransport

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MigrationSubnet
Specifies an array of subnets to use for migration.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonTrustedDomainHost
Indicates that the host to be added to VMM belongs to a non-trusted domain.

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

### -Reassociate
Reassociates a host currently managed by one VMM server with another VMM server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteConnectEnabled
Enables, when set to $True, a connection on a host server that lets users connect to their virtual machines remotely.
This parameter only applies to virtual machines on Hyper-V hosts.
It is not applicable to virtual machines on VMware ESX hosts or Citrix XenServer hosts.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteConnectPort
Specifies a default value for the TCP port to use when a remote user connects to a virtual machine.
Typically, the default port for a Hyper-V host is 2179.
This parameter does not apply to VMware ESX hosts or Citrix XenServer hosts.

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

### -UseAnyMigrationSubnet
Indicates whether any subnet can be used for migration.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: 

Required: False
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

### -VMPaths
Specifies a set of default paths (as strings separated by the pipeline operator) on a host where virtual machine files can be stored. 

Example format: `-VMPaths "C:\Folder1|C:\Folder2|C:\Folder3"`

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

### -VirtualizationManager
Specifies a virtualization manager object managed by VMM.

```yaml
Type: VirtualizationManager
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

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

[Install-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md)

[Move-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCVMHostCluster.md)

