---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 711DCA9F-DB6C-445D-A5E8-DFF4F4FBDDDD
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetworkDefinition.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetworkDefinition.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetworkDefinition.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLogicalNetworkDefinition

## SYNOPSIS
Modifies a logical network definition.

## SYNTAX

```
Set-SCLogicalNetworkDefinition [-VMMServer <ServerConnection>]
 [-LogicalNetworkDefinition] <LogicalNetworkDefinition> [-AddVMHostGroup <HostGroup[]>]
 [-RemoveVMHostGroup <HostGroup[]>] [-Name <String>] [-SubnetVLan <SubnetVLan[]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLogicalNetworkDefinition** cmdlet modifies a logical network definition.
For example, you can add a host group to or remove a host group from a logical network definition (also called a network site).

## EXAMPLES

### Example 1: Change the host groups associated with a logical network definition
```
PS C:\> $LogicalNetwork = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> $VMHostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production"}
PS C:\> $Definition = Get-SCLogicalNetworkDefinition -LogicalNetwork $LogicalNetwork -VMHostGroup $VMHostGroup -Name "Logical Network Definition 01"
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup03\Production" }
PS C:\> Set-SCLogicalNetworkDefinition -LogicalnetworkDefinition $Definition -AddVMHostGroup $HostGroup
```

The first command gets the logical network named "LogicalNetwork01" and stores it in the $LogicalNetwork variable.

The second command gets the host group named "All Hosts\HostGroup02\Production" and stores it in the $VMHostGroup variable.

The third command gets the logical network definition named "Logical Network Definition 01" associated with the logical network stored in $LogicalNetwork and the host group stored in $VMHostGroup.

The fourth command gets the host group object named "All Hosts\HostGroup-3\Production" and stores the object in the $HostGroup variable.

The last command adds the host group stored in $HostGroup to the existing host groups array for the logical network definition stored in $Definition (Logical Network Definition 01).

## PARAMETERS

### -AddVMHostGroup
Specifies an array of one or more host groups to add to an existing host group array or private cloud.

```yaml
Type: HostGroup[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies the name of a variable in which job progress is tracked and stored.

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

### -LogicalNetworkDefinition
Specifies a logical network definition (also called a network site) that contains the subnet that the IP address pool serves, as specified by the *-SubnetVLan* parameter.

```yaml
Type: LogicalNetworkDefinition
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -RemoveVMHostGroup
Specifies an array of one or more host groups to remove from a host group array or private cloud.

```yaml
Type: HostGroup[]
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

### -SubnetVLan
Specifies an array of one or more IP subnet and VLAN sets.

For information about creating a SubnetVLan, type: `Get-Help New-SCSubNetVLan`.

```yaml
Type: SubnetVLan[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### LogicalNetworkDefiniton
This cmdlet returns a **LogicalNetworkDefiniton** object.

## NOTES
* Requires a VMM logical network definition object, that you retrieve by using the **Get-SCLogicalNetworkDefinition** cmdlet.

## RELATED LINKS

[Get-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetwork.md)

[Get-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetworkDefinition.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[New-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetworkDefinition.md)

[New-SCSubnetVLan](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCSubnetVLan.md)

[Remove-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalNetworkDefinition.md)

