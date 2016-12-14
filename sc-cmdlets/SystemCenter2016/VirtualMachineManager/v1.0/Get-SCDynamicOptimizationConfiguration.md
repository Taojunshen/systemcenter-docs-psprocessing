---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMHostGroup.md
schema: 2.0.0
ms.assetid: 8772F0DF-9098-490B-9DA5-70D68A99E0E2
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCDynamicOptimizationConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCDynamicOptimizationConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCDynamicOptimizationConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDynamicOptimizationConfiguration

## SYNOPSIS
Gets the dynamic optimization configuration for a host group.

## SYNTAX

```
Get-SCDynamicOptimizationConfiguration -VMHostGroup <HostGroup> [-VMMServer <ServerConnection>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDynamicOptimizationConfiguration** cmdlet gets the dynamic optimization configuration for a host group.

## EXAMPLES

### Example 1: Get the Dynamic Optimization settings for a host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $DOConfig = Get-SCDynamicOptimizationConfiguration -VMHostGroup $HostGroup
PS C:\> $DOConfig
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the dynamic optimization configuration settings for the host group stored in $HostGroup and stores the settings in the $DOConfig variable.

The last command displays the settings stored in $DOConfig to the user.

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

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
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

### DynamicOptimizationConfiguration
This cmdlet returns a **DynamicOptimizationConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHostGroup.md)

[Set-SCDynamicOptimizationConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCDynamicOptimizationConfiguration.md)

