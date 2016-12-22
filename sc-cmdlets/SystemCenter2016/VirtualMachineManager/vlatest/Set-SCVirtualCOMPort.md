---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 72562DF6-7CED-423A-8C44-6AD911A4CC9A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualCOMPort.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualCOMPort.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualCOMPort.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualCOMPort

## SYNOPSIS
Modifies properties of a virtual COM port for a virtual machine, virtual machine template, or hardware profile.

## SYNTAX

### NewParentJobGroupTextFile
```
Set-SCVirtualCOMPort [-VMMServer <ServerConnection>] -GuestPort <Byte> -TextFile <String> -JobGroup <Guid>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewParentJobGroupNoAttach
```
Set-SCVirtualCOMPort [-VMMServer <ServerConnection>] -GuestPort <Byte> [-NoAttach] -JobGroup <Guid>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewParentJobGroupHostPort
```
Set-SCVirtualCOMPort [-VMMServer <ServerConnection>] -GuestPort <Byte> -VMHostCOMPort <Byte>
 [-WaitForModem <Boolean>] -JobGroup <Guid> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### NewParentJobGroupNamedPipe
```
Set-SCVirtualCOMPort [-VMMServer <ServerConnection>] -GuestPort <Byte> -NamedPipe <String> -JobGroup <Guid>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NoAttach
```
Set-SCVirtualCOMPort [-VirtualCOMPort] <VirtualCOMPort> [-NoAttach] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### TextFile
```
Set-SCVirtualCOMPort [-VirtualCOMPort] <VirtualCOMPort> -TextFile <String> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NamedPipe
```
Set-SCVirtualCOMPort [-VirtualCOMPort] <VirtualCOMPort> -NamedPipe <String> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VMHostCOMPort
```
Set-SCVirtualCOMPort [-VirtualCOMPort] <VirtualCOMPort> -VMHostCOMPort <Byte> [-WaitForModem <Boolean>]
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualCOMPort** cmdlet modifies one or more properties of a virtual communications (COM) port.
A virtual COM port is part of a virtual machine, virtual machine template, or hardware profile used in a Virtual Machine Manager (VMM) environment.
Specify a COM port by using the *VirtualCOMPort* parameter or specify a virtual COM port ID for the *GuestPort* parameter.
Valid values for *GuestPort* are zero (0) and one (1).

This cmdlet can connect a virtual COM port to a physical COM port, to a text file, or to a named pipe.
This cmdlet can disconnect a virtual COM port.
If you connect a virtual COM port on a virtual machine to a physical COM port on its host, the virtual machine can use the physical COM port for input and output.
The host types support the following virtual COM port connection types: 

- Hyper-V.
Connects to a named pipe only. 
- VMware ESX.
Connects to a physical COM port, text file, or named pipe. 
- Citrix XenServer. 
Not Supported.

The *WaitForModem* parameter specifies whether a virtual COM port on a virtual machine connects immediately to a physical COM port on the host when the virtual machine starts.

If you specify a value of $True for *WaitForModem*, the virtual machine attempts to connect to the physical COM port on the host only if a program that runs on the virtual machine sends a modem command to the physical COM port.
If the COM port on the host is already connected, the virtual machine cannot connect to it.
If the virtual machine successfully connects to the physical COM port, the virtual machine later releases the physical COM port back to the host operating system if the program on the virtual machine that uses the COM port stops using the COM port.

If you specify a value of $False for *WaitForModem*, the virtual machine attempts to connect to the physical COM port on the host as soon as the virtual machine starts.
If the COM port on the host is already captured, the virtual machine cannot connect to it.
This is the same behavior as for a value of $True.
If the virtual machine successfully connects to the physical COM port, the virtual machine does not release the physical COM port back to the host operating system until the virtual machine is shut down.

## EXAMPLES

