---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D8F3E466-73A2-4C25-8228-95763893F1A0
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobSchedule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobSchedule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobSchedule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCDWJobSchedule

## SYNOPSIS
Gets scheduling information for data warehouse jobs.

## SYNTAX

```
Get-SCDWJobSchedule [-JobName <String>] [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWJobSchedule** cmdlet provides scheduling information for data warehouse jobs.
You can either use the **JobName** parameter to specify a specific job or omit that parameter to display scheduling information for all data warehouse jobs.

## EXAMPLES

### Example 1: Display the job schedule for a job
```
PS C:\>Get-SCDWJobSchedule -ComputerName "serverDW72" -JobName "Transform.Common"
```

This command displays the job schedule for the `Transform.Common` job.

### Example 2: Display all jobs and their run times
```
PS C:\>Get-SCDWJobSchedule -ComputerName "serverDW72" | Format-Table -Property Name, LastRunTime, NextRunTime -AutoSize
```

This command displays all jobs and their run times.

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
Specifies the job name for which to display scheduling information.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.OrchestrationJob

## NOTES

## RELATED LINKS

[Enable-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobSchedule.md)

[Disable-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobSchedule.md)

[Set-SCDWJobSchedule](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWJobSchedule.md)

