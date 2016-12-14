---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMConfiguration.md
schema: 2.0.0
ms.assetid: 27B4C054-D7B6-40C7-86D2-D326E9D8FF40
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMConfiguration

## SYNOPSIS
Creates a virtual machine configuration from a virtual machine template.

## SYNTAX

### FromTemplateOnly (Default)
```
New-SCVMConfiguration -VMTemplate <Template> [-Name <String>] [-Description <String>] [-CostCenter <String>]
 [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### VMHostGroup
```
New-SCVMConfiguration -VMTemplate <Template> -Name <String> [-Description <String>] -VMHostGroup <HostGroup>
 [-CostCenter <String>] [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Cloud
```
New-SCVMConfiguration -VMTemplate <Template> -Name <String> [-Description <String>] -Cloud <Cloud>
 [-CostCenter <String>] [-CapabilityProfile <CapabilityProfile>]
 [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### ComputerTier
```
New-SCVMConfiguration -ComputerTier <ComputerTier> [-Name <String>] [-Description <String>]
 [-CostCenter <String>] [-ComputerName <String>]
 [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMConfiguration** cmdlet creates a virtual machine configuration from a virtual machine template.
The virtual machine configuration is used to specify instance-specific values to use when deploying the virtual machine configuration.

## EXAMPLES

### Example 1: Create a virtual machine configuration for placement of a virtual machine on a host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup -Name "Production"
PS C:\> $VMTemplate = Get-SCVMTemplate | where {$_.Name -eq "VMTemplate01"}
PS C:\> $VMConfig = New-SCVMConfiguration -VMTemplate $VMTemplate -VMHostGroup $HostGroup -CostCenter 1234 -Name "VMConfig01"
```

The first command gets the host group object named Production and stores the object in the $HostGroup variable.

The second command gets all virtual machine template objects, selects the template named VMTemplate01 and then stores the object in the $VMTemplate variable.

The last command creates a virtual machine configuration named VMConfig01 for the virtual machine template stored in $VMTemplate for deployment on the host group stored in $HostGroup, specifying a cost center value of 1234.

## PARAMETERS

### -AvailabilitySetNames
Specifies a list of availability set names.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CapabilityProfile
Specifies a capability profile object.

```yaml
Type: CapabilityProfile
Parameter Sets: Cloud
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
Parameter Sets: Cloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
Valid formats are: 

- FQDN
- IPv4 address
-  IPv6 address
- NetBIOS name

```yaml
Type: String
Parameter Sets: ComputerTier
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerTier
Specifies a computer tier object.

```yaml
Type: ComputerTier
Parameter Sets: ComputerTier
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CostCenter
Specifies the cost center for a virtual machine so that you can collect data about the allocation of virtual machines (or resources allocated to virtual machines) to make use of in your billing system.

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

### -Description
Specifies a description for the virtual machine configuration.

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
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: FromTemplateOnly, ComputerTier
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: VMHostGroup, Cloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnBehalfOfUser
Specifies the name of a user.
This cmdlet sets the on behalf of user as the user that this parameter specifies.

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
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
To obtain a user role object, use the Get-SCUserRole cmdlet.

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

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: VMHostGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: FromTemplateOnly, VMHostGroup, Cloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMConfiguration
This cmdlet returns a **VMConfiguration** object.

## NOTES
* Requires a VMM virtual machine template object, which you can obtain by using the Get-SCVMTemplate cmdlet.

## RELATED LINKS

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMConfiguration.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHostGroup.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMTemplate.md)

[Remove-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVMConfiguration.md)

[Set-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMConfiguration.md)

[Update-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Update-SCVMConfiguration.md)

