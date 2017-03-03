---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2DDE259C-EA85-4A2A-9DD4-71660678E268
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDVDDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDVDDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDVDDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVirtualDVDDrive

## SYNOPSIS
Changes properties of a virtual DVD drive associated with a virtual machine, virtual machine template, or hardware profile used in VMM.

## SYNTAX

### BusChangesWithVirtualDVDDriveSpecified (Default)
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] [-VirtualDVDDrive] <VirtualDVDDrive> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ISOWithVirtualDVDDriveSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] [-Link] [-VirtualDVDDrive] <VirtualDVDDrive> -ISO <ISO>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HostDriveWithVirtualDVDDriveSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] [-VirtualDVDDrive] <VirtualDVDDrive> -VMHostDrive <String>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### BusChangesWithSourceBusAndLunSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] -JobGroup <Guid> -SourceBus <Byte> -SourceLUN <Byte>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AnyHostDriveWithSourceBusAndLunSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] -JobGroup <Guid> [-AnyVMHostDrive] -SourceBus <Byte>
 -SourceLUN <Byte> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NoMediaWithVirtualDVDDriveSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] [-VirtualDVDDrive] <VirtualDVDDrive> [-NoMedia]
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AnyHostDriveWithVirtualDVDDriveSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] [-VirtualDVDDrive] <VirtualDVDDrive> [-JobGroup <Guid>]
 [-AnyVMHostDrive] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ISOWithSourceBusAndLunSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] [-Link] -ISO <ISO> -JobGroup <Guid> -SourceBus <Byte>
 -SourceLUN <Byte> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HostDriveWithSourceBusAndLunSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] -VMHostDrive <String> -JobGroup <Guid> -SourceBus <Byte>
 -SourceLUN <Byte> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### NoMediaWithSourceBusAndLunSpecified
```
Set-SCVirtualDVDDrive [-Bus <Byte>] [-LUN <Byte>] [-NoMedia] -JobGroup <Guid> -SourceBus <Byte>
 -SourceLUN <Byte> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualDVDDrive** cmdlet changes one or more properties of a virtual DVD drive object associated with a virtual machine, virtual machine template, or hardware profile used in a Virtual Machine Manager (VMM) environment.

You can use this cmdlet to connect a virtual DVD drive to a physical DVD drive on a virtual machine host server, to a different location on the IDE bus, or to an ISO image, or you can use it to disconnect the virtual DVD drive.

Most settings that you can configure for a virtual DVD drive on a virtual machine are the same regardless of whether the virtualization platform of the host is Hyper-V, VMware, or Citrix XenServer.
All of these virtualization platforms support the following: 

- Connecting a virtual DVD drive to a primary or secondary channel on a host. 

- Capturing information from a physical CD or DVD drive on the host without specifying a drive letter. 

- Capturing information from an image (ISO) file stored in the VMM library. 

- Capturing "no media" (used to disconnect a virtual DVD drive from the host drive or from an ISO file).

The only setting that varies for this cmdlet by virtualization platform is whether an ISO file can be used directly from the VMM library: 

- Hyper-V host.
If you configure a connection to an ISO file in the VMM library, you can choose to use the ISO directly from the library instead of copying it to the host. 

- VMware ESX host.
If you configure a connection to an ISO file in the VMM library, you cannot use the ISO directly from the library but must instead accept the default, which copies the ISO file to the host. 

- Citrix XenServer host.
If you configure a connection to an ISO file in the VMM library, you cannot use the ISO directly from the library but must instead accept the default, which copies the ISO file to the host.
The host must have at least one ISO repository available with write access and enough storage space to contain the ISO file.

Note: If the virtual DVD drive is configured on a virtual machine that was created by using the Virtual Machine wizard in the Hyper-V Manager Console rather than in the VMM console, you must specify a drive letter.
That drive letter will appear in the Properties for that virtual machine in the VMM console.

## EXAMPLES

### Example 1: Connect a virtual DVD drive to a physical DVD drive
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $DVDDrive = Get-SCVirtualDVDDrive -VM $VM | where { $_.Bus -eq 1 -and $_.LUN -eq 0 }
PS C:\> Set-SCVirtualDVDDrive -VirtualDVDDrive $DVDDrive -VMHostDrive "E:"
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the virtual DVD drive object that is located on Secondary Channel 0 (specified by -Bus 1 and -LUN 0) on the IDE bus on VM01 and stores the object in the $DVDDrive variable.

The last command connects the virtual DVD drive object stored in $DVDDrive to a physical drive on the host (the D: drive).
It also deletes any ISO file that the virtual DVD drive used earlier if no other virtual machine currently uses that ISO file.

### Example 2: Connect a virtual DVD drive to a different location on the IDE bus
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $DVDDrive = Get-SCVirtualDVDDrive -VM $VM | where { $_.Bus -eq 1 -and $_.LUN -eq 0 }
PS C:\> Set-SCVirtualDVDDrive -VirtualDVDDrive $DVDDrive -Bus 1 -LUN 1
```

The command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The second command gets the virtual DVD drive object that is located on Secondary Channel 0 (specified by -Bus 1 and -LUN 0) on the IDE bus on VM02 and then stores the virtual DVD drive object in $DVDDrive.

The last command connects the virtual DVD drive object stored in $DVDDrive to a different position on the IDE bus by setting the logical unit number (LUN) to 1.

