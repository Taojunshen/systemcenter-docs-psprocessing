---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: F160A8F1-193F-42A4-A9CC-EB7805FA3AC3
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCVirtualMachine

## SYNOPSIS
Refreshes the properties of a virtual machine so that the VMM console displays updated information about the virtual machine.

## SYNTAX

### FullRefreshSingleVm (Default)
```
Read-SCVirtualMachine [-VM] <VM> [-Force] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### LightRefreshVmsOnHost
```
Read-SCVirtualMachine [-VMHost] <Host> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCVirtualMachine** cmdlet updates the properties of a virtual machine so that the Virtual Machine Manager (VMM) console displays updated information about the virtual machine.
The updated properties include **Name**, **Status**, **Host**, **Owner**, **CPUAverage**, **Service**, **OperatingSystem**, and other properties.

## EXAMPLES

### Example 1: Refresh information about a specific virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Read-SCVirtualMachine -VM $VM
```

The first command gets the virtual machine object named VM01, and then stores that object in the $VM variable.

The second command updates the properties of the virtual machine stored in $VM.
After this command finishes successfully, it displays current information about this virtual machine.

### Example 2: Refresh all virtual machines on hosts whose name matches the specified string
```
PS C:\>$VMs = Get-SCVirtualMachine -VMMServer "VMMServer01.Contoso.com" | Where-Object { $_.VMHost.Name -Match "VMM" }
PS C:\> $VMs | Read-SCVirtualMachine
```

The first command gets all virtual machine objects from VMMServer01 deployed on hosts whose name contains the string VMM, and then stores those virtual machine objects in the $VMs array.

The second command updates the properties of each virtual machine object stored in $VMs.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: FullRefreshSingleVm
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
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: FullRefreshSingleVm
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
Parameter Sets: LightRefreshVmsOnHost
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

## NOTES
* This cmdlet requires a virtual machine object, which can be retrieved by using the Get-SCVirtualMachine cmdlet.

## RELATED LINKS

[Add-SCVMHost](xref:VirtualMachineManager/v1/Add-SCVMHost.md)

[Get-SCUserRole](xref:VirtualMachineManager/v1/Get-SCUserRole.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Move-SCVirtualMachine](xref:VirtualMachineManager/v1/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:VirtualMachineManager/v1/New-SCVirtualMachine.md)

[Register-SCVirtualMachine](xref:VirtualMachineManager/v1/Register-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:VirtualMachineManager/v1/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:VirtualMachineManager/v1/Repair-SCVirtualMachine.md)

[Reset-SCVirtualMachine](xref:VirtualMachineManager/v1/Reset-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:VirtualMachineManager/v1/Resume-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:VirtualMachineManager/v1/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:VirtualMachineManager/v1/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:VirtualMachineManager/v1/Stop-SCVirtualMachine.md)

[Suspend-SCVirtualMachine](xref:VirtualMachineManager/v1/Suspend-SCVirtualMachine.md)
