---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCDynamicOptimizationConfiguration.md
schema: 2.0.0
ms.assetid: 2968C962-3F3B-4A9E-B2EA-473CCA5A7B5C
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Add-SCPowerOptimizationRange.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Add-SCPowerOptimizationRange.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Add-SCPowerOptimizationRange.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCPowerOptimizationRange

## SYNOPSIS
Adds a time range to the power optimization schedule in a dynamic optimization configuration.

## SYNTAX

```
Add-SCPowerOptimizationRange -DynamicOptimizationConfiguration <HostGroupDOSettings> -EndHour <Int32>
 -BeginHour <Int32> -WeeklyScheduleDayOfWeek <Int32> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCPowerOptimizationRange** cmdlet adds a time range to the power optimization schedule in the dynamic optimization configuration.
Power optimization is implemented only during the time ranges that have been added.
Otherwise, hosts associated with the dynamic optimization configuration are turned on.

## EXAMPLES

### Example 1: Add a time range for power optmization to a dynamic optimization configuration
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $DOConfig = Get-SCDynamicOptimizationConfiguration -VMHostGroup $HostGroup
PS C:\> Add-SCPowerOptimizationRange -DynamicOptimizationConfiguration $DOConfig -BeginHour 19 -EndHour 23 -WeeklyScheduleDayOfWeek 0
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the dynamic optimization configuration object for the host group stored in $HostGroup and stores the object in the $DOConfig variable.

The last command adds a time range to the dynamic optimization configuration stored in $DOConfig.

## PARAMETERS

### -BeginHour
Specifies the hour of the day that power optimization begins.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicOptimizationConfiguration
Specifies a dynamic optimization configuration object.

```yaml
Type: HostGroupDOSettings
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EndHour
Specifies the hour of the day that power optimization ends.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

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

### -WeeklyScheduleDayOfWeek
Specifies one or more days of the week to run a job.
The default value is the current day of the week.

Valid values to specify an individual day by using a string: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday.

Valid values to specify a set of days in a week: Any set of two or more days separated by commas.

Valid values to specify an individual day by using an integer: 1, 2, 3, 4, 5, 6, 7.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PowerOptimizationSchedule
This cmdlet returns a **PowerOptimizationSchedule** object.

## NOTES

## RELATED LINKS

[Get-SCDynamicOptimizationConfiguration](xref:VirtualMachineManager/v1/Get-SCDynamicOptimizationConfiguration.md)

[Get-SCPowerOptimizationRange](xref:VirtualMachineManager/v1/Get-SCPowerOptimizationRange.md)

[Get-SCVMHostGroup](xref:VirtualMachineManager/v1/Get-SCVMHostGroup.md)

