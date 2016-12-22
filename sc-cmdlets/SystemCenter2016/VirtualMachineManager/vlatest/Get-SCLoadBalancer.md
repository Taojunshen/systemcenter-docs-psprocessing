---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 686A4F37-AED6-4143-BD16-9191C837B5EC
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCLoadBalancer

## SYNOPSIS
Gets a load balancer object.

## SYNTAX

### GlobalList (Default)
```
Get-SCLoadBalancer [-VMMServer <ServerConnection>] [[-LoadBalancerAddress] <String>] [-Manufacturer <String>]
 [-Model <String>] [-All] [-LogicalNetwork <LogicalNetwork[]>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByHostGroup
```
Get-SCLoadBalancer [-VMMServer <ServerConnection>] [[-LoadBalancerAddress] <String>] [-Manufacturer <String>]
 [-Model <String>] -VMHostGroup <HostGroup> [-LogicalNetwork <LogicalNetwork[]>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByCloud
```
Get-SCLoadBalancer [-VMMServer <ServerConnection>] [[-LoadBalancerAddress] <String>] [-Manufacturer <String>]
 [-Model <String>] -Cloud <Cloud> [-LogicalNetwork <LogicalNetwork[]>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCLoadBalancer [-VMMServer <ServerConnection>] [[-LoadBalancerAddress] <String>] [-Manufacturer <String>]
 [-Model <String>] -ID <Guid> [-LogicalNetwork <LogicalNetwork[]>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AccessibleToCloudRootHostGroup
```
Get-SCLoadBalancer [-VMMServer <ServerConnection>] [[-LoadBalancerAddress] <String>] [-Manufacturer <String>]
 [-Model <String>] -CloudRootHostGroup <HostGroup[]> [-LogicalNetwork <LogicalNetwork[]>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AccessibleToCloudRootVMwareResourcePool
```
Get-SCLoadBalancer [-VMMServer <ServerConnection>] [[-LoadBalancerAddress] <String>] [-Manufacturer <String>]
 [-Model <String>] -CloudRootVMwareResourcePool <VmwResourcePool> [-LogicalNetwork <LogicalNetwork[]>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLoadBalancer** cmdlet gets one or more load balancer objects.

## EXAMPLES

### Example 1: Get all load balancers for a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup01" }
PS C:\> $LoadBalancers = Get-SCLoadBalancer -VMHostGroup $HostGroup
PS C:\> $LoadBalancers
```

The first command gets the host group object hamed HostGroup01 and stores the object in the $HostGroup variable.

The second command gets all load balancer objects accessible to the host group stored in $HostGroup and stores the objects in the $LoadBalancers variable.

The last command displays information about each of the load balancers stored in $LoadBalancers.

### Example 2: Get all load balancers of a given type for a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $LoadBalancers = Get-SCLoadBalancer -VMHostGroup $HostGroup -Manufacturer "LB Manufacturer" -Model "LB01"
PS C:\> $LoadBalancers
```

The first command gets the host group object named Production and stores the object in the $HostGroup variable.

The second command gets the load balancer objects with the specified manufacturer and model accessible to the host group stored in $HostGroup and stores the objects in the $LoadBalancers variable.

The last command displays information about each load balancer object stored in $LoadBalancers.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: GlobalList
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: ByCloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudRootHostGroup
Specifies a host group that is defined at the root level for a private cloud.

```yaml
Type: HostGroup[]
Parameter Sets: AccessibleToCloudRootHostGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudRootVMwareResourcePool
Specifies a VMware resource pool that is defined at the root level for a private cloud.

```yaml
Type: VmwResourcePool
Parameter Sets: AccessibleToCloudRootVMwareResourcePool
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ByID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerAddress
Specifies the fully qualified domain name (FQDN) or IP address of a load balancer.
Usual formats are FQDN, IPv4 or IPv6 addresses, but check with the load balancer manufacturer for the valid format for your load balancer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and VLANs that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Manufacturer
Specifies the name of the company that manufactured a physical device.
Valid characters include:

- Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen (-)
- Dot (.)
-  Single quote (')

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

### -Model
Specifies the model of a physical device.

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

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: ByHostGroup
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

### LoadBalancer
This cmdlet returns a **LoadBalancer** object.

## NOTES

## RELATED LINKS

[Add-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLoadBalancer.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Read-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCLoadBalancer.md)

[Remove-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancer.md)

[Set-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancer.md)

[Test-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCLoadBalancer.md)

