---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=191815
schema: 2.0.0
ms.assetid: 7306EB0D-A2BA-4E90-9532-5FC55EFEB4E3
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Enable-SCOMDiscovery.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Enable-SCOMDiscovery.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Enable-SCOMDiscovery.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCOMDiscovery

## SYNOPSIS
Enables Operations Manager discoveries.

## SYNTAX

### Empty (Default)
```
Enable-SCOMDiscovery [-Discovery] <ManagementPackDiscovery[]> [-ManagementPack] <ManagementPack> [-Enforce]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromInstance
```
Enable-SCOMDiscovery [-Discovery] <ManagementPackDiscovery[]> [[-Instance] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromGroup
```
Enable-SCOMDiscovery [-Discovery] <ManagementPackDiscovery[]> [[-Group] <MonitoringObject[]>]
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementPackClass
```
Enable-SCOMDiscovery [-Discovery] <ManagementPackDiscovery[]> [-Class] <ManagementPackClass[]>
 [-ManagementPack] <ManagementPack> [-Enforce] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCOMDiscovery** cmdlet enables System Center 2016 - Operations Manager discoveries.
The cmdlet creates and saves overrides for specified discoveries that enable those discoveries.

## EXAMPLES

### Example 1: Enable discoveries for a class
```
PS C:\>$MP = Get-SCOMManagementPack -DisplayName "My SQL MP Customization" | Where-Object {$_.Sealed -eq $False}
PS C:\> $Class = Get-SCOMClass -DisplayName "SQL DB Engine"
PS C:\> $Discovery = Get-SCOMDiscovery -DisplayName *rule*
PS C:\> Enable-SCOMDiscovery -Class $Class -ManagementPack $MP -Discovery $Discovery -Enforce
```

This example enables discoveries for a specified class.
The **Enable-SCOMDiscovery** cmdlet saves an override in a specified management pack.

The first command uses the **Get-SCOMManagementPack** cmdlet to get management pack objects that have the specified display name, and passes them to the **Where-Object** cmdlet by using the pipeline operator.
That cmdlet drops any sealed management packs.
For more information, type `Get-Help Where-Object`.
The command stores all unsealed management packs in the $MP variable.

The second command uses the **Get-SCOMClass** cmdlet to get classes that have the specified display name, and then stores them in the $Class variable.

The third command uses the **Get-SCOMDiscovery** cmdlet to get discovery objects that have display names that contain the string rule, and then stores them in the $Discovery variable.

The fourth command enables the discoveries.
The $Discovery variable contains objects that represented discoveries.
The command specifies the class object stored in the $Class variable.
The cmdlet saves the override in the management pack represented by the object in the $MP variable.
The command uses the *Enforce* parameter; therefore the cmdlet sets the **Enforce** property to $True.

## PARAMETERS

### -Class
Specifies an array of management pack class objects.
To obtain a class object, use the **Get-SCOMClass** cmdlet.
The cmdlet enables discoveries for these classes.

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

### -Discovery
Specifies an array of **ManagementPackDiscovery** objects.
To obtain a **ManagementPackDiscovery** object, use the **Get-SCOMDiscovery** cmdlet.

```yaml
Type: ManagementPackDiscovery[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enforce
Indicates that the cmdlet sets the **Enforce** property to $True on the override.

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
To obtain a group, use the **Get-SCOMGroup** cmdlet.
The cmdlet enables discoveries for these groups.

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
The cmdlet enables discoveries for these instances.

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
Specifies one or more management pack objects.
To obtain a management pack object, use the **Get-SCOMManagementPack** cmdlet.
The cmdlet saves the override into the specified management pack.

If the discovery is in an unsealed management pack, you must save the override into the same management pack.

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

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

[Disable-SCOMDiscovery](xref:SystemCenter2016/OperationsManager/vlatest/Disable-SCOMDiscovery.md)

