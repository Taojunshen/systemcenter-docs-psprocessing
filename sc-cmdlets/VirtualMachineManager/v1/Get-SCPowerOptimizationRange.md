---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCPowerOptimizationRange.md
schema: 2.0.0
ms.assetid: 2B012833-08F1-4506-9730-97B6C261C3F6
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCPowerOptimizationRange.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCPowerOptimizationRange.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCPowerOptimizationRange.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCPowerOptimizationRange

## SYNOPSIS
Gets the set of time ranges when power optimization will be used.

## SYNTAX

```
Get-SCPowerOptimizationRange -DynamicOptimizationConfiguration <HostGroupDOSettings>
 [-VMMServer <ServerConnection>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPowerOptimizationRange** cmdlet gets the set of power optimization time ranges that have been added to a dynamic optimization configuration.
During these time ranges, the hosts associated with the dynamic optimization configuration are turned on and off as needed.

## EXAMPLES

### Example 1: Get the power optmization time ranges associated with a dynamic optimization configuration
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $DOConfig = Get-SCDynamicOptimizationConfiguration -VMHostGroup $HostGroup 
PS C:\> $PORange = Get-SCPowerOptimizationRange -DynamicOptimizationConfiguration $DOConfig
PS C:\> $PORange
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the dynamic optimization configuration object for the host group stored in $HostGroup and stores the object in the $DOConfig variable.

The third command gets the power optimization ranges that have been added to the dynamic optimization configuration stored in $DOConfig.

The last command displays information about the power optimization ranges stored in $PORange.

## PARAMETERS

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

### PowerOptimizationRange
This cmdlet returns a **PowerOptimizationRange** object.

## NOTES

## RELATED LINKS

[Add-SCPowerOptimizationRange](xref:VirtualMachineManager/v1/Add-SCPowerOptimizationRange.md)

[Get-SCDynamicOptimizationConfiguration](xref:VirtualMachineManager/v1/Get-SCDynamicOptimizationConfiguration.md)

[Get-SCVMHostGroup](xref:VirtualMachineManager/v1/Get-SCVMHostGroup.md)

