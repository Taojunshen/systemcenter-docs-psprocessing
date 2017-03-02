---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FAAA0DD2-C729-4249-B65E-9D189BABA3DA
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVMMManagedComputer

## SYNOPSIS
Gets computer objects managed by VMM.

## SYNTAX

```
Get-SCVMMManagedComputer [-VMMServer <ServerConnection>] [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMMManagedComputer** cmdlet gets one or more computer objects managed by Virtual Machine Manager (VMM).
Managed computers include the following types of computers: 


- Virtual Machine Host.
A Hyper-V host, VMware ESX host, or Citrix XenServer host on which you deploy virtual machines. 


- VMWare Virtualization Manager.
A server running VMware vCenter Server that VMM connects to in order to manage ESX hosts and the virtual machines deployed on those hosts. 

- Library Server.
A server used to make shares available to store VMM library resources. 

- P2V Source Computer.
Any physical computer that you want to clone so that you can use its hardware and software settings to create one or more virtual machines.

## EXAMPLES

### Example 1: Get all computers managed by VMM
```
PS C:\> Get-SCVMMManagedComputer
```

This command gets all computer objects managed by VMM and displays information about these managed computers to the user.
When you look at the output, note that the RoleString property indicates whether the server is a library server, a host for virtual machines, both a library server and a host, a VMware vCenter Server, or a Citrix XenServer.

### Example 2: Update the agent software on all host servers managed by VMM
```
PS C:\> $Credential = Get-Credential
PS C:\> Get-SCVMMManagedComputer | Update-SCVMMManagedcomputer -Credential $Credential -RunAsynchronously
```

The first command uses **Get-Credential** to prompt you to supply a user name and password and then stores your credentials in the $Credential variable.
The required credential for this operation is a domain account with rights to update software on computers managed by VMM.

The second command gets all computer objects managed by VMM, and then passes each managed computer object to the Update-SCVMMManagedComputer cmdlet which updates the VMM agent software on each computer.
As this command is processed, $Credential provides credentials to the **Update-SCVMMManagedComputer** cmdlet.

### Example 3: Get a specific computer managed by VMM by IP address
```
PS C:\> Get-SCVMMManagedComputer -ComputerName "10.20.30.40"
```

This command gets a computer object by its IP address.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
-  NetBIOS name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMMManagedComputer
This cmdlet returns a **VMMManagedComputer** object.

## NOTES

## RELATED LINKS

[Add-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMMManagedComputer.md)

[Read-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMMManagedComputer.md)

[Register-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMMManagedComputer.md)

[Remove-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMMManagedComputer.md)

[Set-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMMManagedComputer.md)

[Update-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Update-SCVMMManagedComputer.md)