### Example 3: Disconnect a virtual DVD drive
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> $DVDDrive = Get-SCVirtualDVDDrive -VM $VM | where { $_.Bus -eq 1 -and $_.LUN -eq 0 }
PS C:\> Set-SCVirtualDVDDrive -VirtualDVDDrive $DVDDrive -NoMedia
```

The first command gets the virtual machine object named VM03 and stores the object in the $VM variable.

The second command gets the virtual DVD drive object that is located on Secondary Channel 0 (specified by -Bus 1 and -LUN 0) on the IDE bus on VM03 and then stores the virtual DVD drive object in $DVDDrive.

The last command uses the *NoMedia* parameter to disconnect the virtual DVD drive object stored in $DVDDrive from any host drive or ISO to which it is connected.
It also deletes any ISO file that the virtual DVD drive used earlier if no other virtual machine currently uses that ISO file.

### Example 4: Connect a virtual DVD drive on an existing virtual machine to any available physical DVD drive
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM04"
PS C:\> Set-SCVirtualDVDDrive -AnyVMHostDrive -VirtualDVDDrive (Get-VirtualDVDDrive -VM $VM | where {$_.Bus -eq 1 -and $_.Lun -eq 0})
```

The first command gets the virtual machine object named VM04 and stores the object in the $VM variable.

The last command gets the virtual DVD drive object that is located on the first slot of the Secondary Channel (specified by -Bus 1 and -LUN 0) on the IDE bus on VM04.
The command uses the **Set-SCVirtualDVDDrive** cmdlet with the *AnyVMHostDrive* parameter to connect the virtual DVD drive to any available physical DVD drive on the host.

## PARAMETERS

### -AnyVMHostDrive
Indicates that a virtual DVD or floppy drive on a virtual machine will be connected to any corresponding physical drive on a host.
This mapping occurs when you deploy a stored virtual machine on a host, or when you use a template or hardware profile to create and deploy a virtual machine on a host.

```yaml
Type: SwitchParameter
Parameter Sets: AnyHostDriveWithSourceBusAndLunSpecified, AnyHostDriveWithVirtualDVDDriveSpecified
Aliases: AnyHostDrive

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bus
Specifies the IDE bus to which to attach a virtual disk drive or virtual DVD drive, or the SCSI bus to which to attach a virtual disk drive.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ISO
Specifies an ISO object.

```yaml
Type: ISO
Parameter Sets: ISOWithVirtualDVDDriveSpecified, ISOWithSourceBusAndLunSpecified
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: BusChangesWithVirtualDVDDriveSpecified, ISOWithVirtualDVDDriveSpecified, HostDriveWithVirtualDVDDriveSpecified, NoMediaWithVirtualDVDDriveSpecified, AnyHostDriveWithVirtualDVDDriveSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: BusChangesWithSourceBusAndLunSpecified, AnyHostDriveWithSourceBusAndLunSpecified, ISOWithSourceBusAndLunSpecified, HostDriveWithSourceBusAndLunSpecified, NoMediaWithSourceBusAndLunSpecified
Aliases: 

Required: True
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

- Example format: `-IDE -Bus 1 -LUN 0`
- Example format: `-SCSI -Bus 0 -LUN 1`

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Link
Indicates that a resource should be linked to instead of copied.

```yaml
Type: SwitchParameter
Parameter Sets: ISOWithVirtualDVDDriveSpecified, ISOWithSourceBusAndLunSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoMedia
Disconnects a virtual DVD drive from the host drive or ISO to which it was connected, or disconnects a virtual floppy drive from the host drive or virtual floppy disk to which it was connected.

```yaml
Type: SwitchParameter
Parameter Sets: NoMediaWithVirtualDVDDriveSpecified, NoMediaWithSourceBusAndLunSpecified
Aliases: 

Required: True
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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -SourceBus
Specifies the source IDE bus for the drive.

```yaml
Type: Byte
Parameter Sets: BusChangesWithSourceBusAndLunSpecified, AnyHostDriveWithSourceBusAndLunSpecified, ISOWithSourceBusAndLunSpecified, HostDriveWithSourceBusAndLunSpecified, NoMediaWithSourceBusAndLunSpecified
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceLUN
Specifies the source logical unit number (LUN) for a virtual DVD drive object on an IDE bus.

```yaml
Type: Byte
Parameter Sets: BusChangesWithSourceBusAndLunSpecified, AnyHostDriveWithSourceBusAndLunSpecified, ISOWithSourceBusAndLunSpecified, HostDriveWithSourceBusAndLunSpecified, NoMediaWithSourceBusAndLunSpecified
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostDrive
Specifies a drive on a virtual machine host. 

Example formats: 

- Hyper-V host hard drive: `"C:"`
- Hyper-V host floppy drive: `"A:"`
- VMware ESX host hard drive: `"/dev/tools"`
- VMware ESX host floppy drive: `"/dev/sda"`
- Citrix XenServer host hard drive: `"Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`
- Citrix XenServer host floppy drive: Not supported

```yaml
Type: String
Parameter Sets: HostDriveWithVirtualDVDDriveSpecified, HostDriveWithSourceBusAndLunSpecified
Aliases: HostDrive

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDVDDrive
Specifies a virtual DVD drive object.

```yaml
Type: VirtualDVDDrive
Parameter Sets: BusChangesWithVirtualDVDDriveSpecified, ISOWithVirtualDVDDriveSpecified, HostDriveWithVirtualDVDDriveSpecified, NoMediaWithVirtualDVDDriveSpecified, AnyHostDriveWithVirtualDVDDriveSpecified
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

### VirtualDVDDrive
This cmdlet returns a **VirtualDVDDrive** object.

## NOTES
* Requires a VMM virtual DVD drive object, which can be retrieved by using the **Get-SCVirtualDVDDrive** cmdlet.

## RELATED LINKS

[Get-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDVDDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[New-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDVDDrive.md)

[Remove-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDVDDrive.md)

