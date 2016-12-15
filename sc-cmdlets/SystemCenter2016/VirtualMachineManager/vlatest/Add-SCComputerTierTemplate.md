---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCComputerTierTemplate.md
schema: 2.0.0
ms.assetid: CA4CE93F-E7EA-4ADE-B0C7-8B81140EC2F4
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCComputerTierTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCComputerTierTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCComputerTierTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCComputerTierTemplate

## SYNOPSIS
Adds a computer tier template to a service template.

## SYNTAX

```
Add-SCComputerTierTemplate [-Name] <String> [-Description <String>] [-InstanceMaximumCount <Int32>]
 [-InstanceMinimumCount <Int32>] [-DefaultInstanceCount <Int32>] [-DeploymentOrder <Int32>] [-Tag <String>]
 [-ServicingOrder <Int32>] [-NumberOfUpgradeDomains <Int32>] -ServiceTemplate <ServiceTemplate>
 -VMTemplate <Template> [-BlockAutomaticMigration <Boolean>] [-EnableAvailabilitySet <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCComputerTierTemplate** cmdlet adds a computer tier template to a service template.
A computer tier template contains a virtual machine template that is used to create a virtual machine.

For information about service templates, type `Get-Help New-SCServiceTemplate -Detailed`.
For more information about virtual machine templates, type `Get-Help New-SCVMTemplate -Detailed`.

## EXAMPLES

### Example 1: Add a computer tier template to a service template
```
PS C:\>$WebTemplate = Get-SCVMTemplate | Where-Object { $_.Name -Eq "WebTemplate01" }
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> Add-SCComputerTierTemplate -ServiceTemplate $ServiceTemplate -VMTemplate $WebTemplate -Name "Web Tier" -DefaultInstanceCount 3 -InstanceMinimumCount 1 -InstanceMaximumCount 5 -DeploymentOrder 1 -ServicingOrder 1 -NumberOfUpgradeDomains 1
```

The first command gets the virtual machine template object named WebTemplate01 and stores the object in the $WebTemplate variable.

The second command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The last command adds a computer tier template to the service template stored in $ServiceTemplate.

## PARAMETERS

### -BlockAutomaticMigration
Indicates whether the computer can be automatically migrated.
When set to $True, automatic migration is blocked.
When set to $False, automatic migration is allowed.
The default value is $False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultInstanceCount
Specifies the default instance count for a computer tier that can be scaled out.
The default value is 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeploymentOrder
Specifies the order in which a computer tier, application host, or application is deployed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the computer tier template.

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

### -EnableAvailabilitySet
Indicates whether an availability set is generated on a service tier when a service is deployed.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceMaximumCount
Specifies the maximum number of virtual machines to which a service instance can scale out.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceMinimumCount
Specifies the minimum number of virtual machines to which a service instance can scale in.

```yaml
Type: Int32
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
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfUpgradeDomains
Specifies the number of upgrade domains for a computer tier that can be scaled out.
The default value is 1.

```yaml
Type: Int32
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

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServicingOrder
Specifies the order in which a computer tier or application host is serviced.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ComputerTierTemplate
This cmdlet returns a **ComputerTierTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTierTemplate.md)

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[Get-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md)

[Remove-SCComputerTierTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCComputerTierTemplate.md)

[Set-SCComputerTierTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTierTemplate.md)

