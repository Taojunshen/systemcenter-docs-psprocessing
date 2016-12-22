---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4E0B6739-E7EC-489D-A3D7-BDACF07CB1D5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Move-SCVMHost

## SYNOPSIS
Moves a virtual machine host managed by VMM from one host group to another.

## SYNTAX

```
Move-SCVMHost [-VMHost] <Host> -ParentHostGroup <HostGroup> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-SCVMHost** cmdlet moves one or more virtual machine hosts managed by Virtual Machine Manager (VMM) from its current host group to a new parent host group.
Before you can move a host, its new parent host group must exist.

If the host is a computer that is managed by members of a Self-Service User or Delegated Administrator user role, moving the host from one host group to another might affect the roles that have access to the host or to virtual machines on that host.

## EXAMPLES

### Example 1: Move a single host to a new parent host group
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $NewHG = Get-SCVMHostGroup -Name "NewHostGroup01" 
PS C:\> Move-SCVMHost -VMHost $VMHost -ParentHostGroup $NewHG
```

The first command gets the host named VMHost01 and stores it in the $VMHost variable.

The second command gets the host group object named NewHostGroup and stores it in the $NewHG variable.

The last command moves the host stored in the $VMHost variable (VMHost01) to the host group stored in the $NewHG variable (NewHostGroup).

### Example 2: Move all hosts to a new parent host group
```
PS C:\> $AllHosts = Get-SCVMHost  
PS C:\> $NewHG = Get-SCVMHostGroup -Name "NewHostGroup02"
PS C:\> $AllHosts | Move-SCVMHost -ParentHostGroup $NewHG
```

The first command gets all host objects and stores them in the $AllHosts array.

The second command gets the host group named NewHostGroup02 and stores it in the $NewHG variable.

The last command moves each host object in the $AllHosts array to the new parent host group stored in the $NewHG variable (NewHostGroup02).

### Example 3: Move a set of hosts from one host group to a new parent host group
```
PS C:\> $SpecificHosts = Get-SCVMHost | where { $_.VMHostGroup -like "*OldGroup*" }
PS C:\> $NewHG = Get-SCVMHostGroup -Name "NewHostGroup03" 
PS C:\> $SpecificHosts | Move-SCVMHost -ParentHostGroup $NewHG
```

The first command gets all host objects whose host group contains the string "OldGroup" and stores them in the $SpecificHosts variable.

The second command gets the host group named NewHostGroup03 and stores it in the $NewHG variable.

The last command moves each host object stored in $SpecificHosts to the host group stored in the $NewHG variable (NewHostGroup03).

## PARAMETERS

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

### -ParentHostGroup
Specifies the parent host group that contains one or more hosts, host groups, or host clusters.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: ParentVMHostGroup

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

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Host
This cmdlet returns a **Host** object.

## NOTES
* Requires a VMM host object, which can be retrieved by using the **Get-SCVMHost** cmdlet.

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHost.md)

[Repair-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVMHost.md)

