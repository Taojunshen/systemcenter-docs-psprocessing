---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Compress-SCVirtualDiskDrive.md
schema: 2.0.0
ms.assetid: 889A17D3-5ACA-4243-91C0-0462D1E1E3BD
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVirtualDiskDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVirtualDiskDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVirtualDiskDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualDiskDrive

## SYNOPSIS
Modifies settings of a virtual disk drive.

## SYNTAX

### BusChanges (Default)
```
Set-SCVirtualDiskDrive [-Bus <Byte>] [-LUN <Byte>] [-SCSI] [-IDE] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-SharedStorage <Boolean>] [-CreateDiffDisk <Boolean>]
 -VirtualDiskDrive <VirtualDiskDrive> [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### StorageQoSPolicy
```
Set-SCVirtualDiskDrive [-Bus <Byte>] [-LUN <Byte>] [-SCSI] [-IDE] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] -StorageQoSPolicy <StorageQoSPolicy>
 [-SharedStorage <Boolean>] [-CreateDiffDisk <Boolean>] -VirtualDiskDrive <VirtualDiskDrive> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### IOPSMaximum
```
Set-SCVirtualDiskDrive [-Bus <Byte>] [-LUN <Byte>] [-SCSI] [-IDE] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] -IOPSMaximum <UInt64> [-SharedStorage <Boolean>]
 [-CreateDiffDisk <Boolean>] -VirtualDiskDrive <VirtualDiskDrive> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### DisableStorageQoS
```
Set-SCVirtualDiskDrive [-Bus <Byte>] [-LUN <Byte>] [-SCSI] [-IDE] [-VolumeType <VolumeType>]
 [-StorageClassification <StorageClassification>] [-SharedStorage <Boolean>] [-CreateDiffDisk <Boolean>]
 -VirtualDiskDrive <VirtualDiskDrive> [-JobGroup <Guid>] [-DisableStorageQoS] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualDiskDrive** cmdlet modifies settings of a virtual disk drive object on a virtual machine or on a virtual machine template in a Virtual Machine Manager (VMM) environment.
You can use this cmdlet to change the *Bus* type (IDE or SCSI), or to change the Bus and LUN settings to connect a virtual disk drive to a different location on the bus.

## EXAMPLES

### Example 1: Change the IDE bus and LUN settings for a virtual disk drive
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VirtDiskDrive = @(Get-SCVirtualDiskDrive -VM $VM)
PS C:\> If($VirtDiskDrive.Count -Eq 1 -And $VirtDiskDrive[0].Bus -Eq 0 -And $VirtDiskDrive[0].Lun -Eq 1){Set-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive[0] -Bus 0 -LUN 0}
```

The first command gets the virtual machine object VM01 by using the Get-SCVirtualMachine cmdlet.
The command stores that object in the $VM variable.

The second command gets the virtual disk drive object on VM01, and then stores the object in $VirtDiskDrive.
Using the @ symbol and parentheses make sure that the command stores the results in an array even if the command returns a single object or a $Null value.

The last command sets the Bus value to 0 and sets the LUN value to 0 for the virtual disk drive on VM01, if the virtual machine has only one virtual disk drive and is located on the second slot of the first IDE channel.

### Example 2: Change the bus type for a virtual disk drive from SCSI to IDE
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $VirtDiskDrive = Get-SCVirtualDiskDrive -VM $VM
PS C:\> Set-SCVirtualDiskDrive -VirtualDiskDrive $VirtDiskDrive[1] -IDE -Bus 0 -LUN 1
```

The first command gets the virtual machine object named VM02, and then stores that object in the $VM variable.

The second command gets all virtual disk drive objects configured for the virtual machine stored in $VM, and stores those virtual disk drive objects in the $VirtDiskDrive object array.
This example assumes that the virtual disk drive is on a SCSI bus.

The last command sets the Bus type to IDE.
The command connects the second virtual disk drive, specified by $VirtDiskDrive\[1\], to Primary Channel (1) and slot 2, specified by -Bus 0 and LUN 1.

## PARAMETERS

### -Bus
Specifies the IDE bus to which to attach a virtual disk drive or the SCSI bus to which to attach a virtual disk drive.

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

### -CreateDiffDisk
Indicates whether the cmdlet creates a differencing disk.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableStorageQoS
Indicates this cmdlet disables storage Quality of Service (QoS) standards.

```yaml
Type: SwitchParameter
Parameter Sets: DisableStorageQoS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IDE
Indicates that IDE is the bus type to which to attach a virtual disk drive object configured on a virtual machine or on a template.

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

### -IOPSMaximum
Specifies the maximum IOPS.

```yaml
Type: UInt64
Parameter Sets: IOPSMaximum
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

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

### -LUN
Specifies the logical unit number (LUN) for a virtual disk drive object or for a virtual disk drive object on a SCSI bus.

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

### -SCSI
Specifies SCSI as the bus type to which to attach a virtual disk drive object configured on a virtual machine or on a template.

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

### -SharedStorage
Indicates whether the virtual disk drive uses shared storage.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageClassification
Specifies a storage classification object.

```yaml
Type: StorageClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQoSPolicy
Specifies a storage QoS policy.

```yaml
Type: StorageQoSPolicy
Parameter Sets: StorageQoSPolicy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDiskDrive
Specifies a virtual disk drive object.
You can attach either a virtual hard disk or a pass-through disk to a virtual disk drive object.

```yaml
Type: VirtualDiskDrive
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VolumeType
Specifies the volume type for a virtual hard disk.
The acceptable values for this parameter are:

- Boot
- System
- BootAndSystem
- None

```yaml
Type: VolumeType
Parameter Sets: (All)
Aliases: 
Accepted values: None, Boot, System, BootAndSystem

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

### VirtualDiskDrive
This cmdlet returns a **VirtualDiskDrive** object.

## NOTES
* This cmdlet requires a VMM virtual disk drive object, which can be retrieved by using the Get-SCVirtualDiskDrive cmdlet.

## RELATED LINKS

[Compress-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Compress-SCVirtualDiskDrive.md)

[Convert-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Convert-SCVirtualDiskDrive.md)

[Expand-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Expand-SCVirtualDiskDrive.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualDiskDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVirtualMachine.md)

[New-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVirtualDiskDrive.md)

[Remove-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVirtualDiskDrive.md)

[Test-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1.0/Test-SCVirtualDiskDrive.md)

