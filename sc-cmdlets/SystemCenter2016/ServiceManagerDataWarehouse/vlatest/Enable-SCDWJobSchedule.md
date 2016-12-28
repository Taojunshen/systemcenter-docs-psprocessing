---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FE448EAF-6CB2-44CA-8CA8-87CC80B103B1
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCDWJobSchedule

## SYNOPSIS
Enables a job schedule so that a job runs according to its schedule.

## SYNTAX

```
Enable-SCDWJobSchedule [-JobName] <String> [-ComputerName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCDWJobSchedule** cmdlet enables a job schedule so that a job runs according to its specified schedule.
If the job schedule was previously disabled, enabling the job schedule retains the job's schedule settings.
To disable the job schedule, use the **Disable-SCDWJobSchedule** cmdlet; to modify the job's schedule, use the **Set-SCDWJobSchedule** cmdlet.

## EXAMPLES

### Example 1: Enable a job schedule
```
PS C:\>Enable-SCDWJobSchedule â€"ComputerName "serverDW72" â€"JobName "Transform.Common"
```

This command enables the job schedule for the `Transform.Common` job.

### Example 2: Display jobs and their job schedule status
```
PS C:\>Get-SCDWJobSchedule -ComputerName "serverDW72" | Format-Table -Property Name, ScheduleEnabled
-AutoSize
```

The following command shows the all the jobs and whether their schedule is enabled or disabled.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
You can omit this parameter only if the System Center Data Access Service is running on the same computer that has Service Manager installed.

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

### -JobName
Specifies the Data Warehouse job for which you want to enable the schedule.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Disable-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobSchedule.md)

[Set-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWJobSchedule.md)

[Get-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobSchedule.md)

