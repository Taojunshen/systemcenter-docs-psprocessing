---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: 49C15197-B9C3-4897-A2A6-72769032A343
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Move-SCVirtualHardDisk.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Move-SCVirtualHardDisk.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Move-SCVirtualHardDisk.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Move-SCVirtualHardDisk

## SYNOPSIS
Moves a virtual hard disk file from one location to another on the same host or, when used with Move-SCVirtualMachine, to a location on a different host.

## SYNTAX

### MoveVHDOnSCSI
```
Move-SCVirtualHardDisk [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte> [-SCSI] -JobGroup <Guid>
 -Path <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### MoveVHDOnIDE
```
Move-SCVirtualHardDisk [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte> [-IDE] -JobGroup <Guid>
 -Path <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### SetVM
```
Move-SCVirtualHardDisk [-VirtualHardDisk] <StandaloneVirtualHardDisk> [-JobGroup <Guid>] -Path <String>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-SCVirtualHardDisk** cmdlet moves a Windows-based virtual hard disk file (a .vhd file) or a VMware-based virtual hard disk file (a .vmdk file) from one location to another on the same host.
You can also use **Move-SCVirtualHardDisk** with the Move-SCVirtualMachine cmdlet to move a virtual hard disk file to a location on a different host. 


 
You can use this cmdlet to perform the following tasks: 



- Move a virtual hard disk on a running VMware virtual machine with no service interruption. 


- Move a virtual hard disk on a running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2016 virtual machine with minimal service interruption.
In this case, use **Move-SCVirtualHardDisk** with **Move-SCVirtualMachine**.

    
- Move a virtual hard disk on a virtual machine on any type of host if the virtual machine is in a stopped state or in a saved state.
In this case, use **Move-SCVirtualHardDisk** with Set-SCVirtualMachine.
This option is supported if either of the following conditions are true: 


    
 -- The virtual machine is on a host that uses Windows Server 2008 R2, Windows Server 2012, or Windows Server 2016 Hyper-V technology or on a VMware ESX host, and the virtual machine is in a saved state or in a stopped state. 


 -- The virtual machine is on any other supported host, and it is in a stopped state.

Usage examples: 



- If a host has multiple physical disk drives and the virtual machine has two virtual hard disks (one disk might contain the operating system and the other disk might contain data), you can use this cmdlet to move one of the virtual hard disks to a different physical hard drive in order to improve performance for both virtual hard disks. 


- If the virtual machine has one dynamically expanding virtual hard disk and you discover that the virtual hard disk has expanded to a point where it uses most of the space on its current physical hard disk on the host, you can use this cmdlet to move the expanded virtual hard disk to a larger physical hard disk if one is available on the host.

## EXAMPLES

### Example 1: Move a virtual hard disk file from one location to another on the same host
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VHD = $VM.VirtualHardDisks[0]
PS C:\> Move-SCVirtualHardDisk -VirtualHardDisk $VHD -Path "C:\VHDs"
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command stores the first virtual hard disk object on VM01 in the $VHD variable.

The last command moves the virtual hard disk stored in $VHD to the existing folder "C:\VHDs".

## PARAMETERS

### -Bus
Specifies the IDE bus to which to attach a virtual disk drive or virtual DVD drive, or the SCSI bus to which to attach a virtual disk drive.

```yaml
Type: Byte
Parameter Sets: MoveVHDOnSCSI, MoveVHDOnIDE
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IDE
Specifies IDE as the bus type to which to attach a virtual disk drive object or a virtual DVD drive object configured on a virtual machine or on a template. 



Example format: `-IDE -Bus 0 -LUN 1`

```yaml
Type: SwitchParameter
Parameter Sets: MoveVHDOnIDE
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: MoveVHDOnSCSI, MoveVHDOnIDE
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: SetVM
Aliases: 

Required: False
Position: Named
Default value: None
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

### -LUN
Specifies the logical unit number (LUN) for a virtual disk drive object or for a virtual DVD drive object on an IDE bus, or for a virtual disk drive object on a SCSI bus. 



Example format: ` -IDE -Bus 1 -LUN 0`

Example format: `-SCSI -Bus 0 -LUN 1`

```yaml
Type: Byte
Parameter Sets: MoveVHDOnSCSI, MoveVHDOnIDE
Aliases: 

Required: True
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

### -Path
Specifies the destination path for the operation. 



Example formats: 

 Local path:       `-Path "F:\"`

 UNC path:         `-Path "\\\\Library\Templates"`

 Volume GUID path: `-Path "\\\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`

 VMware ESX path:  `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`

 Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -SCSI
Specifies SCSI as the bus type to which to attach a virtual disk drive object configured on a virtual machine or on a template. 



Example format: `-SCSI -Bus 0 -LUN 0`

```yaml
Type: SwitchParameter
Parameter Sets: MoveVHDOnSCSI
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: MoveVHDOnSCSI, MoveVHDOnIDE
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualHardDisk
Specifies a virtual hard disk object.

```yaml
Type: StandaloneVirtualHardDisk
Parameter Sets: SetVM
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

### VirtualHardDisk
This cmdlet returns a **VirtualHardDisk** object.

## NOTES

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Compress-SCVirtualDiskDrive.md)

[Copy-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Copy-SCVirtualHardDisk.md)

[Get-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Get-SCVirtualHardDisk.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Remove-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Remove-SCVirtualHardDisk.md)

[Set-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Set-SCVirtualHardDisk.md)

