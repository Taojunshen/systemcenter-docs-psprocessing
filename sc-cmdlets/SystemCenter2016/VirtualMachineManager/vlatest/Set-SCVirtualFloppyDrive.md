---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DB1D1C95-80EF-48A3-944F-1D657C21985F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFloppyDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualFloppyDrive

## SYNOPSIS
Changes properties of a virtual floppy drive associated with a virtual machine, virtual nmachine template, or hardware profile used in VMM.

## SYNTAX

### VirtualFloppyDisk
```
Set-SCVirtualFloppyDrive [-VMMServer <ServerConnection>] [[-VirtualFloppyDrive] <VirtualFloppyDrive>]
 -VirtualFloppyDisk <VirtualFloppyDisk> [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### NoMedia
```
Set-SCVirtualFloppyDrive [-VMMServer <ServerConnection>] [[-VirtualFloppyDrive] <VirtualFloppyDrive>]
 [-NoMedia] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualFloppyDrive** cmdlet changes one or more properties of a virtual floppy drive associated with a virtual machine, virtual machine template, or hardware profile used in a Virtual Machine Manager (VMM) environment.

You can use the **Set-SCVirtualFloppyDrive** cmdlet to configure the virtual floppy drive to use a physical floppy drive (typically, drive A:) to read physical floppy disks, to read an existing virtual floppy disk, or to disconnect the virtual floppy disk.

## EXAMPLES

### Example 1: Connect a virtual floppy drive to a virtual floppy disk
```
PS C:\> $FloppyDisk = Get-SCVirtualFloppyDisk -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "BootDisk.vfd"}
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $FloppyDrive = @(Get-SCVirtualFloppyDrive -VM $VM)
PS C:\> Set-SCVirtualFloppyDrive -VirtualFloppyDrive $FloppyDrive[0] -VirtualFloppyDisk $FloppyDisk
```

The first command gets the virtual floppy disk object named BootDisk.vfd from VMMServer01 and stores the object in the $FloppyDisk variable.

The second command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The third command gets the virtual floppy drive object on VM01 and stores the virtual floppy drive object in the $FloppyDrive object array (in the event there is more than one virtual floppy drive object, the array stores all of the objects).

The last command connects the virtual floppy disk stored in $FloppyDisk (BootDisk.vfd) to the first virtual floppy drive on VM01.

### Example 2: Disconnect a virtual floppy drive
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $FloppyDrive = @(Get-SCVirtualFloppyDrive -VM $VM)
PS C:\> Set-SCVirtualFloppyDrive -VirtualFloppyDrive $FloppyDrive[0] -NoMedia
```

The first command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The second command gets the virtual floppy drive object on VM02 and stores the object in $FloppyDrive.

The last command disconnects the virtual floppy drive object stored in $FloppyDrive from any host drive or virtual floppy disk to which it was connected by specifying the *NoMedia* parameter.
This command also deletes any virtual floppy disk that the virtual floppy drive used earlier if no other virtual machine currently uses that virtual floppy disk.

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -NoMedia
Disconnects a virtual DVD drive from the host drive or ISO to which it was connected, or disconnects a virtual floppy drive from the host drive or virtual floppy disk to which it was connected.

```yaml
Type: SwitchParameter
Parameter Sets: NoMedia
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

### -VirtualFloppyDisk
Specifies a virtual floppy disk object.

```yaml
Type: VirtualFloppyDisk
Parameter Sets: VirtualFloppyDisk
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualFloppyDrive
Specifies a virtual floppy drive object.

```yaml
Type: VirtualFloppyDrive
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualFloppyDrive
This cmdlet returns a **VirtualFloppyDrive** object.

## NOTES
* Requires a VMM virtual floppy drive object, which can be retrieved by using the **Get-SCVirtualFloppyDrive** cmdlet.

## RELATED LINKS

[Get-SCVirtualFloppyDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFloppyDisk.md)

[Get-SCVirtualFloppyDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFloppyDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

