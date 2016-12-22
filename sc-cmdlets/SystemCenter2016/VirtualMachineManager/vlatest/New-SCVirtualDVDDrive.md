---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BEEDF866-A449-4C48-84A3-FE5B427B0E67
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDVDDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDVDDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDVDDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVirtualDVDDrive

## SYNOPSIS
Creates a virtual DVD drive on a virtual machine, a virtual machine template, or a hardware profile used in VMM.

## SYNTAX

### JobGroup
```
New-SCVirtualDVDDrive [-VMMServer <ServerConnection>] -Bus <Byte> -LUN <Byte> [-Link] -JobGroup <Guid>
 [-ISO <ISO>] [-VMHostDrive <String>] [-AnyVMHostDrive] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HardwareProfile
```
New-SCVirtualDVDDrive -Bus <Byte> -LUN <Byte> [-Link] -HardwareProfile <HardwareProfile> [-ISO <ISO>]
 [-VMHostDrive <String>] [-AnyVMHostDrive] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VM
```
New-SCVirtualDVDDrive -Bus <Byte> -LUN <Byte> [-Link] -VM <VM> [-ISO <ISO>] [-VMHostDrive <String>]
 [-AnyVMHostDrive] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Template
```
New-SCVirtualDVDDrive -Bus <Byte> -LUN <Byte> [-Link] -VMTemplate <Template> [-ISO <ISO>]
 [-VMHostDrive <String>] [-AnyVMHostDrive] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualDVDDrive** cmdlet creates a virtual DVD drive object on a virtual machine, a virtual machine template, or a hardware profile used in a Virtual Machine Manager (VMM) environment.
By default, the virtual DVD drive created by New-SCVirtualDVDDrive is not connected to any media.
You can use the **Set-SCVirtualDVDDrive** cmdlet to connect a virtual DVD drive to a physical DVD drive on a virtual machine host or to an ISO image.

Note: You can connect a virtual DVD drive to an IDE device on a virtual machine but you cannot connect a virtual DVD drive to a SCSI adapter on a virtual machine.

## EXAMPLES

### Example 1: Create a virtual DVD drive on a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> New-SCVirtualDVDDrive -VM $VM -Bus 1 -LUN 1
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command creates a virtual DVD drive on VM01 and attaches the virtual DVD drive to Secondary channel (1) by specifying IDE Bus 1 and LUN 1.

### Example 2: Create a virtual DVD drive on a virtual machine template
```
PS C:\> $VMTemplate = Get-SCVMTemplate | where { $_.Name -eq "VMTemplate01" }
PS C:\> New-SCVirtualDVDDrive -VMTemplate $VMTemplate -Bus 1 -LUN 1
```

The first command gets the virtual machine templat object named VMTemplate01 and stores the object in the $Template variable.

The second command creates a virtual DVD drive on VMTemplate01 that attaches a virtual DVD drive to Secondary Channel (1) on the IDE bus when the template is used to create a virtual machine.

### Example 3: Create a virtual DVD drive on a hardware profile
```
PS C:\> $HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01" }
PS C:\> New-SCVirtualDVDDrive -HardwareProfile $HWProfile -Bus 1 -LUN 1
```

The first command gets the hardware profile object named NewHardwareProfile01 and stores the object in the $HWProfile variable.

The second command creates a virtual DVD drive on HardwareProfile1 that attaches a virtual DVD drive to Secondary Channel (1) on the IDE bus when the hardware profile is used to create a virtual machine.

### Example 4: Create a virtual machine with a virtual DVD drive that connects to any available physical DVD drive on the host
```
PS C:\> $JobGroupId = [Guid]::NewGuid().ToString()
PS C:\> New-SCVirtualDVDDrive -VMMServer "VMMServer01.Contoso.com" -JobGroup $JobGroupId -Bus 1 -LUN 0 -AnyVMHostDrive 
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost04"
PS C:\> New-SCVirtualMachine -Name "VM04" -Description "A new VM with a DVD drive" -VMMServer "VMMServer01.Contoso.com" -Owner "Contoso\Katarina" -VMHost $VMHost -Path "D:\VirtualMachinePath" -StartVM -JobGroup $JobGroupId
```

The first command creates a new GUID string and stores it to variable $JobGroupID.
This GUID is a job group ID that functions as an identifier that groups subsequent commands that include this identifier into a single job group.

The second command creates a new virtual DVD drive object and specifies that this new virtual DVD drive can use any available physical DVD drive.
The command will attach the new virtual DVD drive to the first slot of the second IDE channel (IDE is the only bus type that a virtual DVD drive can be attached to).
Using the job group ID specifies that that this command does not run until just before the final command that includes the *JobGroup* parameter runs.

The third command gets the host object named VMHost04 and stores the object in the $VMHost variable.

The last command creates a virtual machine, names it VM04, provides a description, assigns an owner, and specifies the location on the host to store the virtual machine.
The  command uses the job group ID to run the **New-SCVirtualDVDDrive** command just before the New-SCVirtualMachine command runs; the resulting virtual DVD drive object is associated with the new virtual machine.

### Example 5: Add a new virtual DVD drive to an existing virtual machine and attach an ISO file from the library to the drive
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM05"
PS C:\> $ISO = Get-SCISO | where {$_.Name -eq "WindowsServer2008R2.iso"}
PS C:\> New-SCVirtualDVDDrive -VM $VM -ISO $ISO -Bus 1 -LUN 1
```

The first command gets the virtual machine object named VM05 and stores the object in the $VM variable.

The second command gets the ISO object named WindowsServer2008R2.iso and stores the object in the $ISO variable.

The last command creates a new virtual DVD drive on VM05, attaches it to the specified location on the IDE bus, and links it with the ISO image stored in $ISO.

## PARAMETERS

### -AnyVMHostDrive
Indicates that a virtual DVD or floppy drive on a virtual machine will be connected to any corresponding physical drive on a host.
This mapping occurs when you deploy a stored virtual machine on a host, or when you use a template or hardware profile to create and deploy a virtual machine on a host.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: AnyHostDrive

Required: False
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -ISO
Specifies an ISO object.

```yaml
Type: ISO
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: JobGroup
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Link
Indicates that a resource should be linked to instead of copied.

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

### -VM
Specifies a virtual machine object.

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
Parameter Sets: (All)
Aliases: HostDrive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

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

### VirtualDVDDrive
This cmdlet returns a **VirtualDVDDrive** object.

## NOTES
* Requires a VMM virtual machine object, virtual machine template object, or hardware profile object. You can retrieve these objects by using the **Get-SCVirtualMachine**, **Get-SCVMTemplate**, or **Get-SCHardwareProfile** cmdlets, respectively.

## RELATED LINKS

[Get-SCHardwareProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCHardwareProfile.md)

[Get-SCISO](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISO.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDVDDrive.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Remove-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDVDDrive.md)

[Set-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDVDDrive.md)

