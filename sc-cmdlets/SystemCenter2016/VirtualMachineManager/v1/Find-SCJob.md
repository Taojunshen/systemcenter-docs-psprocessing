---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCJob.md
schema: 2.0.0
ms.assetid: 4F2E3AAD-5390-4021-8E8F-47D9FCCE6C8D
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Find-SCJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Find-SCJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Find-SCJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Find-SCJob

## SYNOPSIS
Searches for VMM jobs.

## SYNTAX

### FindAfter (Default)
```
Find-SCJob [-After <DateTime>] [-VMMServer <ServerConnection>] -MaxCount <Int32> [-ObjectID <Guid>]
 [-CriticalFailures <Boolean>] [<CommonParameters>]
```

### FindRecent
```
Find-SCJob [-VMMServer <ServerConnection>] -MaxCount <Int32> [-ObjectID <Guid>] [-CriticalFailures <Boolean>]
 [-Recent] [<CommonParameters>]
```

## DESCRIPTION
The **Find-SCJob** cmdlet searches for Virtual Machine Manager (VMM) jobs.
You can search for the most recent jobs, jobs after a certain date, or search for a job by its result or target ID.

## EXAMPLES

### Example 1: Find all jobs for the last five hours
```
PS C:\>$StartTime = (Get-Date) - (New-TimeSpan -Hours 5)
PS C:\> Find-SCJob -MaxCount 25 -After $StartTime
```

This command searches for all jobs that started within the last five hours.
Because the *MaxCount* parameter value is set to 25, only 25 job objects are displayed.

### Example 2: Find recent jobs
```
PS C:\>Find-SCJob -MaxCount 50 -Recent
```

This command searches for recent jobs and displays the 50 most recent jobs.

### Example 3: Find jobs by ObjectID
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Find-SCJob -MaxCount 10 -ObjectID $VM.Id
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command returns up to 10 jobs for the specified virtual machine ID.

## PARAMETERS

### -After
Specifies a **DateTime** object for the time after which jobs are retrieved.
By default, time is represented in the local time zone.
You can pass the **DateTime** object as UTC for standardized time.

When you specify this parameter, jobs are filtered by the StartTime property and returned from earliest start time to latest start time.

For information about how to get a **DateTime** object, see the Get-Date cmdlet.

```yaml
Type: DateTime
Parameter Sets: FindAfter
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CriticalFailures
Indicates whether to find critical failures only.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCount
Specifies the maximum number of jobs to return.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectID
Specifies the object ID, as a GUID, for a service.
This ID is the result object or target object for the returned job.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recent
Indicates that the most recent jobs are returned.
Jobs are returned from latest start time to earliest start time.

Use this parameter with the *MaxCount* parameter to retrieve only a specified number of jobs.

```yaml
Type: SwitchParameter
Parameter Sets: FindRecent
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Job
This cmdlet returns a **Job** object.

## NOTES

## RELATED LINKS

[Get-SCJob](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCJob.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Restart-SCJob](xref:SystemCenter2016/VirtualMachineManager/v1/Restart-SCJob.md)

[Stop-SCJob](xref:SystemCenter2016/VirtualMachineManager/v1/Stop-SCJob.md)

