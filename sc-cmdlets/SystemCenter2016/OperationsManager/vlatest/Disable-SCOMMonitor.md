---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=191814
schema: 2.0.0
ms.assetid: 8289F011-C7B9-4216-A83B-2E205D2DF2F5
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Disable-SCOMMonitor.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Disable-SCOMMonitor.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Disable-SCOMMonitor.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCOMMonitor

## SYNOPSIS
Disables monitors in Operations Manager.

## SYNTAX

### Empty (Default)
```
Disable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [-ManagementPack] <ManagementPack> [-Enforce]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromInstance
```
Disable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [[-Instance] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGroup
```
Disable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [[-Group] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementPackClass
```
Disable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [-Class] <ManagementPackClass[]>
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCOMMonitor** cmdlet disables monitors in System Center 2016 - Operations Manager.
In Operations Manager, monitors define logic for determining the health of an object.
The cmdlet disables monitors by creating and saving overrides that modify the default behavior of a monitor.

## EXAMPLES

### Example 1: Disable a monitor
```
PS C:\>$MP = Get-SCOMManagementPack -DisplayName "My SQL MP Customization" | where {$_.Sealed -eq $False}
PS C:\> $Class = Get-SCOMClass -DisplayName "SQL DB Engine"
PS C:\> $Monitor = Get-SCOMMonitor -DisplayName "*memory*"
PS C:\> Disable-SCOMMonitor -Class $Class -ManagementPack $MP -Monitor $Monitor -Enforce
```

This example disables an Operations Manager monitor.

The first command uses the **Get-SCOMManagementPack** cmdlet to get a management pack object, and it stores the result in the variable named $MP.

The second command uses the **Get-SCOMClass** cmdlet to get a class object, and it stores the result in the variable named $Class.

The third command uses the **Get-SCOMMonitor** cmdlet to get a monitor object, and it stores the result in the variable named $Monitor.

The fourth command uses the **Disable-SCOMMonitor** cmdlet to disable the monitor by using the *Enforce* parameter.
The cmdlet stores the override in the variable named $MP.

## PARAMETERS

### -Class
Specifies an array of class objects.
For information about how to get a class object, type "`Get-Help Get-SCOMClass`".

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
Indicates that the cmdlet sets the **Enforce** property on the override to $True.

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
Specifies an array of one or more group objects.
For information about how to get a group object, type "`Get-Help Get-SCOMGroup`".

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
Specifies an array of class instance objects.
The *Instance* parameter also accepts group objects as input.
For information about how to get a class instance object, type "`Get-Help Get-SCOMClassInstance`".

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
Specifies one or more management pack objects where you can save the override.
If the monitor is in an unsealed management pack, you must save the overrides into the same management pack.
For information about how to get a management pack object, type "`Get-Help Get-SCOMManagementPack`".

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

### -Monitor
Specifies an array of one or more monitor objects.
For information about how to get a monitor object, type "`Get-Help Get-SCOMMonitor`".

```yaml
Type: ManagementPackMonitor[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Enable-SCOMMonitor](xref:SystemCenter2016/OperationsManager/vlatest/Enable-SCOMMonitor.md)

[Get-SCOMMonitor](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMMonitor.md)

