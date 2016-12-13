---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: 6C63CB7A-2436-4839-8EC5-8242DF2C454B
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCVMHost

## SYNOPSIS
Refreshes virtual machine host properties in the VMM Console.

## SYNTAX

### DefaultRefresh (Default)
```
Read-SCVMHost [-VMHost] <Host> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### OutOfBandRefresh
```
Read-SCVMHost [-VMHost] <Host> [-RefreshOutOfBandProperties] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCVMHost** cmdlet refreshes the properties of a virtual machine host so that the Virtual Machine Manager (VMM) console displays updated information about the host.

Host properties that this cmdlet updates include: 

- Name
- Operating system
- Status (such as Responding)
- Host volumes (typically, addition or removal of drive letters, mount points, as well as used and available space)
- Network adapters (addition or removal)

## EXAMPLES

### Example 1: Refresh information about a specific host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01" 
PS C:\> Read-SCVMHost -VMHost $VMHost
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command refreshes the properties for VMHost01 so that current information about this host will appear in the VMM Console.

### Example 2: Refresh information about all hosts
```
PS C:\>Get-SCVMHost -VMMServer "VMMServer01.Contoso.com" | Read-SCVMHost
```

This command refreshes information about all hosts managed by VMMServer01 so that current information about each host will appear in the VMM Console.

### Example 3: Refresh information about a given host through its OOB channel
```
PS C:\>Get-SCVMHost -ComputerName "VMHost02" | Read-SCVMHost -RefreshOutOfBandProperties
```

This command refreshes information about host VMHost02 using its out-of-band interface so that current information about the host appears in the VMM console.

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

### -RefreshOutOfBandProperties
Refreshes available computer hardware properties through the out-of-band baseboard management controller (BMC).
This process is different from the regular host refreshing logic, because the host refresher goes through the VMM agent inside the operating system (in-band).
The properties that are refreshed through BMC are different from those in the in-band refresher.

```yaml
Type: SwitchParameter
Parameter Sets: OutOfBandRefresh
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

[Add-SCVMHost](xref:VirtualMachineManager/v1/Add-SCVMHost.md)

[Disable-SCVMHost](xref:VirtualMachineManager/v1/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:VirtualMachineManager/v1/Enable-SCVMHost.md)

[Get-SCVMHost](xref:VirtualMachineManager/v1/Get-SCVMHost.md)

[Move-SCVMHost](xref:VirtualMachineManager/v1/Move-SCVMHost.md)

[Register-SCVMHost](xref:VirtualMachineManager/v1/Register-SCVMHost.md)

[Remove-SCVMHost](xref:VirtualMachineManager/v1/Remove-SCVMHost.md)

[Repair-SCVMHost](xref:VirtualMachineManager/v1/Repair-SCVMHost.md)

[Restart-SCVMHost](xref:VirtualMachineManager/v1/Restart-SCVMHost.md)

[Set-SCVMHost](xref:VirtualMachineManager/v1/Set-SCVMHost.md)

[Start-SCVMHost](xref:VirtualMachineManager/v1/Start-SCVMHost.md)

[Stop-SCVMHost](xref:VirtualMachineManager/v1/Stop-SCVMHost.md)

