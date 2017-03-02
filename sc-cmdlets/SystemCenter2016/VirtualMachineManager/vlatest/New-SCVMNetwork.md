---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C718267B-761E-4F83-81F2-82C8953682FD
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCVMNetwork

## SYNOPSIS
Creates a virtual machine network.

## SYNTAX

### Default (Default)
```
New-SCVMNetwork [-UserRole <UserRole>] [-VMMServer <ServerConnection>] [-Name] <String>
 [[-Description] <String>] -LogicalNetwork <LogicalNetwork> [-RoutingDomainId <Guid>]
 [-PAIPAddressPoolType <VMNetworkIPAddressPoolType>] [-CAIPAddressPoolType <VMNetworkIPAddressPoolType>]
 [-Owner <String>] [-PortACL <PortACL>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### IsolationType
```
New-SCVMNetwork [-UserRole <UserRole>] [-VMMServer <ServerConnection>] [-Name] <String>
 [[-Description] <String>] -LogicalNetwork <LogicalNetwork> [-RoutingDomainId <Guid>]
 -IsolationType <VMNetworkType> [-PAIPAddressPoolType <VMNetworkIPAddressPoolType>]
 [-CAIPAddressPoolType <VMNetworkIPAddressPoolType>] [-Owner <String>] [-PortACL <PortACL>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AutoCreate
```
New-SCVMNetwork [-UserRole <UserRole>] [-VMMServer <ServerConnection>] [-Name] <String>
 [[-Description] <String>] -LogicalNetwork <LogicalNetwork> [-RoutingDomainId <Guid>]
 [-PAIPAddressPoolType <VMNetworkIPAddressPoolType>] [-CAIPAddressPoolType <VMNetworkIPAddressPoolType>]
 [-AutoCreateSubnet] [-Owner <String>] [-NetworkManager <VirtualSwitchExtensionManager>] [-PortACL <PortACL>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### External
```
New-SCVMNetwork [-UserRole <UserRole>] [-VMMServer <ServerConnection>] [-Name] <String>
 [[-Description] <String>] -LogicalNetwork <LogicalNetwork> [-RoutingDomainId <Guid>]
 [-PAIPAddressPoolType <VMNetworkIPAddressPoolType>] [-CAIPAddressPoolType <VMNetworkIPAddressPoolType>]
 -ExternalName <String> [-Owner <String>] [-PortACL <PortACL>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ExternalVMNetwork
```
New-SCVMNetwork [-UserRole <UserRole>] [-VMMServer <ServerConnection>] [-Name] <String>
 [[-Description] <String>] -LogicalNetwork <LogicalNetwork> [-RoutingDomainId <Guid>]
 [-PAIPAddressPoolType <VMNetworkIPAddressPoolType>] [-CAIPAddressPoolType <VMNetworkIPAddressPoolType>]
 [-ExternalVMNetwork] [-Owner <String>] [-NetworkManager <VirtualSwitchExtensionManager>] [-PortACL <PortACL>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMNetwork** cmdlet creates a virtual machine network.
Virtual machine networks support multiple methods of isolation: No isolation, network virtualization, external, and VLAN.
The type of isolation used by the VM network depends on the specified logical network.
Virtual Machine Manager (VMM) uses the IP address pools that are associated with a virtual machine network to assign customer addresses to virtual machines.

The customer address is visible to the virtual machine and is used by customers to communicate with the virtual machine.

You must provide a logical network object when you create a virtual machine network.
To obtain a logical network object, use the **Get-SCLogicalNetwork** cmdlet.

## EXAMPLES

### Example 1: Create a virtual machine network
```
PS C:\> $LogNet = Get-SCLogicalNetwork -Name "LogicalNetwork01"
PS C:\> New-SCVMNetwork -Name "VMNetwork01" -LogicalNetwork $LogNet
```

The first command gets the logical network object named LogicalNetwork01 and stores the object in the $LogNet variable.

The second command creates a VM network named VMNetwork01 with the logical network LogicalNetwork01.

## PARAMETERS

### -AutoCreateSubnet
Indicates that a subnet is automatically created.

```yaml
Type: SwitchParameter
Parameter Sets: AutoCreate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CAIPAddressPoolType
Specifies an address pool type.
Valid values are: IPV4, IPV6.

```yaml
Type: VMNetworkIPAddressPoolType
Parameter Sets: (All)
Aliases: 
Accepted values: IPV4, IPV6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the virtual machine network.

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

### -ExternalName
Specifies an external name for an object.

```yaml
Type: String
Parameter Sets: External
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalVMNetwork
Indicates that the virtual machine network is external.

```yaml
Type: SwitchParameter
Parameter Sets: ExternalVMNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsolationType
Specifies an isolation type for a virtual machine network.
The acceptable values for this parameter are:

- NoIsolation
- WindowsNetworkVirtualization
- External
- VLANNetwork

```yaml
Type: VMNetworkType
Parameter Sets: IsolationType
Aliases: 
Accepted values: NoIsolation, WindowsNetworkVirtualization, External, VLANNetwork

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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkManager
Specifies a virtual switch extension manager.

```yaml
Type: VirtualSwitchExtensionManager
Parameter Sets: AutoCreate, ExternalVMNetwork
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account. 

- Example format: `-Owner "Contoso\PattiFuller"`
- Example format: `-Owner "PattiFuller@Contoso"`

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

### -PAIPAddressPoolType
Specifies an address pool type.
Valid values are: IPV4, IPV6.

```yaml
Type: VMNetworkIPAddressPoolType
Parameter Sets: (All)
Aliases: 
Accepted values: IPV4, IPV6

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
Specifies a port ACL object.

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

### -RoutingDomainId
Specifies the ID of a routing domain in the form of a GUID.

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

### -UserRole
Specifies a user role object.

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

## NOTES

## RELATED LINKS

[Get-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetwork.md)

[Get-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMNetwork.md)

[Remove-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMNetwork.md)

[Set-SCVMNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMNetwork.md)

