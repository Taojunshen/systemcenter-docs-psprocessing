---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Get-SCDWJob.md
schema: 2.0.0
ms.assetid: 49AF13C3-7C7E-4489-A6D2-060DB13E1A95
updated_at: 12/15/2016 6:30 PM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobModule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobModule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/59ca46449cbaf6c065d4887fdd68c8de98ef34f0/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJobModule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDWJobModule

## SYNOPSIS
Gets detailed status information about the modules of the job.

## SYNTAX

### JobNameSet (Default)
```
Get-SCDWJobModule [-JobName <String>] [-NumberOfBatches <Int32>] [-ComputerName <String>] [<CommonParameters>]
```

### JobNameModuleNameSet
```
Get-SCDWJobModule [-ModuleName <String>] [-JobName <String>] [-NumberOfBatches <Int32>]
 [-ComputerName <String>] [<CommonParameters>]
```

### JobIDSet
```
Get-SCDWJobModule [-ModuleName <String>] [-ModuleID <Int32>] -JobBatchID <Int32> [-ComputerName <String>]
 [<CommonParameters>]
```

### JobNameModuleIDSet
```
Get-SCDWJobModule [-ModuleID <Int32>] [-JobName <String>] [-NumberOfBatches <Int32>] [-ComputerName <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWJobModule** cmdlet returns detailed status information about the modules of the specified job.
Each data warehouse job comprises multiple subprocesses, called modules, which perform the individual work items that are associated with the parent job.

For updated information about this cmdlet, see Get-SCDWJobModulehttp://go.microsoft.com/fwlink/p/?LinkId=234991.

## EXAMPLES

### Example 1: Display module information about a job
```
PS C:\>Get-SCDWJobmodule -ComputerName "serverDW72" -JobName "Transform.common" -NumberOfBatches 4
```

This command displays module information about the `Transform.common` job.

### Example 2: Display module information about a job with a specific batch ID
```
PS C:\>Get-SCDWJobModule â€"ComputerName "serverDW72" -JobBatchID 4126 -NumberOfBatches 4
```

This command displays module information for jobs using a specified job batch ID.

### Example 3: Display module information for a specific job and module ID
```
PS C:\>Get-SCDWJobModule -ComputerName "IXSMTestDW" -JobName "DWMaintenance" -ModuleID 7 -NumberOfBatches 12
```

This command displays module information for a specific job and module by its module ID.

### Example 4: Display module information for a job with a specific module name
```
PS C:\>Get-SCDWJobModule -ComputerName "IXSMTestDW" -JobName "MPSyncJob" -ModuleName "Clean Up" -NumberOfBatches 12
```

This command displays module information for a specific job and module by its module name.

### Example 5: List module error counts for modules with errors
```
PS C:\>Get-SCDWJobModule -ComputerName "serverDW72" -NumberOfBatches 12| Where-Object {$_.ModuleErrorCount -gt 0} | Format-Table -Property JobName, ModuleID, ModuleErrorCount -AutoSize
```

This command lists module error counts, but only if an error count is greater than zero.

### Example 6: Save module property values to a CSV file
```
PS C:\>Get-SCDWJobModule -ComputerName "serverDW72" â€"NumberOfBatches 4| Select-Object -Property BatchId, CategoryId, CategoryName, CreationTime, Description, JobId, JobModuleId, JobName, ManagementGroup, ManagementGroupId, ModuleCreationTime, ModuleDescription, ModuleErrorCount, ModuleErrorSummary, ModuleId, ModuleModifiedTime, ModuleName, ModuleRetryCount, ModuleStartTime, ModuleTypeId, ModuleTypeName, NotToBePickedBefore, Status | Export-Csv "C:\TEMP\JobModuleData.csv"
```

This command gets all the job module property values and saves the results to a CSV file.

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

### -JobBatchID
Specifies the jobâ€™s batch ID for which to retrieve all associated modules.
You can use the **Get-SCDWJob** cmdlet to retrieve a jobâ€™s batch ID.
By specifying the **JobBatchID** parameter, you retrieve all the modules of the specified job.

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
Specifies the name of the specific Extract, Transform, or Load job for which you want to get status.

```yaml
Type: String
Parameter Sets: JobNameSet, JobNameModuleNameSet, JobNameModuleIDSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleID
Specifies the ID of the job module for which to retrieve status.
This must be a valid module ID for the specified job.
This parameter cannot be used in conjunction with the **JobModule** parameter.

```yaml
Type: Int32
Parameter Sets: JobIDSet, JobNameModuleIDSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModuleName
Specifies the name of the job module for which to retrieve status.
This name must be a valid module name for the specified job.
This parameter cannot be used in conjunction with the **ModuleID** parameter.

```yaml
Type: String
Parameter Sets: JobNameModuleNameSet, JobIDSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfBatches
Specifies the number of batches for which to return status.

```yaml
Type: Int32
Parameter Sets: JobNameSet, JobNameModuleNameSet, JobNameModuleIDSet
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

### Microsoft.EnterpriseManagement.OrchestrationJobModule

## NOTES

## RELATED LINKS

[Get-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJob.md)

