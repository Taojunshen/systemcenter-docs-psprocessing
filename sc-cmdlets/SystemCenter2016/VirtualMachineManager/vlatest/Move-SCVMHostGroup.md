---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMHostGroup.md
schema: 2.0.0
ms.assetid: 0BD94D79-3577-4ECF-89B1-4AFE9A19CE74
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Move-SCVMHostGroup

## SYNOPSIS
Moves a host group from the current location to a new location under a different host group parent.

## SYNTAX

```
Move-SCVMHostGroup [-VMHostGroup] <HostGroup> [-JobGroup <Guid>] -ParentHostGroup <HostGroup>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-SCVMHostGroup** cmdlet moves one or more host group objects, which contain virtual machine hosts managed by Virtual Machine Manager (VMM), from the current location to a new location under a different host group parent.
You can place host groups under the default root host group (All Hosts) or under any other host group created by an administrator.

All hosts within a moved host group acquire a new host path relative to the root host group.
Changing the structure of host groups might change which Self Service User or Delegated Administrator user roles have access to the hosts contained within the affected host groups, or to the virtual machines deployed on those hosts.

## EXAMPLES

### Example 1: Move one host group to a new parent host group
```
PS C:\>$OldHostGroup = Get-SCVMHostGroup -Name "OldHostGroup"
PS C:\> $NewHostGroup = Get-SCVMHostGroup -Name "NewHostGroup"
PS C:\> Move-SCVMHostGroup -VMHostGroup $OldHostGroup -ParentHostGroup $NewHostGroup
```

The first command gets the host group named OldHostGroup and stores the host group object in the $OldHostGroup variable.

The second command gets the host group named NewHostGroup and stores this host group object in the $NewHostGroup variable.

The last command moves the host group stored in the $OldHostGroup variable (OldHostGroup) to a location under its new parent host group, stored in the $NewHostGroup variable.

### Example 2: Move all host groups to a new parent host group
```
PS C:\>$AllGroups = Get-SCVMHostGroup
PS C:\> $HostGroup = New-SCVMHostGroup -Name "NewHostGroup01" 
PS C:\> $AllGroups | Move-SCVMHostGroup -ParentHostGroup $HostGroup
```

The first command gets all host group objects and stores them in the $AllGroups array.
This includes the default parent host group (All Hosts).

The second command creates a host group object named NewHostGroup01 and stores it in the $HostGroup variable.

The last command passes each host group object stored in the $AllGroups variable to the **Move-VMHostGroup** cmdlet, which moves each host group object to location stored in the $HostGroup variable, except for All Hosts because All Hosts is the default parent host group and cannot be moved.

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

### -ParentHostGroup
Specifies the parent host group that contains one or more hosts, host groups, or host clusters.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: ParentVMHostGroup

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

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
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

### HostGroup
This cmdlet returns a **HostGroup** object.

## NOTES
* Requires a VMM host group object, which can be retrieved by using the Get-SCVMHostGroup cmdlet.

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[New-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHostGroup.md)

[Remove-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostGroup.md)

[Set-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostGroup.md)

