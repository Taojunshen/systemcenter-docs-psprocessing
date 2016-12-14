---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCustomProperty.md
schema: 2.0.0
ms.assetid: 8B062BCD-40A6-4763-9C61-26C22EED4D1B
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCCustomProperty.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCCustomProperty.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCCustomProperty.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCCustomProperty

## SYNOPSIS
Modifies the properties of a custom property.

## SYNTAX

### __AllParameterSets (Default)
```
Set-SCCustomProperty [-VMMServer <ServerConnection>] -CustomProperty <CustomProperty> [-Name <String>]
 [-Description <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddMembers
```
Set-SCCustomProperty [-VMMServer <ServerConnection>] -CustomProperty <CustomProperty> [-Name <String>]
 [-Description <String>] -AddMember <CustomPropertyObjectType[]> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### RemoveMembers
```
Set-SCCustomProperty [-VMMServer <ServerConnection>] -CustomProperty <CustomProperty> [-Name <String>]
 [-Description <String>] -RemoveMember <CustomPropertyObjectType[]> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCCustomProperty** cmdlet modifies the properties of a custom property.
Properties that can be modified include the following:  

- Description of the custom property
- Name of the custom property
- Add a member to the custom property
- Remove a member from the custom property

For information about creating a custom property, type `Get-Help New-SCCustomProperty -Detailed`.

## EXAMPLES

### Example 1: Add a member to a custom property
```
PS C:\>$CustomProp = Get-SCCustomProperty -Name "Cost Center"
PS C:\> Set-SCCustomProperty -CustomProperty $CustomProp -AddMember "VMHost"
```

The first command gets the custom property object named Cost Center and stores the object in the $CustomProp variable.

The second command adds the VMHost member to the custom property stored in $CustomProp.

### Example 2: Remove a member from a custom property
```
PS C:\>$CustomProp = Get-SCCustomProperty -Name "Cost Center"
PS C:\> Set-SCCustomProperty -CustomProperty $CustomProp -RemoveMember "VM"
```

The first command gets the custom property object named Cost Center and stores the object in the $CustomProp variable.

The second command removes the VM member from the custom property object stored in $CustomProp.

## PARAMETERS

### -AddMember
Specifies an array of members that this cmdlet adds to an object that has the concept of members, such as a group.
For example, this cmdlet can add one or more Active Directory® Domain Services domain users or groups to a user role.
Specify members in the following formats: 

- Domain\User
- User
- User@Domain
- Domain\LabGroupAlias
- LabGroupAlias

 The lab group alias is an Active Directory Domain Services security group, not an email alias.

```yaml
Type: CustomPropertyObjectType[]
Parameter Sets: AddMembers
Aliases: 
Accepted values: VM, Template, VMHost, HostCluster, VMHostGroup, ServiceTemplate, ServiceInstance, ComputerTier, Cloud, ProtectionUnit

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomProperty
Specifies a custom property object.

```yaml
Type: CustomProperty
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
Specifies a description for the specified object.

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

### -RemoveMember
Specifies an array of members that this cmdlet removes from a VMM object that has the concept of membership, such as a group.
For example, this cmdlet can removes one or more Active Directory Domain Services domain users or groups from a user role.
Specify members in the following formats: 

- Domain\User
- User
- User@Domain
- Domain\LabGroupAlias
- LabGroupAlias

 The lab group alias is an Active Directory Domain Services security group, not an email alias.

```yaml
Type: CustomPropertyObjectType[]
Parameter Sets: RemoveMembers
Aliases: 
Accepted values: VM, Template, VMHost, HostCluster, VMHostGroup, ServiceTemplate, ServiceInstance, ComputerTier, Cloud, ProtectionUnit

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

[Get-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCCustomProperty.md)

[New-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCCustomProperty.md)

[Remove-SCCustomProperty](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCCustomProperty.md)

