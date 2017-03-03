---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 822FA44D-3282-404C-81A3-351C27F6FEC4
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTierTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTierTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTierTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCComputerTierTemplate

## SYNOPSIS
Modifies the properties of a computer tier template.

## SYNTAX

```
Set-SCComputerTierTemplate [-Name <String>] [-Description <String>] [-InstanceMaximumCount <Int32>]
 [-InstanceMinimumCount <Int32>] [-DefaultInstanceCount <Int32>] [-DeploymentOrder <Int32>] [-Tag <String>]
 [-ServicingOrder <Int32>] [-NumberOfUpgradeDomains <Int32>] [-BlockAutomaticMigration <Boolean>]
 [-EnableAvailabilitySet <Boolean>] -ComputerTierTemplate <ComputerTierTemplate> [-VMTemplate <Template>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCComputerTierTemplate** cmdlet modifies the properties of a computer tier template.

## EXAMPLES

### Example 1: Set the properties of a computer tier template
```
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $TierTemplate = Get-SCComputerTierTemplate -ServiceTemplate $ServiceTemplate
PS C:\> Set-SCComputerTierTemplate -ComputerTierTemplate $TierTemplate -DefaultInstanceCount 2 -InstanceMinimumCount 1
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the computer tier template object for the service template stored in $ServiceTemplate.

The last command sets properties for the computer template tier object stored in $TierTemplate.

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

### -ComputerTierTemplate
Specifies a computer tier template object.

```yaml
Type: ComputerTierTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
States a description for the specified object.

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

Required: False
Position: Named
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

### ComputerTierTemplate
This cmdlet returns a **ComputerTierTemplate** object.

## NOTES

## RELATED LINKS

[Add-SCComputerTierTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCComputerTierTemplate.md)

[Get-SCComputerTierTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTierTemplate.md)

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[Remove-SCComputerTierTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCComputerTierTemplate.md)

