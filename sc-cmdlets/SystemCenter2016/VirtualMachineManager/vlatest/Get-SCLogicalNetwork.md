---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F019FC47-F5F0-4520-A002-A69C25A5BC3D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCLogicalNetwork

## SYNOPSIS
Gets a logical network object.

## SYNTAX

### GlobalList (Default)
```
Get-SCLogicalNetwork [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByHost
```
Get-SCLogicalNetwork [-VMMServer <ServerConnection>] [[-Name] <String>] -VMHost <Host>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByCloud
```
Get-SCLogicalNetwork [-VMMServer <ServerConnection>] [[-Name] <String>] -Cloud <Cloud>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByHostGroup
```
Get-SCLogicalNetwork [-VMMServer <ServerConnection>] [[-Name] <String>] -VMHostGroup <HostGroup>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCLogicalNetwork [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AccessibleToCloudRootHostGroup
```
Get-SCLogicalNetwork [-VMMServer <ServerConnection>] [[-Name] <String>] -CloudRootHostGroup <HostGroup[]>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AccessibleToCloudRootVMwareResourcePool
```
Get-SCLogicalNetwork [-VMMServer <ServerConnection>] [[-Name] <String>]
 -CloudRootVMwareResourcePool <VmwResourcePool> [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLogicalNetwork** cmdlet retrieves one or more Virtual Machine Manager (VMM) logical network objects.

## EXAMPLES

### Example 1: Retrieve all available logical networks for a specified host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup01" }
PS C:\> Get-SCLogicalNetwork -VMHostGroup $HostGroup
```

The first command gets the host group object at the path "All Hosts\HostGroup01" and stores the object in the $HostGroup variable.

The second command gets all of the logical networks for the host group stored in $HostGroup and displays information about each logical network to the user.

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

Required: False
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

### -VMHost
Specifies an array of virtual machine host objects.

```yaml
Type: Host
Parameter Sets: ByHost
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

### LogicalNetwork
This cmdlet returns a **LogicalNetwork** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[New-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalNetwork.md)

[Remove-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalNetwork.md)

[Set-SCLogicalNetwork](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalNetwork.md)

