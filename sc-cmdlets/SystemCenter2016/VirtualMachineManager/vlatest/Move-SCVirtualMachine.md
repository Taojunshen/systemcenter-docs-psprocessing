---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: 6537BFC5-B3F1-40CD-8A4C-F3BD591CDE4B
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Move-SCVirtualMachine

## SYNOPSIS
Moves a virtual machine stored in the VMM library or deployed on a host to a new location on a host.

## SYNTAX

```
Move-SCVirtualMachine [-VM] <VM> [-VMHost <Host>] [-ReplicationGroup <ReplicationGroup>]
 [-BlockLiveMigrationIfHostBusy] [-UseDiffDiskOptimization] [-StartVMOnTarget] [-DiscardSavedState] [-UseLAN]
 [-UseCluster] [-HighlyAvailable <Boolean>] [-Path <String>] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Move-SCVirtualMachine** cmdlet moves a virtual machine stored in the Virtual Machine Manager (VMM) library or deployed on a host to a new location on a host.

In System Center 2016, you can take advantage of new migration capabilities included in Windows Server 2016.
These capabilities include live migration of virtual machines between two stand-alone computers and live migration between stand-alone computers and a cluster node.
Additionally, multiple concurrent live migrations are supported.
For more information about how to migrate virtual machines in System Center 2016, see Migrating Virtual Machines and Storage in VMMhttps://technet.microsoft.com/en-us/library/mt710321(v=sc.16).aspx (https://technet.microsoft.com/en-us/library/mt710321(v=sc.16).aspx) in the TechNet Library.

If you move a virtual machine deployed on a host running Windows Server 2008 R2 to a host running Windows Server 2016, you cannot move the virtual machine back to a host running Windows Server 2008 R2.

VMM includes storage migration features that let you move one or more virtual hard disks of a running virtual machine to a different location.
You can use the current cmdlet and the Move-SCVirtualHardDisk cmdlet to move Windows-based virtual hard disk (.vhd) files and VMware-based virtual hard disk (.vmdk) files to a location on a different host.
You can also use the **Move-SCVirtualHardDisk** cmdlet to move a .vhd file or a .vmdk file from one location to another on the same host.

To move a virtual machine from a host and store it in the library, you must use the Save-SCVirtualMachine cmdlet.

VMM can use any of the following transfer methods, listed in the order in which VMM tries to use them:

- Hyper-V live migration. If a virtual machine is running and is deployed on a Hyper-V host that is a node of a Windows Server 2008 R2 or Windows Server 2016 host cluster, by default, VMM uses Hyper-V live migration to move the virtual machine to another node in the cluster without any disruption of service. Moving a running virtual machine does not disconnect it from the network. The virtual machine retains its high availability attribute. You do not have to specify a path. You can start live migration of multiple virtual machines at the same time.
- Windows Server 2008 Cluster Migration. System Center 2016 continues to support Windows 2008 Cluster Migration, which is sometimes called Quick Migration. Cluster Migration moves a running virtual machine on a Hyper-V node of a host cluster. It also lets you move a virtual machine that is in a stopped or saved state, and that is deployed to another node in the cluster. You can use Cluster Migration to move a virtual machine in a stopped or saved state if the virtual machine is deployed on either of the following nodes: 

----A node in a Windows Server 2008 cluster
----A node in a Windows Server 2008 R2 cluster

You do not have to specify a path. Windows Server 2008 Cluster Migration puts the virtual machine in a saved state during migration. This operation causes a temporary loss of service to any users of that virtual machine.
- VMware live migration. If a virtual machine deployed on a VMware ESX host uses shared storage, VMM can use the VMware live migration feature to move the virtual machine to a new host. This feature is called VMware VMotion. You do not have to specify a path. The current cmdlet can use VMware VMotion to move a virtual machine from one ESX host to another only if both ESX hosts are in the same Datacenter container on the vCenter Server.
- Citrix XenServer XenMotion. If a virtual machine deployed on a Citrix XenServer host uses shared storage and is part of the same Resource Pool, VMM can use the XenServer live migration feature to move the virtual machine to a different XenServer host. The live migration feature is called Citrix XenMotion.
- SAN migration (Fibre Channel, iSCSI, or NPIV). If the virtual machine is on a host that is connected to a SAN and the virtual machine is on a SAN LUN, VMM can move that virtual machine to another host if that host has access to the same SAN. In a SAN transfer, the target LUNs are redirected from the source host to the destination host. This migration does not move files. A SAN transfer is much faster than moving virtual machine files from one host to another over a local area network (LAN). VMM supports SAN migration of virtual machines into and out of a cluster. You must specify a path. VMM can use an NPIV SAN transfer if a host bus adapter (HBA) with NPIV support is available.
- Network Migration. If no faster method is available, VMM uses a network transfer to move the virtual machine files from one host to another over the LAN that connects the two hosts. You can decide to use this transfer type even if the SAN transfer type is available. You must specify a path.

When more than one transfer type is available, this cmdlet automatically uses the fastest available transfer type to move a virtual machine.
If a method is not appropriate or available for the virtual machine that you want to move, VMM tries to use the next method in the list.
If you want to force the use of a network transfer, specify the *UseLAN* parameter.

## EXAMPLES

### Example 1: Move a virtual machine from the library to a host
```
PS C:\>$VM = Get-SCVirtualMachine | Where-Object { $_.Name -Eq "VM01" -And $_.LibraryServer -Eq "LibServer01.Contoso.com" }
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> Move-SCVirtualMachine -VMHost $VMHost -VM $VM -Path "D:\VirtualMachinePath"
```

The first command command gets the virtual machine object named VM01, and then stores that object in the $VM variable.
In this example, the virtual machine stored in the VMM library on the library server named LibServer01.
This example assumes that only one virtual machine named VM01 is currently stored on LibServer01.

The second command gets the host object named VMHost01, and then stores that object in the $VMHost variable.

The last command moves the virtual machine from its current location in the library to the location D:\VirtualMachinePath on the host stored in $VMHost.
The command automatically uses the fastest available transfer type.
When the command finishes, it returns information about the moved virtual machine.

### Example 2: Move a virtual machine from the library to a host asynchronously
```
PS C:\>$VM = Get-SCVirtualMachine | Where-Object { $_.Name -Eq "VM01" -And $_.LibraryServer -Eq "LibServer01.Contoso.com" }
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com"
PS C:\> Move-SCVirtualMachine -VMHost $VMHost -VM $VM -Path "D:\VirtualMachinePath" -RunAsynchronously -JobVariable "MoveVMJob"
PS C:\> $MoveVMJob
```

The first two commands in this example are identical to the commands in the first example, except for the name of the virtual machine host.

The third command moves the virtual machine from its current location to D:\VirtualMachinePath on VMHost02.
The command specifies the *RunAsynchronously* parameter to return control to the command shell immediately.
The command specifies the *JobVariable* parameter to track the progress of the job.
The command stores a record of the job progress in the $MoveVMJob variable.
For the *JobVariable* parameter, you do not specify the dollar sign ($) to create the variable.

The last command displays the contents of $MoveVMJob, which includes a description of the move job, its status, its progress, and other information.

### Example 3: Move a virtual machine from the library to a host by forcing a LAN transfer
```
PS C:\>$VM = Get-SCVirtualMachine | Where-Object { $_.Name -Eq "VM03" -And $_.LibraryServer -Eq "LibServer01.Contoso.com" }
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost03.Contoso.com"
PS C:\> Move-SCVirtualMachine -VMHost $VMHost -VM $VM -Path "D:\VirtualMachinePath" -UseLAN
```

The first command gets the virtual machine object named VM03 on library server LibServer01, and then stores that object in the $VM variable.

The second command gets the host object named VMHost03, and then stores that object in the $VMHost variable.

The last command moves the virtual machine VM03 from its current location in the library to D:\VirtualMachinePath on VMHost03.
The command specifies the *UseLAN* parameter to specify that the transfer use a network transfer, even if faster transfer mechanisms are available.

### Example 4: Move a virtual machine between hosts by using VMware VMotion
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM04" | Where-Object {$_.VMHost.Name -Eq "ESXHost01"}
PS C:\> $VMHost = Get-SCVMHost | Where-Object {$_.Name -Eq "ESXHost02"}
PS C:\> Move-SCVirtualMachine -VM $VM -VMHost $VMHost -Path "[Storage2]"
```

