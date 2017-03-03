---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9ACFA5A7-C61C-41CC-B5C6-5D9A5F13F772
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Disable-SCDWJobSchedule

## SYNOPSIS
Disables a Data Warehouse job schedule.

## SYNTAX

```
Disable-SCDWJobSchedule [-JobName] <String> [-ComputerName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCDWJobSchedule** cmdlet disables a data warehouse job schedule, which causes the job schedule to stop initiating jobs.
Disabling the job schedule retains the job schedule settings.
To modify the job schedule settings, use the **Set-SCDWJobSchedule** cmdlet.

## EXAMPLES

### Example 1: Disable a job schedule
```
PS C:\>Disable-SCDWJobSchedule â€"ComputerName "serverDW72" â€"JobName "Transform.Common"
```

This command disables the job schedule for the `Transform.Common` job.

### Example 2: List enabled/disabled status of job schedules
```
PS C:\>Get-SCDWJobSchedule -ComputerName "serverDW72" | Format-Table -Property Name, ScheduleEnabled
-AutoSize
```

This command shows the all the jobs and whether their schedule is enabled or disabled.

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
Specifies the Data Warehouse job for which the schedule will be disabled.

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

[Enable-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobSchedule.md)

[Get-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobSchedule.md)

[Set-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWJobSchedule.md)

