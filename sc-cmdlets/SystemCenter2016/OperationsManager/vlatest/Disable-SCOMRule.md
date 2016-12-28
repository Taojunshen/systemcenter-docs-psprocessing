---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B49B1031-F02D-4288-B5ED-27652318878F
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Disable-SCOMRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Disable-SCOMRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Disable-SCOMRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCOMRule

## SYNOPSIS
Creates and saves overrides that disable monitoring rules.

## SYNTAX

### Empty (Default)
```
Disable-SCOMRule [-Rule] <ManagementPackRule[]> [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGroup
```
Disable-SCOMRule [-Rule] <ManagementPackRule[]> [[-Group] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromInstance
```
Disable-SCOMRule [-Rule] <ManagementPackRule[]> [[-Instance] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementPackClass
```
Disable-SCOMRule [-Rule] <ManagementPackRule[]> [-Class] <ManagementPackClass[]>
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCOMRule** cmdlet creates and saves overrides that disable System Center 2016 - Operations Manager monitoring rules.
After you disable a monitoring rule, Operations Manager no longer raises alerts for the systems specified in the rules.

## EXAMPLES

### Example 1: Disable a monitoring rule
```
PS C:\>$MP = Get-SCOMManagementPack -DisplayName "My SQL MP Customization" | where {$_.Sealed -eq $False}
PS C:\> $Class = Get-SCOMClass -DisplayName "SQL DB Engine"
PS C:\> $Rule = Get-SCOMRule -DisplayName "*Events/sec"
PS C:\> Disable-SCOMRule -Class $Class -Rule $Rule -ManagementPack $MP -Enforce
```

This example disables a monitoring rule for a management pack.

The first three commands get an unsealed management pack object, a class object, and a monitoring rule object and then store the objects in the $MP, $Class, and $Rule variables, respectively.

The last command disables the monitoring rule stored in $Rule for the class object stored in $Class.
The command stores the override in the management pack stored in $MP.
The command specifies the *Enforce* parameter.

## PARAMETERS

### -Class
Specifies an array of management pack objects that represent classes for which the cmdlet disables rules.
To obtain a **ManagementPackClass** object, use the **Get-SCOMClass** cmdlet.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackClass
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enforce
Indicates that Operations Manager enforces the override that disables the monitoring rules.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Specifies an array of monitoring objects that represent groups.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.
The cmdlet disables rules for these groups.

```yaml
Type: MonitoringObject[]
Parameter Sets: FromGroup
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an array of monitoring objects that represent instances.
To obtain instances, use the **Get-SCOMClassInstance** cmdlet.
The cmdlet disables rules for these instances.
This parameter also accepts group objects.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.

```yaml
Type: MonitoringObject[]
Parameter Sets: FromInstance
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies a management pack object that stores overrides.
To obtain a management pack object, use the **Get-SCOMManagementPack** cmdlet.
If the rule is in an unsealed management pack, you must save the override into the same management pack.

```yaml
Type: ManagementPack
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
Specifies an array of rules as **ManagementPackRule** objects.
To obtain a **ManagementPackRule** object, use the **Get-SCOMRule** cmdlet.

```yaml
Type: ManagementPackRule[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

## NOTES

## RELATED LINKS

[Enable-SCOMRule](xref:SystemCenter2016/OperationsManager/vlatest/Enable-SCOMRule.md)

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

[Get-SCOMRule](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRule.md)

