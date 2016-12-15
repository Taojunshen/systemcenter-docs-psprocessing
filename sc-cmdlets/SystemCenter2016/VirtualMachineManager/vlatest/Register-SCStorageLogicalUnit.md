---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageLogicalUnit.md
schema: 2.0.0
ms.assetid: 847E31BB-40D3-47A5-A195-7E43ECA10566
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageLogicalUnit.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageLogicalUnit.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageLogicalUnit.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Register-SCStorageLogicalUnit

## SYNOPSIS
Associates a logical unit with a host.

## SYNTAX

### RegisterToClusterJobGroup (Default)
```
Register-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> -JobGroup <Guid>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToHost
```
Register-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> [-JobGroup <Guid>] -VMHost <Host>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToVM
```
Register-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> [-JobGroup <Guid>] -VM <VM[]>
 [-AddVM <VM>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToStorageFileServer
```
Register-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> [-JobGroup <Guid>]
 -StorageFileServer <StorageFileServer> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### RegisterToInitiators
```
Register-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> [-StorageEndpoints <String[]>]
 [-StorageGroupName <String>] -StorageInitiators <String[]> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToCluster
```
Register-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> -VMHostCluster <HostCluster>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Register-SCStorageLogicalUnit** cmdlet associates a logical unit with a virtual machine host.
The logical unit appears in the operating system as a disk.

## EXAMPLES

### Example 1: Register a logical unit with a host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $LU = Get-SCStorageLogicalUnit -Name "LUN01"
PS C:\> Register-SCStorageLogicalUnit -StorageLogicalUnit $LU -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the storage logical unit object named LUN01 and stores the object in the $LU variable.

The last command registers LUN01 with VMHost01.

## PARAMETERS

### -AddVM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: RegisterToVM
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
Parameter Sets: RegisterToClusterJobGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: RegisterToHost, RegisterToVM, RegisterToStorageFileServer
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

### -StorageEndpoints
Specifies an array of storage endpoints.

```yaml
Type: String[]
Parameter Sets: RegisterToInitiators
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
Parameter Sets: RegisterToStorageFileServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageGroupName
Specifies the name of a storage group.

```yaml
Type: String
Parameter Sets: RegisterToInitiators
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageInitiators
Specifies an array of storage initiators.

```yaml
Type: String[]
Parameter Sets: RegisterToInitiators
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageLogicalUnit
Specifies an array of storage logical unit objects.

```yaml
Type: StorageLogicalUnit[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machine objects.

```yaml
Type: VM[]
Parameter Sets: RegisterToVM
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

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
Parameter Sets: RegisterToHost
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
Parameter Sets: RegisterToCluster
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

### StorageDisk
This cmdlet returns a **StorageDisk** object.

## NOTES

## RELATED LINKS

[Get-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageLogicalUnit.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[New-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageLogicalUnit.md)

[Remove-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageLogicalUnit.md)

[Set-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageLogicalUnit.md)

[Unregister-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageLogicalUnit.md)

