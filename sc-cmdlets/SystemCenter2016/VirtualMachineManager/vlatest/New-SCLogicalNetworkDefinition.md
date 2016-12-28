---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AF8CFCC3-9D63-4C9B-B987-C7BE56E59BCB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetworkDefinition.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetworkDefinition.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetworkDefinition.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLogicalNetworkDefinition

## SYNOPSIS
Creates a definition for a logical network that can be associated with one or more host groups.

## SYNTAX

```
New-SCLogicalNetworkDefinition [-VMMServer <ServerConnection>] -Name <String> -LogicalNetwork <LogicalNetwork>
 -SubnetVLan <SubnetVLan[]> -VMHostGroup <HostGroup[]> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLogicalNetworkDefinition** cmdlet creates a definition for a Virtual Machine Manager (VMM) logical network.
The logical network can be associated with one or more host groups.
A logical network definition is also called a network site.

After you create a new logical network, use the logical network definition to assign IP subnets and virtual local area networks (VLANs) to the logical network.
For information about creating logical networks, type: `Get-Help New-SCLogicalNetwork -Detailed`.

## EXAMPLES

### Example 1: Create a logical network definition for a logical network
```
PS C:\> $LogicalNetwork = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> $HostGroup =@()
PS C:\> $HostGroup += Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup01" }
PS C:\> $Hostgroup += Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $SubnetVLAN = @()
PS C:\> $SubnetVLAN += New-SCSubnetVLAN -Subnet 10.0.0.0/24 -VLAN 25
PS C:\> $SubnetVLAN += New-SCSubnetVLAN -Subnet FD4A:29CD:184F:3A2C::/64 -VLAN 25
PS C:\> New-SCLogicalNetworkDefinition -Name "Logical Network Definition 01" -LogicalNetwork $LogicalNetwork -VMHostGroup $HostGroup -SubnetVLAN $SubnetVLAN
```

The first command gets the logical network named LogicalNetwork01.

The second command creates a host group array and stores it in the $HostGroup variable.

The third and fourth commands retrieve the host groups named HostGroup01 and Production, and adds them to the $HostGroup array.

The fifth command creates a subnet VLAN array and stores it in the $SubnetVLAN variable.

The sixth and seventh commands create SubnetVLAN objects with the specified subnet and VLAN values and then stores the objects in the $SubnetVLAN array.

The final command creates a logical network definition named Logical Network Definition 01 for the logical network object stored in the $LogicalNetwork variable by using the objects stored in the $HostGroup and $SubnetVLAN arrays.

## PARAMETERS

### -JobVariable
Specifies the name of a variable in which to track and store job progress.

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

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and VLANs that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
Parameter Sets: (All)
Aliases: 

Required: True
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

### -SubnetVLan
Specifies one or more IP subnet and VLAN sets.

For information about creating a SubnetVLan, type: `Get-Help New-SCSubNetVLan`.

```yaml
Type: SubnetVLan[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup[]
Parameter Sets: (All)
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
* This cmdlet requires a VMM logical network object, which you retrieve by using the **Get-SCLogicalNetwork** cmdlet and a VMM host group object which you retrieve by using the **Get-SCVMHostGroup** cmdlet.

## RELATED LINKS

[Get-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetwork.md)

[Get-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetworkDefinition.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[New-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetwork.md)

[New-SCSubnetVLan](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCSubnetVLan.md)

[Remove-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalNetworkDefinition.md)

[Set-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetworkDefinition.md)

