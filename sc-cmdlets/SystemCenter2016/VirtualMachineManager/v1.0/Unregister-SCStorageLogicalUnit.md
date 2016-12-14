---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageLogicalUnit.md
schema: 2.0.0
ms.assetid: AF1539CE-6CC0-4208-8ACA-2555836C3882
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Unregister-SCStorageLogicalUnit.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Unregister-SCStorageLogicalUnit.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Unregister-SCStorageLogicalUnit.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Unregister-SCStorageLogicalUnit

## SYNOPSIS
Disassociates a logical unit from a host.

## SYNTAX

### RegisterToClusterJobGroup (Default)
```
Unregister-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> -JobGroup <Guid>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToHost
```
Unregister-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> [-JobGroup <Guid>] -VMHost <Host>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### UnregisterFromVM
```
Unregister-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> [-JobGroup <Guid>] -VM <VM[]>
 [-RemoveVM <VM>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### UnregisterFromStorageFileServer
```
Unregister-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> [-JobGroup <Guid>]
 -StorageFileServer <StorageFileServer> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### RegisterToCluster
```
Unregister-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> -VMHostCluster <HostCluster>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToInitiators
```
Unregister-SCStorageLogicalUnit [-StorageLogicalUnit] <StorageLogicalUnit[]> -StorageInitiators <String[]>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-SCStorageLogicalUnit** cmdlet disassociates a logical unit from a host.

## EXAMPLES

### Example 1: Hide a logical unit from a host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $LU = Get-SCStorageLogicalUnit -Name "LUN01"
PS C:\> Unregister-SCStorageLogicalUnit -StorageLogicalUnit $LU -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the storage logical unit object named LUN01 and stores the object in the $LU variable.

The last command unregisters LUN01 from VMHost01.

## PARAMETERS

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
Parameter Sets: RegisterToHost, UnregisterFromVM, UnregisterFromStorageFileServer
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

### -RemoveVM
Specifies a virtual machine object to remove.

```yaml
Type: VM
Parameter Sets: UnregisterFromVM
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

### -StorageFileServer
Specifies a storage file server object.

```yaml
Type: StorageFileServer
Parameter Sets: UnregisterFromStorageFileServer
Aliases: 

Required: True
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
Specifies a storage logical unit object.

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
Parameter Sets: UnregisterFromVM
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

## NOTES

## RELATED LINKS

[Get-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageLogicalUnit.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHost.md)

[New-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageLogicalUnit.md)

[Register-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/v1.0/Register-SCStorageLogicalUnit.md)

[Remove-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageLogicalUnit.md)

[Set-SCStorageLogicalUnit](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageLogicalUnit.md)

