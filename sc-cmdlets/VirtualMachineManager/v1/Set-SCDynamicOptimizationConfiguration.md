---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCDynamicOptimizationConfiguration.md
schema: 2.0.0
ms.assetid: 7186B1D3-A73A-4919-BF8A-222F4A3838C1
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCDynamicOptimizationConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCDynamicOptimizationConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCDynamicOptimizationConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCDynamicOptimizationConfiguration

## SYNOPSIS
Configures dynamic optimization for a host group.

## SYNTAX

### ToInherit
```
Set-SCDynamicOptimizationConfiguration -Inherit <Boolean>
 -DynamicOptimizationConfiguration <HostGroupDOSettings> [-VMMServer <ServerConnection>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ToManual
```
Set-SCDynamicOptimizationConfiguration [-ManualMode] -DynamicOptimizationConfiguration <HostGroupDOSettings>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ToAutomatic
```
Set-SCDynamicOptimizationConfiguration [-AutomaticMode] -DynamicOptimizationConfiguration <HostGroupDOSettings>
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromValues
```
Set-SCDynamicOptimizationConfiguration -DynamicOptimizationConfiguration <HostGroupDOSettings>
 [-Aggressiveness <Byte>] [-FrequencyMinutes <UInt32>] [-EnablePowerOptimization <Boolean>]
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCDynamicOptimizationConfiguration** cmdlet configures dynamic optimization for a host group.

## EXAMPLES

### Example 1: Enable automatic mode for a dynamic optimization configuration
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $DOConfig = Get-SCDynamicOptimizationConfiguration -VMHostGroup $HostGroup
PS C:\> Set-SCDynamicOptimizationConfiguration -DynamicOptimizationConfiguration $DOConfig -AutomaticMode
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the dynamic optimization configuration object for the host group stored in $HostGroup and stores the object in the $DOConfig variable.

The last command enables automatic mode for the dynamic optimization configuration stored in $DOConfig.

### Example 2: Enable power optimization for a host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $DOConfig = Get-SCDynamicOptimizationConfiguration -VMHostGroup $HostGroup 
PS C:\> Set-SCDynamicOptimizationConfiguration -DynamicOptimizationConfiguration $DOConfig -EnablePowerOptimization $True
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the dynamic optimization configuration object for the host group stored in $HostGroup and stores the object in the $DOConfig variable.

The last command enables power optimization for the dynamic optimization configuration stored in $DOConfig.

## PARAMETERS

### -Aggressiveness
Specifies the level of improvement required before migrating a virtual machine from one host to another in order to load balance virtual machines.

The higher the aggressiveness, the more resulting live migrations; the lower the aggressiveness, the fewer resulting live migrations.
Valid values are: 1 through 5.
The default value is 3 (Medium).

```yaml
Type: Byte
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticMode
Indicates that dynamic optimization automatically migrates virtual machines in order to load balance.

```yaml
Type: SwitchParameter
Parameter Sets: ToAutomatic
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

### -EnablePowerOptimization
Enables power optimization when set to $True.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrequencyMinutes
Specifies the frequency, in minutes, at which dynamic optimization will run when set to automatic mode.

```yaml
Type: UInt32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Inherit
Indicates whether settings are inherited from the parent host group.

```yaml
Type: Boolean
Parameter Sets: ToInherit
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

### -ManualMode
Indicates that dynamic optimization will not run automatically.

```yaml
Type: SwitchParameter
Parameter Sets: ToManual
Aliases: 

Required: True
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

### DynamicOptimizationConfiguration
This cmdlet returns a **DynamicOptimizationConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCDynamicOptimizationConfiguration](xref:VirtualMachineManager/v1/Get-SCDynamicOptimizationConfiguration.md)

[Get-SCVMHostGroup](xref:VirtualMachineManager/v1/Get-SCVMHostGroup.md)

