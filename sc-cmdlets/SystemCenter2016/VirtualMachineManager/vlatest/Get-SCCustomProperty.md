---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C3FD9539-4364-4DC7-9A67-B7243DECFED3
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomProperty.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomProperty.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomProperty.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCustomProperty

## SYNOPSIS
Gets a custom property definition from the VMM database.

## SYNTAX

### ID (Default)
```
Get-SCCustomProperty [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Name
```
Get-SCCustomProperty [-VMMServer <ServerConnection>] -Name <String> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Member
```
Get-SCCustomProperty [-VMMServer <ServerConnection>] -Member <CustomPropertyObjectType>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCustomProperty** cmdlet gets a custom property definition from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Get a custom property by its name
```
PS C:\> $CustomProp = Get-SCCustomProperty -Name "Cost Center"
PS C:\> $CustomProp
```

The first command gets the custom property object named Cost Center and stores the object in the $CustomProp variable.

The second command displays the properties of the custom property object stored in $CustomProp to the user.

### Example 2: Get all custom properties for a specific member type
```
PS C:\> Get-SCCustomProperty -Member "VM"
```

This command returns all custom properties that contain VM as a member.

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

### -Member
Specifies an object that is part of a group.
The acceptable values for this parameter are:

- VM
- Template
- VMHost
- HostCluster
- VMHostGroup
- ServiceTemplate
- ServiceInstance
- ComputerTier
- Cloud
- ProtectionUnit

```yaml
Type: CustomPropertyObjectType
Parameter Sets: Member
Aliases: 
Accepted values: VM, Template, VMHost, HostCluster, VMHostGroup, ServiceTemplate, ServiceInstance, ComputerTier, Cloud, ProtectionUnit

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
Parameter Sets: Name
Aliases: 

Required: True
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

[New-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCCustomProperty.md)

[Remove-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomProperty.md)

[Set-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomProperty.md)

