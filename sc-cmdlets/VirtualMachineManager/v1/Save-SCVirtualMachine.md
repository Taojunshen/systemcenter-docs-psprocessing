---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCUserRole.md
schema: 2.0.0
ms.assetid: BBACC3EC-0CDB-409C-ADE2-E000143C9633
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Save-SCVirtualMachine.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Save-SCVirtualMachine.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Save-SCVirtualMachine.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Save-SCVirtualMachine

## SYNOPSIS
Migrates a virtual machine deployed on a host to the VMM library.

## SYNTAX

```
Save-SCVirtualMachine [-VM] <VM> [-LibraryServer <LibraryServer>] [-UseLAN] [-SharePath <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Save-SCVirtualMachine** cmdlet migrates a virtual machine deployed on a host to the Virtual Machine Manager (VMM) library.

This stores a virtual machine to the VMM library by using one of the following transfer methods:

- SAN transfer (Fibre Channel, iSCSI, or NPIV). If the host and library server are both connected to SAN storage, VMM can use a SAN transfer to store the virtual machine in the library. In a SAN transfer, the target LUNs are remapped from the source host to the destination library server. This cmdlet does not moved any files. SAN transfer is much faster than moving virtual machine files from one host to another over a local area network (LAN). VMM can use an NPIV SAN transfer if a host bus adapter (HBA) with NPIV support is available.
- Network transfer. If no faster method is available, VMM uses a network transfer to move the virtual machine files from the host server to the library server over the LAN that connects the two servers. Specify the path of the share in the library to store the virtual machine as the *SharePath* parameter.

This cmdlet automatically uses the fastest available transfer type.
If you want to force a network transfer, specify the *UseLAN* parameter.
If the host server and library server are the same server, the command does not fail if you specify *UseLAN*, but the migration to the library occur faster if you do not use that parameter.

When a virtual machine is stored in the library, it cannot be started.
Before you can start the virtual machine, you must move it to a host by using the Move-SCVirtualMachine cmdlet.

## EXAMPLES

### Example 1: Save a virtual machine to the library
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $LibServer = Get-SCLibraryServer -ComputerName "LibServer01"
PS C:\> Save-SCVirtualMachine -LibraryServer $LibServer -VM $VM -SharePath "\\LibServer01.Contoso.com\Library01\VMs"
```

The first command gets the virtual machine object named VM01, and then stores that object in the $VM variable.

The second command gets the library server object named LibServer01, and then stores that object in the $Library variable.

The last command migrates VM01 from its host and stores it to the location \\\\LibServer01.Contoso.com\Library01\VMs.
The command automatically uses the fastest available transfer type.

### Example 2: Store a virtual machine in the library asynchronously
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $LibServer = Get-SCLibraryServer -ComputerName "LibServer02"
PS C:\> Save-SCVirtualMachine -LibraryServer $LibServer -VM $VM -SharePath "\\LibServer02.Contoso.com\Library02\VMs" -RunAsynchronously -JobVariable "SaveVMJob"
PS C:\> $SaveVMJob
```

The first command gets the virtual machine object named VM02, and then stores that object in the $VM variable.

The second command gets the library server object named LibServer02, and then stores that object in the $Library variable.

The third command migrates VM02 to the location \\\\LibServer02.Contoso.com\Library02\VMs.
The command specifies the *RunAsynchronously* parameter to return control to the command shell immediately.
The command specifies the *JobVariable* parameter tracks job progress, and stores a record of its progress in $SaveVMJob.
For *JobVariable*, you do not specify the dollar sign ($) to create the variable.

The last command displays the contents of $SaveVMJob.

### Example 3: Store a virtual machine in the library by forcing a network transfer
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> $LibServer = Get-SCLibraryServer -ComputerName "LibServer01"
PS C:\> Save-SCVirtualMachine -LibraryServer $LibServer -VM $VM -SharePath "\\LibServer01.Contoso.com\Library01\VMs" -UseLAN
```

The first command gets the virtual machine named VM03, and then stores that object in the $VM variable.

The second command gets the library server object named LibServer01, and then stores that object in the $LibServer variable.

The last command stores VM03 to the location \\\\LibServer01.Contoso.com\Library01\VMs.
The *UseLAN* parameter forces a network transfer over the LAN even if a faster transfer mechanism is available.

## PARAMETERS

### -JobVariable
Specifies the name of a variable for job progress.

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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -SharePath
Specifies a path to a valid library share on an existing library server where this cmdlet saves the virtual machine.
Specify a Universal Naming Convention (UNC) path.

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

### -UseLAN
Indicates that this cmdlet uses transfer over the LAN even if a faster transfer mechanism is available.

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
Specifies a virtual machine object to save.

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
* Requires a VMM virtual machine object, which can be retrieved by using the Get-SCVirtualMachine cmdlet.

## RELATED LINKS

[Get-SCUserRole](xref:VirtualMachineManager/v1/Get-SCUserRole.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Move-SCVirtualMachine](xref:VirtualMachineManager/v1/Move-SCVirtualMachine.md)

[Read-SCVirtualMachine](xref:VirtualMachineManager/v1/Read-SCVirtualMachine.md)

[Stop-SCVirtualMachine](xref:VirtualMachineManager/v1/Stop-SCVirtualMachine.md)

