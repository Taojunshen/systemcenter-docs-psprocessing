---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8EFED3B8-DC53-4E43-8CC4-7CFB7A3360C7
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Join-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Join-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Join-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Join-SCVirtualMachine

## SYNOPSIS
Re-associates an orphaned virtual machine to its service or virtual machine role.

## SYNTAX

### ServiceComputerTierParameterSet
```
Join-SCVirtualMachine [-VM] <VM> -ComputerTier <ComputerTier> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMRoleParameterSet
```
Join-SCVirtualMachine [-VM] <VM> -VMRole <CloudVmRole> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Join-SCVirtualMachine** cmdlet re-associates an orphaned virtual machine to its service or virtual machine role.

When a host or cluster is removed from Virtual Machine Manager (VMM), any virtual machines belonging to a service or a virtual machine role deployed on the host remain functional.
However, on adding the host or cluster back to VMM, the virtual machines become orphaned in the sense that they no longer have any association with their service or virtual machine role.

You can use this cmdlet to restore the association between a virtual machine and its service or virtual machine role.
The **Join-SCVirtualMachine** cmdlet runs a re-associate task on VMM that performs a set of validations that help confirm the compatibility of the virtual machine with the service template.

When the cmdlet validates the compatibility of the virtual machine with the computer tier template, database-only operations are performed, and no adjustments are made to the virtual machine.
It is assumed that the virtual machine is running and that all of the guest applications and services running on it are intact.

The computer tier to which you want to join the virtual machine must be running below its maximum instance count.
The upgrade domain for the join operation is similar to a scale-out.

For best results, use this cmdlet with a virtual machine that was originally part of a service or virtual machine role deployment and was not modified.

## EXAMPLES

### Example 1: Join an orphaned virtual machine to a service tier
```
PS C:\> $VM = Get-SCVirtualMachine -Name "PS-Web-001" 
PS C:\> $CT = Get-SCComputerTier -Name "MyService-WebTier" 
PS C:\> Join-SCVirtualMachine -VM $VM -ComputerTier $CT
```

The first command gets the virtual machine named PS-Web-001, and then stores it in the $VM variable.

The second command gets the computer tier named MyService-WebTier, and then stores it in the $CT variable.

The last command joins the virtual machine in $VM to the computer tier in $CT.

### Example 2: Join an orphaned virtual machine to a virtual machine role
```
PS C:\> $VM = Get-SCVirtualMachine -Name "PS-Web-001" 
PS C:\> $VmRole = Get-CloudResource -Name "ContosoShop" 
PS C:\> Join-SCVirtualMachine -VM $VM -VMRole $VmRole
```

The first command gets the virtual machine named PS-Web-001, and then stores it in the $VM variable.

The second command gets the cloud resource named ContosoShop, and then stores it in the $VmRole variable.

The last command joins the virtual machine in $VM to the role in $VMRole.

## PARAMETERS

### -ComputerTier
Specifies a **ComputerTier** object.

```yaml
Type: ComputerTier
Parameter Sets: ServiceComputerTierParameterSet
Aliases: 

Required: True
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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -VM
Specifies a **VM** object.

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

### -VMRole
Specifies a **CloudVMRole** object.

```yaml
Type: CloudVmRole
Parameter Sets: VMRoleParameterSet
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

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Register-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md)

[Reset-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Reset-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Save-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Save-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

