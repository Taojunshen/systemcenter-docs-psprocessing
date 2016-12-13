---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCHardwareProfile.md
schema: 2.0.0
ms.assetid: 2F500C47-518C-44EC-AF87-FF51C7854166
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualCOMPort.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualCOMPort.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVirtualCOMPort.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualCOMPort

## SYNOPSIS
Gets a virtual  COM port from a virtual machine, a virtual machine template, or a hardware profile.

## SYNTAX

### All
```
Get-SCVirtualCOMPort [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### HardwareProfile
```
Get-SCVirtualCOMPort -HardwareProfile <HardwareProfile> [<CommonParameters>]
```

### VM
```
Get-SCVirtualCOMPort -VM <VM> [<CommonParameters>]
```

### Template
```
Get-SCVirtualCOMPort -VMTemplate <Template> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualCOMPort** cmdlet gets virtual communication (COM) port objects.
This cmdlet gets one or both COM ports from a virtual machine object, a virtual machine template object, or a hardware profile object that Virtual Machine Manager (VMM) manages.

A virtual COM port can connect to a physical port on a virtual machine host server, to a text file, or to a named pipe.
Each virtual machine, virtual machine template, and hardware profile contains exactly two COM ports.

## EXAMPLES

### Example 1: Get COM ports for a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Get-SCVirtualCOMPort -VM $VM
```

The first command gets the virtual machine named VM01, and then stores that object in the $VM variable.

The second command gets the virtual COM port objects on VM01, and displays information about these ports.

### Example 2: Get COM ports for a template
```
PS C:\>$VMTemplate = Get-SCVMTemplate | where { $_.Name -eq "VMTemplate01" }
PS C:\> Get-SCVirtualCOMPort -VMTemplate $VMTemplate
```

The first command gets the virtual machine template named VMTemplate01, and then stores that object in the $VMTemplate variable.

The second command gets the virtual COM port objects for VMTemplate01, and displays information about these ports.

### Example 3: Get COM ports for a hardware profile
```
PS C:\>$HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> Get-SCVirtualCOMPort -HardwareProfile $HWProfile
```

The first command gets the hardware profile named NewHWProfile01, and then stores that object in the $HWProfile variable.

The second command gets the virtual COM port objects for NewHWProfile01, and displays information about these ports.

## PARAMETERS

### -All
Indicates that this cmdlet gets a full list of subordinate COM ports independent of the parent object.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: HardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine for which this cmdlet gets virtual COM ports.
To obtain a virtual machine object, use the Get-SCVirtualMachine cmdlet.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template that is used to create virtual machines for which this cmdlet gets virtual COM ports.
To obtain a VMM template object, use the Get-SCVMTemplate cmdlet.

```yaml
Type: Template
Parameter Sets: Template
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualCOMPort
This cmdlet returns a **VirtualCOMPort** object.

## NOTES

## RELATED LINKS

[Get-SCHardwareProfile](xref:VirtualMachineManager/v1/Get-SCHardwareProfile.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Get-SCVMTemplate](xref:VirtualMachineManager/v1/Get-SCVMTemplate.md)

[Set-SCVirtualCOMPort](xref:VirtualMachineManager/v1/Set-SCVirtualCOMPort.md)