### Example 1: Connect a virtual COM port to a named pipe
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $COM1 = Get-SCVirtualCOMPort -VM $VM | where {$_.Name -eq "COM1"}
PS C:\> Set-SCVirtualCOMPort -VirtualCOMPort $COM1 -NamedPipe "\\Contoso\Pipe\PipeName"
```

The first command gets the virtual machine named VM02, and then stores that object in the $VM variable.

The second command gets the virtual COM port named COM1 from VM02, and then stores that object in the $COM1 variable.

The last command connects the virtual COM port in $COM1 to the named pipe \\\\Contoso\Pipe\PipeName.

### Example 2: Disconnect a virtual COM port
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM04"
PS C:\> $COM1 = Get-SCVirtualCOMPort -VM $VM | where {$_.Name -eq "COM1"}
PS C:\> Set-SCVirtualCOMPort -VirtualCOMPort $COM1 -NoAttach
```

The first command gets the virtual machine named VM04, and then stores that object in the $VM variable.

The second command gets the virtual COM port on VM04 named COM1, and then stores that object in the $COM1 variable.

The last command specifies the *NoAttach* parameter.
This causes the command to disconnect the virtual COM port in $COM1.
You can use this command to disconnect a virtual COM port that is currently connected to a physical COM port on a host, to a named pipe, or to a text file.

## PARAMETERS

### -GuestPort
Specifies the ID of a virtual COM port on a virtual machine.
Valid values are: 0 and 1.

```yaml
Type: Byte
Parameter Sets: NewParentJobGroupTextFile, NewParentJobGroupNoAttach, NewParentJobGroupHostPort, NewParentJobGroupNamedPipe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: NewParentJobGroupTextFile, NewParentJobGroupNoAttach, NewParentJobGroupHostPort, NewParentJobGroupNamedPipe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: NoAttach, TextFile, NamedPipe, VMHostCOMPort
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

### -NamedPipe
Specifies a named pipe to which a virtual COM port connects.
Typical uses include connecting a virtual machine to a debugging program on the host.
You can also create a virtual null modem cable between two virtual machines.
Specify a pipe in the following format: \\\\.\ComputerName\Pipe\PipeName

```yaml
Type: String
Parameter Sets: NewParentJobGroupNamedPipe, NamedPipe
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAttach
Indicates that this cmdlet specifies that no physical COM port on a host, named pipe, or file connect to a virtual COM port.
If you specify this parameter, the cmdlet disconnects a virtual COM port that is already connected to a physical COM port, to a named pipe, or to a text file.

```yaml
Type: SwitchParameter
Parameter Sets: NewParentJobGroupNoAttach, NoAttach
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization (PRO) tip that triggered this action.
This allows for auditing of PRO tips.

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

### -TextFile
Specifies a text file on the host to which the virtual COM port connects.
The virtual machine sends output from the virtual COM port the text file that this parameter specifies.
The text file can be on any valid disk drive on the host.

```yaml
Type: String
Parameter Sets: NewParentJobGroupTextFile, TextFile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostCOMPort
Specifies a physical COM port object on a host server to which the virtual machine can connect a virtual COM port.

```yaml
Type: Byte
Parameter Sets: NewParentJobGroupHostPort, VMHostCOMPort
Aliases: HostPort

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server.

```yaml
Type: ServerConnection
Parameter Sets: NewParentJobGroupTextFile, NewParentJobGroupNoAttach, NewParentJobGroupHostPort, NewParentJobGroupNamedPipe
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualCOMPort
Specifies a virtual COM port object that this cmdlet modifies.
VMM supports configuring two COM ports on a virtual machine, template, or hardware profile.

```yaml
Type: VirtualCOMPort
Parameter Sets: NoAttach, TextFile, NamedPipe, VMHostCOMPort
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WaitForModem
Indicates whether a virtual COM port on a virtual machine connects immediately to a physical COM port on the host when the virtual machine starts.

If you specify a value of $True, the virtual COM port waits to connect to a physical COM port on the host.
If you specify a value of  $False, the virtual COM port connect immediately to a physical COM port on the host as soon as the virtual machine starts.

```yaml
Type: Boolean
Parameter Sets: NewParentJobGroupHostPort, VMHostCOMPort
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualCOMPort
This cmdlet returns a **VirtualCOMPort** object.

## NOTES
* Requires a VMM virtual COM port object. You can retrieve this object by using the **Get-SCVirtualCOMPort** cmdlet.

## RELATED LINKS

[Get-SCVirtualCOMPort](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualCOMPort.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

