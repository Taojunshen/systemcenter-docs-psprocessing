---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4BD90B3F-B7B1-4054-ACE5-FAEBDA9B78D7
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDVDDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDVDDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualDVDDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualDVDDrive

## SYNOPSIS
Removes a virtual DVD drive object from VMM.

## SYNTAX

### VirtualDVDDriveSpecified
```
Remove-SCVirtualDVDDrive [-VirtualDVDDrive] <VirtualDVDDrive> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### SourceBusAndLunSpecified
```
Remove-SCVirtualDVDDrive -SourceBus <Byte> -SourceLUN <Byte> -JobGroup <Guid> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualDVDDrive** cmdlet removes one or more virtual DVD drive objects from a hardware profile, a virtual machine, or a virtual machine template used in a Virtual Machine Manager (VMM) environment.
The cmdlet also deletes any .iso file that the virtual DVD drive uses from the file system on the library server.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a specific virtual DVD drive from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $DVDDrive = Get-SCVirtualDVDDrive -VM $VM | where { $_.Bus -eq 1 -and $_.LUN -eq 0 }
PS C:\> Remove-SCVirtualDVDDrive -VirtualDVDDrive $DVDDrive
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the virtual DVD drive object located on the first slot of the Secondary Channel (specified by -Bus 1 and -LUN 0) on the IDE bus on VM01 and then stores the virtual DVD drive object in the $DVDDrive variable.

The last command removes the virtual DVD drive object stored in $DVDDrive from VM01 and deletes any .iso file that this virtual DVD drive uses from the file system on the library server.

### Example 2: Remove the third virtual DVD drive from a virtual machine
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM02"
PS C:\> $DVDDrive = Get-SCVirtualDVDDrive -VM $VM
PS C:\> $DVDDrive[2] | Remove-SCVirtualDVDDrive
```

The first command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The second command gets all virtual DVD drive objects connected to VM02 and stores each virtual DVD drive object in the $DVDDrive object array.
This example assumes that VM02 has three virtual DVD drives and therefore the array contains three elements (counting 0 to 2).

The last command passes the third virtual DVD drive (object \[2\]) stored in $DVDDrive to the **Remove-SCVirtualDVDDrive** cmdlet, which removes this virtual DVD drive object from VM02 and deletes any .iso file used by this virtual DVD drive from the file system on the library server.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: VirtualDVDDriveSpecified
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: SourceBusAndLunSpecified
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
Parameter Sets: SourceBusAndLunSpecified
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
Parameter Sets: SourceBusAndLunSpecified
Aliases: 

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
Parameter Sets: VirtualDVDDriveSpecified
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* Requires a VMM virtual DVD drive object, which can be retrieved by using the **Get-SCVirtualDVDDrive** cmdlet.

## RELATED LINKS

[Get-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualDVDDrive.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[New-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualDVDDrive.md)

[Set-SCVirtualDVDDrive](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualDVDDrive.md)

