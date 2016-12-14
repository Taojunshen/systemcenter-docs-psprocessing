---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Enable-SCDWJob.md
schema: 2.0.0
ms.assetid: 4A2F8A95-DA68-4690-BAF0-4395F24E2750
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/Get-SCDWJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/Get-SCDWJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/Get-SCDWJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDWJob

## SYNOPSIS
Gets the list of all data warehouse jobs.

## SYNTAX

### JobNameSet (Default)
```
Get-SCDWJob [-JobName <String>] [-NumberOfBatches <Int32>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### JobIDSet
```
Get-SCDWJob -JobBatchID <Int32> [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWJob** cmdlet gets the list of all data warehouse jobs, displaying information such as the status of these jobs.

## EXAMPLES

### Example 1: List data warehouse jobs
```
PS C:\>Get-SCDWJob -ComputerName "serverDW72" â€"NumberOfBatches 4
```

The command in this example lists data warehouse jobs.

### Example 2: Get jobs by job name
```
PS C:\>Get-SCDWjob -ComputerName "serverDW72" -JobName "Transform.Common" -NumberOfBatches 2
```

This command gets `Transform.Common` jobs.

### Example 3: Get jobs by status and batch ID
```
PS C:\>Get-SCDWJob -ComputerName "ServerDW72" â€"NumberOfBatches 4| Where-Object {$_.Status -eq "Not Started" -and $_.BatchID -gt 800}
```

This command gets jobs that have a status of 'Not Started' and that have a batch ID greater than 800.

### Example 4: Get job property values and save them to a CSV file
```
PS C:\>Get-SCDWJobModule -ComputerName "serverDW72" -NumberOfBatches 4 | Select-Object -Property BatchId, CategoryId, CategoryName, CreationTime, Description, EndTime, Id, IsEnabled, IsRecuring, LastRunTime, ManagementGroup, ModifedTime, Modules, Name, NextRuntime, Schedule, ScheduleRuleID, SourceTypeName, StartTime, Status, StatusID, WorkflowRuleID | Export-Csv "C:\DWData\JobData.csv"
```

This command gets all the job property values and saves the results to a CSV file.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
The user account that is defined in the **Credential** parameter must have access rights to the specified computer.
You can omit this parameter only if the System Center Data Access Service is running on the same computer that has Service Manager installed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials to use when you are connecting to the server on which the System Center Data Access service is running.
The provided user account must have access to that server.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobBatchID
Specifies the batch ID of the job run to return.
A job batch ID is generated by the system for each individual run of a job.
This integer value is unique across job runs of all types.
This parameter cannot be used in conjunction with the **JobName** parameter.

```yaml
Type: Int32
Parameter Sets: JobIDSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Specifies the name of the Data Warehouse job instance for which you want to get status.
This parameter cannot be used in conjunction with the **JobBatchID** parameter.

```yaml
Type: String
Parameter Sets: JobNameSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfBatches
Specifies the number of batches for which you want to display status.
This value must be greater than or equal to 1.

```yaml
Type: Int32
Parameter Sets: JobNameSet
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

[Enable-SCDWJob](xref:SystemCenter2016/ServiceManagerData Warehouse/Enable-SCDWJob.md)

[Get-SCDWJobModule](xref:SystemCenter2016/ServiceManagerData Warehouse/Get-SCDWJobModule.md)

[Start-SCDWJob](xref:SystemCenter2016/ServiceManagerData Warehouse/Start-SCDWJob.md)