The first command gets the virtual machine object named VM04 on ESXHost01, and then stores that object in the $VM variable.

The second command gets the ESX host object named ESXHost02, and then stores that object in the $VMHost variable.

The final command uses VMware VMotion to move the virtual machine from its current ESX host to the other ESX host.

NOTE: The **Move-SCVirtualMachine** cmdlet can use the VMware VMotion feature to move a virtual machine from one ESX host to another only if both ESX servers are in the same Datacenter container on the vCenter Server.

### Example 5: Move a highly available virtual machine between nodes in a host cluster by using Hyper-V live migration
```
PS C:\>$VM = Get-SCVirtualMachine -Name "HAVM05" | Where-Object {$_.VMHost.Name -Eq "VMHVHostNode05A.Contoso.com"}
PS C:\> $VMHost = Get-SCVMHost | Where-Object {$_.Name -Eq "VMHVHostNode05B.Contoso.com"}
PS C:\> Move-SCVirtualMachine -VM $VM -VMHost $VMHost -Path "D:\VMs\"
```

The first command gets the virtual machine object named HAVM05 on VMHVHostNode05A, and then stores that object in the $VM variable.
In this example, HAVM05 is a highly available virtual machine.
VMHVHostNode05A and VMHVHostNode05B are nodes in a Hyper-V host cluster.

