---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCustomProperty.md
schema: 2.0.0
ms.assetid: D4162B4A-CCD1-4E89-B14F-51A6CC450355
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCCustomProperty.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCCustomProperty.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCCustomProperty.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCCustomProperty

## SYNOPSIS
Creates a custom property definition in the VMM database.

## SYNTAX

```
New-SCCustomProperty [-Name] <String> [-Description <String>] -AddMember <CustomPropertyObjectType[]>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCCustomProperty** cmdlet creates a custom property definition in the Virtual Machine Manager (VMM) database.

You can create a custom property for the following object types: 

- VM
- Template
- VMHost
- HostCluster
- VMHostGroup
- ServiceTemplate
- ServiceInstance
- ComputerTier
- Cloud

## EXAMPLES

### Example 1: Create a custom property
```
PS C:\>$CustomProp = New-SCCustomProperty -Name "Cost Center" -AddMember "VM"
PS C:\> $CustomProp
```

The first command creates a custom property object named Cost Center with VM as a member and stores the object in the $CustomProp variable.

The second command displays the properties of the custom property object stored in $CustomProp to the user.

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
Parameter Sets: (All)
Aliases: 
Accepted values: VM, Template, VMHost, HostCluster, VMHostGroup, ServiceTemplate, ServiceInstance, ComputerTier, Cloud, ProtectionUnit

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the custom property definition.

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

[Get-SCCustomProperty](xref:VirtualMachineManager/v1/Get-SCCustomProperty.md)

[Remove-SCCustomProperty](xref:VirtualMachineManager/v1/Remove-SCCustomProperty.md)

[Set-SCCustomProperty](xref:VirtualMachineManager/v1/Set-SCCustomProperty.md)

