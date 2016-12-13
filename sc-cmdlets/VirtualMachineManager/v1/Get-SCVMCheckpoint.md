---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: C1EB8A0E-33C5-462E-A319-1D3A0E7933A0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMCheckpoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMCheckpoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMCheckpoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMCheckpoint

## SYNOPSIS
Gets virtual machine checkpoint objects from the VMM database.

## SYNTAX

### Connection (Default)
```
Get-SCVMCheckpoint [-VMMServer <ServerConnection>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### VM
```
Get-SCVMCheckpoint [-VM <VM>] [-VMMServer <ServerConnection>] [-MostRecent] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVMCheckpoint [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMCheckpoint** cmdlet gets one or more virtual machine checkpoint objects from the Virtual Machine Manager (VMM) database.

A virtual machine checkpoint is a point-in-time "snapshot" of a virtual machine.
You can use the checkpoint to revert a virtual machine to a previous state.
For more information about VMM checkpoints, type `Get-Help New-VMCheckpoint -Detailed`.

## EXAMPLES

### Example 1: Get all existing checkpoints for each virtual machine
```
PS C:\>Get-SCVMCheckpoint -VMMServer "VMMServer01.Contoso.com"
```

This command gets all existing checkpoint objects for each virtual machine managed by VMMServer01 and displays information about these checkpoint objects to the user.

### Example 2: Get all checkpoints for one or more virtual machines with a specific name
```
PS C:\>$Checkpoints = Get-SCVMCheckpoint -VM "VM01" 
PS C:\> $Checkpoints
```

The first command gets all checkpoint objects for virtual machine VM01 and stores the objects in the $Checkpoints object array.

The second command displays information about the checkpoint objects in $Checkpoints.

### Example 3: Get the hardware profile of the most recently created checkpoint on a VM deployed on a Hyper-V host
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $Checkpoint = $VM | Get-SCVMCheckpoint -MostRecent
PS C:\> $Checkpoint.CheckpointHWProfile
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the most recent checkpoint object created for VM01 and stores the object in the $Checkpoint variable.

The last command displays information about the hardware profile for checkpoint stored in $Checkpoint (the most recent checkpoint object created for VM01).

### Example 4: Display the .NET type, events, methods, and properties for checkpoint objects
```
PS C:\>$Checkpoints = Get-SCVMCheckpoint -VMMServer "VMMServer01.Contoso.com"
PS C:\> $Checkpoints | Get-Member
PS C:\> $Checkpoints | Get-Member | Format-List
```

The first command gets all checkpoint objects on VMMServer01 and stores the objects in the $Checkpoints object array.

The second command passes each checkpoint object in $Checkpoints to the Get-Member cmdlet, which displays the .NET TypeName and the Name, MemberType, and Definition for each event, method, and property associated with this object type.

The last command is the same as the second command except that it pipes the output to the Format-List cmdlet so that you can see the complete definition for each event, method, and property for the checkpoint object type.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MostRecent
Specifies the most recent VMM virtual machine checkpoint object.

```yaml
Type: SwitchParameter
Parameter Sets: VM
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnBehalfOfUser
Specifies the name of a user.
This cmdlet sets the on behalf of user as the user that this parameter specifies.

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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### VMCheckpoint
This cmdlet returns a **VMCheckpoint** object.

## NOTES

## RELATED LINKS

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[New-SCVMCheckpoint](xref:VirtualMachineManager/v1/New-SCVMCheckpoint.md)

[Remove-SCVMCheckpoint](xref:VirtualMachineManager/v1/Remove-SCVMCheckpoint.md)

[Restore-SCVMCheckpoint](xref:VirtualMachineManager/v1/Restore-SCVMCheckpoint.md)

[Set-SCVMCheckpoint](xref:VirtualMachineManager/v1/Set-SCVMCheckpoint.md)

