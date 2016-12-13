---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMSubnet.md
schema: 2.0.0
ms.assetid: 2B8C4DAE-F390-4215-821A-BE1F81401433
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVMSubnet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVMSubnet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVMSubnet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMSubnet

## SYNOPSIS
Creates a virtual machine subnet.

## SYNTAX

### WindowsNetworkVirtualization (Default)
```
New-SCVMSubnet [-VMMServer <ServerConnection>] [-Name] <String> [[-Description] <String>]
 -SubnetVLan <SubnetVLan[]> -VMNetwork <VMNetwork> [-VMSubnetID <UInt32>] [-MaxNumberOfPorts <UInt32>]
 [-PortACL <PortACL>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Vlan
```
New-SCVMSubnet [-VMMServer <ServerConnection>] [-Name] <String> [[-Description] <String>]
 -SubnetVLan <SubnetVLan[]> -VMNetwork <VMNetwork> -LogicalNetworkDefinition <LogicalNetworkDefinition>
 [-MaxNumberOfPorts <UInt32>] [-PortACL <PortACL>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMSubnetExternal
```
New-SCVMSubnet [-VMMServer <ServerConnection>] [-Name] <String> [[-Description] <String>] [-VMSubnetExternal]
 -VMNetwork <VMNetwork> [-MaxNumberOfPorts <UInt32>] [-PortACL <PortACL>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMSubnet** cmdlet creates a virtual machine subnet.
A virtual machine subnet is an IP subnet that is associated with a virtual machine network.

When you create a virtual machine subnet, you must provide **SubNetVLan** and **VMNetwork** objects.
To create the **SubnetVLan** object, use the New-SCSubnetVLan cmdlet.
To obtain a **VMNetwork** object, use the Get-SCVMNetwork cmdlet.
The logical network used by the virtual machine network must be enabled for network virtualization.

## EXAMPLES

### Example 1: Create a virtual machine subnet that uses NVGRE as the encapsulation mechanism
```
PS C:\>$SubNetVLan = New-SCSubnetVLan -Subnet "192.168.3.0/24"
PS C:\> $VMNetwork = Get-SCVMNetwork -Name "VMNetwork01"
PS C:\> New-SCVMSubnet -Name "VMSubnet01" -SubnetVLan $SubnetVLan -VMNetwork $VMNetwork
```

The first command creates a subnet VLan object and stores the object in the $SubNetVLan variable.

The second command gets the virtual machine network object named VMNetwork 01 and stores the object in the $VMNetwork variable.

The last command creates a virtual machine subnet with the name VMSubnet01 using the subnet VLan stored in $SubnetVLan and the virtual machine network stored in $VMNetwork.

## PARAMETERS

### -Description
Specifies a description for a virtual machine subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

### -LogicalNetworkDefinition
Specifies a logical network definition (also known as a network site) that contains the subnet that the IP address pool serves as specified by the *SubnetVLan* parameter.

```yaml
Type: LogicalNetworkDefinition
Parameter Sets: Vlan
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxNumberOfPorts
Specifies the maximum number of ports supported by the virtual machine subnet.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -PortACL
Specifies a port access control list (ACL).

```yaml
Type: PortACL
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

For information about creating a SubnetVLan, type `Get-Help New-SCSubNetVLan`.

```yaml
Type: SubnetVLan[]
Parameter Sets: WindowsNetworkVirtualization, Vlan
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

### -VMNetwork
Specifies a virtual machine network object.

To get a virtual machine network object, use the Get-SCVMNetwork cmdlet.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSubnetExternal
Indicates that the virtual machine network is able to communicate with other networks.

```yaml
Type: SwitchParameter
Parameter Sets: VMSubnetExternal
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSubnetID
Specifies the ID of a virtual machine subnet.

```yaml
Type: UInt32
Parameter Sets: WindowsNetworkVirtualization
Aliases: 

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

## NOTES

## RELATED LINKS

[Get-SCVMSubnet](xref:VirtualMachineManager/v1/Get-SCVMSubnet.md)

[New-SCSubnetVLan](xref:VirtualMachineManager/v1/New-SCSubnetVLan.md)

[Remove-SCVMSubnet](xref:VirtualMachineManager/v1/Remove-SCVMSubnet.md)

[Set-SCVMSubnet](xref:VirtualMachineManager/v1/Set-SCVMSubnet.md)

