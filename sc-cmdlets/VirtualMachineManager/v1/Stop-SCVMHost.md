---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: 4833FC55-072C-45A4-938B-7452E3A91D15
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Stop-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Stop-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Stop-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Stop-SCVMHost

## SYNOPSIS
Stops a host managed by VMM.

## SYNTAX

```
Stop-SCVMHost [-VMHost] <Host> [-UseOutOfBandChannel] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SCVMHost** cmdlet stops a host managed by Virtual Machine Manager (VMM) by issuing a Power Off command.

There are two methods by which you can stop a host: in-band and out-of-band (OOB).
The default parameter set uses the in-band method to shut down the host.
To use the OOB method, the host must be configured for OOB management.
For information about configuring the Baseboard Management Controller (BMC) settings for a host, type `Get-Help Set-SCVMHost -Detailed`.

## EXAMPLES

### Example 1: Power-off a specified host using in-band management
```
PS C:\>Get-SCVMHost -ComputerName "NewHost01" | Stop-SCVMHost -Confirm
```

This command gets the host object named NewHost01 and powers off the host.
The command prompts you to confirm the action before proceeding.

### Example 2: Power-off a specified host using out-of-band management
```
PS C:\>Get-SCVMHost -ComputerName "NewHost01" | Stop-SCVMHost -UseOutOfBandChannel -Confirm
```

This command gets the host object named NewHost01 and powers off the host using OOB management.
The command prompts you for confirmation before proceeding.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -UseOutOfBandChannel
Indicates that the out-of-band management channel should be used to perform the operation.
You should use this parameter only when the computer is unresponsive.

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

For more information about each type of host, see the Add-SCVMHost cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Host
This cmdlet returns a **Host** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:VirtualMachineManager/v1/Add-SCVMHost.md)

[Disable-SCVMHost](xref:VirtualMachineManager/v1/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:VirtualMachineManager/v1/Enable-SCVMHost.md)

[Get-SCCertificate](xref:VirtualMachineManager/v1/Get-SCCertificate.md)

[Get-SCVMHost](xref:VirtualMachineManager/v1/Get-SCVMHost.md)

[Move-SCVMHost](xref:VirtualMachineManager/v1/Move-SCVMHost.md)

[Read-SCVMHost](xref:VirtualMachineManager/v1/Read-SCVMHost.md)

[Register-SCVMHost](xref:VirtualMachineManager/v1/Register-SCVMHost.md)

[Remove-SCVMHost](xref:VirtualMachineManager/v1/Remove-SCVMHost.md)

[Restart-SCVMHost](xref:VirtualMachineManager/v1/Restart-SCVMHost.md)

[Set-SCVMHost](xref:VirtualMachineManager/v1/Set-SCVMHost.md)
