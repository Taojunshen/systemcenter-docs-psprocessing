---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: 6DE3D33F-2D2F-4795-8831-CC5E8BB11673
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCVMHost

## SYNOPSIS
Starts a stopped host managed by VMM by using out-of-band management.

## SYNTAX

```
Start-SCVMHost [-VMHost] <Host> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCVMHost** cmdlet starts a stopped host managed by Virtual Machine Manager by using out-of-band management.
Before using this cmdlet, a host must be configured for out-of-band (OOB) management.
For information about configuring the Baseboard Management Controller (BMC) settings for a host, type `Get-Help Set-SCVMHost -Detailed`.

## EXAMPLES

### Example 1: Power on a specified host
```
PS C:\>Get-SCVMHost -ComputerName "NewHost01" | Start-SCVMHost
```

This command gets the host object named NewHost01 and starts the host using OOB management.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Host
This cmdlet returns a **Host** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCVMHost.md)

[Get-SCCertificate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCertificate.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCVMHost.md)