The second command gets the host object named VMHVHostNode05B, and then stores that object in the $VMHost variable.

The final command uses live migration to move the virtual machine from VMHVHostNode05A to VMHVHostNode05B.

### Example 6: Move a running virtual machine on a Hyper-V host to a new location on the same host
```
PS C:\>$MoveVhdPath = "E:\VHDs" 
PS C:\> $VM = Get-SCVirtualMachine "VM06" 
PS C:\> $VMHost = Get-SCVMHost "VMHost06"
PS C:\> $HostPath = "E:\VirtualMachinePath" 
PS C:\> $JobGroupID = [System.Guid]::NewGuid().ToString()
PS C:\> Move-SCVirtualHardDisk -IDE -Bus 1 -Lun 1 -Path $MoveVhdPath -JobGroup $JobGroupID
PS C:\> Move-SCVirtualMachine -VM $VM -VMHost $VMHost -Path $HostPath -JobGroup $JobGroupID
```

The first command stores the string E:\VHDs in $MoveVhdPath.
This is the path of which to move the virtual hard disk of the virtual machine.

The second command gets the virtual machine object named VM06, and then stores that object the $VM variable.

The third command gets the host object named VMHost06, and then stores that object in the $VMHost variable.
In this example, VMHost06 is a Hyper-V host.

The fourth command stores the string E:\VirtualMachinePath in the $HostPath variable.
This is the path of which to move VM06.

The fifth command creates a new GUID string and stores it in the $JobGroupID variable.
This GUID is a job group ID that functions as an identifier that groups subsequent commands that include this identifier into a single job group.

The sixth command sets the virtual hard disk path of the value stored in $MoveVhdPath and it connects the virtual hard disk to Bus 1 and LUN 1 on the virtual IDE controller on the virtual machine.
This command specifies the *JobGroup* parameter so that it does not actually run until **Move-SCVirtualMachine** triggers the running of any commands in the job group list.

The last command moves VM06 to E:\VirtualMachinePath on the same host.
The cmdlet runs Move-SCVirtualHardDisk as part of $JobGroupID.
The command moves the virtual hard disk of the virtual machine to E:\VHDs.

## PARAMETERS

### -BlockLiveMigrationIfHostBusy
Indicates that the cmdlet blocks retrying a Hyper-V live migration if the migration failed because the source host or the destination host is already participating in another live migration.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: BlockLMIfHostBusy

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiscardSavedState
Indicates that this cmdlet deletes the saved state associated with a virtual machine or service.

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

### -HighlyAvailable
Specifies whether to place a virtual machine on a Hyper-V host that is part of a host cluster.

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

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

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
Specifies the name of a variable for job progress.

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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the Get-SCUserRole cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### -Path
Specifies the path of the moved virtual machine.

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

### -ReplicationGroup
Specifies a replication group.

```yaml
Type: ReplicationGroup
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

### -StartVMOnTarget
Specifies that a virtual machine starts as soon as this cmdlet moves it to its destination host.

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

### -UseCluster
Indicates that this cmdlet uses Cluster Migration for the transfer of a virtual machine that is in a saved state to a host, even if the cluster supports Hyper-V live migration.

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

### -UseDiffDiskOptimization
Indicates that the cmdlet uses differencing disk optimization.

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

### -UseLAN
Indicates that this cmdlet uses transfer over the LAN even if a faster transfer mechanism is available.

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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
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

### VirtualMachine
This cmdlet returns a **VirtualMachine** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Move-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualHardDisk.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Register-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md)

[Reset-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Reset-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Save-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Save-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md)

