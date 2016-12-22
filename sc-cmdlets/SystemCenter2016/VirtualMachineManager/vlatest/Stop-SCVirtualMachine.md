---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C4A19367-DB20-4F11-A2C9-A6BB3960B349
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Stop-SCVirtualMachine

## SYNOPSIS
Stops virtual machines managed by VMM.

## SYNTAX

### SingleVM (Default)
```
Stop-SCVirtualMachine [-VM] <VM> [-Shutdown] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### CorrespondsToVMM2008SaveStateVM
```
Stop-SCVirtualMachine [-VM] <VM> [-SaveState] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### CorrespondsToVMM2008DiscardSavedStateVM
```
Stop-SCVirtualMachine [-VM] <VM> [-DiscardSavedState] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### CorrespondsToVMM2008StopVM
```
Stop-SCVirtualMachine [-VM] <VM> [-Force] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SCVirtualMachine** cmdlet stops one or more running virtual machines on hosts managed by Virtual Machine Manager (VMM) and returns the virtual machine object in a stopped state.

This cmdlet stops a virtual machine just like shutting down the operating system on a computer.
If you specify the *Force* parameter, this cmdlet stops a virtual machine just like turning off a computer.

To resume a stopped virtual machine, use the Start-SCVirtualMachine cmdlet.

## EXAMPLES

### Example 1: Stop a specified virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Stop-SCVirtualMachine -VM $VM
```

The first command gets the virtual machine object named VM01, and then stores that object in the $VM variable.

The second command stops the virtual machine stored in $VM, and displays information about the stopped object.

### Example 2: Stop multiple virtual machines
```
PS C:\> $VMs = Get-SCVirtualMachine | where { $_.Name -match "VM" -and $_.Status -eq "Running" }
PS C:\> $VMs | Stop-SCVirtualMachine
```

The first command gets all virtual machine objects whose name contains the string VMM and whose current status is Running.
The command then stores those objects in the $VMs array.

The second command passes each virtual machine object stored in $VMs to the current cmdlet, which stops each virtual machine.
The command displays information about the stopped virtual machines.

## PARAMETERS

### -DiscardSavedState
Indicates that this cmdlet deletes the saved state associated with a virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: CorrespondsToVMM2008DiscardSavedStateVM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Indicates that this cmdlet stops a virtual machine just like turning off a computer.

```yaml
Type: SwitchParameter
Parameter Sets: CorrespondsToVMM2008StopVM
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

### -SaveState
Indicates that this cmdlet saves the state of a virtual machine.

```yaml
Type: SwitchParameter
Parameter Sets: CorrespondsToVMM2008SaveStateVM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Shutdown
Indicates that this cmdlet shuts down a virtual machine.
This cmdlet uses the operating system to shut the virtual machine down gracefully.

```yaml
Type: SwitchParameter
Parameter Sets: SingleVM
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualMachine
This cmdlet returns a **VirtualMachine** object.

## NOTES
* This cmdlet requires a virtual machine object, which can be retrieved by using the **Get-SCVirtualMachine** cmdlet.

## RELATED LINKS

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Move-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualMachine.md)

[Register-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualMachine.md)

[Reset-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Reset-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCVirtualMachine.md)

