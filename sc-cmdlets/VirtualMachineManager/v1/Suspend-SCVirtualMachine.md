---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCUserRole.md
schema: 2.0.0
ms.assetid: A1079226-FC22-48C4-A67E-219E0B138F35
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Suspend-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Suspend-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Suspend-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Suspend-SCVirtualMachine

## SYNOPSIS
Suspends a virtual machine managed by VMM.

## SYNTAX

```
Suspend-SCVirtualMachine [-VM] <VM> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Suspend-SCVirtualMachine** cmdlet suspends one or more virtual machines deployed on hosts managed by Virtual Machine Manager (VMM).
This cmdlet pauses activity on a virtual machine, and returns an object that represents that virtual machine in a paused state.

To resume running a suspended virtual machine, use the Resume-SCVirtualMachinecmdlet.

## EXAMPLES

### Example 1: Suspend a specified virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Suspend-SCVirtualMachine -VM $VM
```

The first command gets the virtual machine object named VM01, and then stores that object in the $VM variable.

The second command pauses the virtual machine stored in $VM, and displays information about the paused object.

## PARAMETERS

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

## NOTES
* This cmdlet requires a virtual machine object, which can be retrieved by using the Get-SCVirtualMachine cmdlet.

## RELATED LINKS

[Get-SCUserRole](xref:VirtualMachineManager/v1/Get-SCUserRole.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Move-SCVirtualMachine](xref:VirtualMachineManager/v1/Move-SCVirtualMachine.md)

[New-SCVirtualMachine](xref:VirtualMachineManager/v1/New-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:VirtualMachineManager/v1/Read-SCVirtualMachine.md)

[Register-SCVirtualMachine](xref:VirtualMachineManager/v1/Register-SCVirtualMachine.md)

[Remove-SCVirtualMachine](xref:VirtualMachineManager/v1/Remove-SCVirtualMachine.md)

[Repair-SCVirtualMachine](xref:VirtualMachineManager/v1/Repair-SCVirtualMachine.md)

[Reset-SCVirtualMachine](xref:VirtualMachineManager/v1/Reset-SCVirtualMachine.md)

[Resume-SCVirtualMachine](xref:VirtualMachineManager/v1/Resume-SCVirtualMachine.md)

[Set-SCVirtualMachine](xref:VirtualMachineManager/v1/Set-SCVirtualMachine.md)

[Start-SCVirtualMachine](xref:VirtualMachineManager/v1/Start-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:VirtualMachineManager/v1/Stop-SCVirtualMachine.md)

