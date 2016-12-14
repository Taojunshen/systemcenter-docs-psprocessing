---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=191813
schema: 2.0.0
ms.assetid: CBC17C1C-7ED4-4330-A1D5-BFE59E788497
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Enable-SCOMMonitor.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Enable-SCOMMonitor.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Enable-SCOMMonitor.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCOMMonitor

## SYNOPSIS
Enables monitors in Operations Manager.

## SYNTAX

### Empty (Default)
```
Enable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [-ManagementPack] <ManagementPack> [-Enforce]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGroup
```
Enable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [[-Group] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementPackClass
```
Enable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [-Class] <ManagementPackClass[]>
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromInstance
```
Enable-SCOMMonitor [-Monitor] <ManagementPackMonitor[]> [[-Instance] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCOMMonitor** cmdlet enables monitors in System Center 2016 - Operations Manager.
In Operations Manager, monitors define logic for determining the health of an object.

## EXAMPLES

### Example 1: Enable a monitor
```
PS C:\>$MP = Get-SCOMManagementPack -Displayname "My SQL MP Customization" | where {$_.Sealed -eq $False}
PS C:\> $Class = Get-SCOMClass -DisplayName "SQL DB Engine"
PS C:\> $Monitor = Get-SCOMMonitor -DisplayName "*memory*"
PS C:\> Enable-SCOMMonitor -Class $Class -ManagementPack $MP -Monitor $Monitor -Enforce
```

This example enables an Operations Manager monitor.

The first command uses the **Get-SCOMManagementPack** cmdlet to get a management pack object, and it stores the result in the variable named $MP.

The second command uses the **Get-SCOMClass** cmdlet to get a class object, and it stores the result in the variable named $Class.

The third command uses the **Get-SCOMMonitor** cmdlet to get a monitor object, and it stores the result in the variable named $Monitor.

The fourth command uses the **Enable-SCOMMonitor** cmdlet to enable the monitor by using the *Enforce* parameter.

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
Specifies an array of group objects.
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
Specifies an array of monitor objects.
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
Indicates that the cmdlet creates or modifies an object that a command can use in a pipeline.
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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMClassInstance.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMGroup.md)

[Disable-SCOMMonitor](xref:SystemCenter2016/OperationsManager/v1.0/Disable-SCOMMonitor.md)

[Get-SCOMMonitor](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMMonitor.md)

