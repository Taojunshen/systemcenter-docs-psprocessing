---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMHostGroup.md
schema: 2.0.0
ms.assetid: F858B08E-F0A0-46C8-8470-1AA55D799022
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMHostGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMHostGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMHostGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMHostGroup

## SYNOPSIS
Creates a host group that can contain virtual machine host computers, other host groups, or host clusters.

## SYNTAX

```
New-SCVMHostGroup [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>]
 [-ParentHostGroup <HostGroup>] [-EnableUnencryptedFileTransfer <Boolean>] [-InheritNetworkSettings <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMHostGroup** cmdlet creates a host group object that can contain host computers on which one or more virtual machines are deployed, other host groups, or host clusters.

Virtual Machine Manager (VMM) provides a default parent host group called All Hosts, to which you can add child host groups.
A new host group is empty until you move hosts into it or create one or more child host groups under it.
Host groups are organized into a hierarchical and customizable tree structure.
In the host group tree, the parent of a new host group is either the default root host group (All Hosts) or a user-created host group.

A host group can be a parent container for any of the following: 

- A host or set of hosts
- A host group or set of host groups, and hosts within those host groups
- A host cluster, and hosts (nodes) within that host cluster

Hosts contained in a host group have a host path property that shows the location of that host in the host group hierarchy, as illustrated in the following table:

Name                                        Path

All Hosts                          All Hosts
ChildHostGroup01             All Hosts\ChildHostGroup01
ChildHostGroup02           All Hosts\ChildHostGroup02
New Datacenter            All Hosts\New Datacenter
nested1                           All Hosts\New Datacenter\nested01
nested2                   All Hosts\New Datacenter\nested\nested02

## EXAMPLES

### Example 1: Create a host group under the root host group
```
PS C:\>New-SCVMHostGroup -VMMServer "VMMServer01.Contoso.com" -Name "HostGroup01"
```

This command creates a host group named HostGroup01 on VMMServer01 in the Contoso.com domain.
By default, VMM places this host group under the root host group, which is called All Hosts.

### Example 2: Create a host group under a specified parent host group
```
PS C:\>$ParentGroup = Get-SCVMHostGroup -Name "HostGroup01" 
PS C:\> New-SCVMHostGroup -Name "ChildGroup01" -ParentHostGroup $ParentGroup
```

The first command gets the host group named HostGroup01 and stores it in the $ParentGroup variable.

The second command creates a host group named ChildGroup01 and places it under the parent host group stored in the $ParentGroup variable.

## PARAMETERS

### -Description
Specifies a description for the host group.

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

### -EnableUnencryptedFileTransfer
Indicates, when set to True, that network file transfers do not require encryption.
Allowing unencrypted network file transfers can improve performance if neither the source host nor the destination host requires encryption.

Use this parameter to: 


- Enable unencrypted file transfers into, or out of, the library. 
- Enable unencrypted file transfers into, out of, or within a host group.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AllowUnencryptedTransfers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InheritNetworkSettings
Indicates, when set to $True, that the network settings for a host group will have the same values as those specified for its parent.

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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### HostGroup
This cmdlet returns a **HostGroup** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHostGroup.md)

[Move-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Move-SCVMHostGroup.md)

[Remove-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVMHostGroup.md)

[Set-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMHostGroup.md)

