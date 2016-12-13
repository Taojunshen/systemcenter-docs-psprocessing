---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCExternalJob.md
schema: 2.0.0
ms.assetid: 122E2D3C-EE43-4828-9FF1-4C3A2FA148F6
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCExternalJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCExternalJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCExternalJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCExternalJob

## SYNOPSIS
Updates an existing external job.

## SYNTAX

### Progress (Default)
```
Set-SCExternalJob [-Job] <Task> -ProgressValue <Int32> [<CommonParameters>]
```

### Completed
```
Set-SCExternalJob [-Job] <Task> [-Completed] [-InfoMessage <String>] [<CommonParameters>]
```

### Failed
```
Set-SCExternalJob [-Job] <Task> [-Failed] -InfoMessage <String> [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCExternalJob** cmdlet updates existing external jobs in Virtual Machine Manager (VMM).
You can update the percent complete of the job, or set the status of the job to completed or failed.

For more information about external jobs, see the New-SCExternalJob cmdlet.

## EXAMPLES

### Example 1: Set an external job to 15% complete
```
PS C:\>$ExternalJob = Get-SCJob -Name "ExternalJob01"
PS C:\> Set-SCExternalJob -Job $ExternalJob -ProgressValue 15
```

The first command gets the external job object named ExternalJob01 and stores the object in the $ExternalJob variable.

The second command sets the progress value for the job stored in $ExternalJob to 15.

### Example 2: Set an external job to completed
```
PS C:\>$ExternalJob = Get-SCJob -Name "ExternalJob02"
PS C:\> Set-SCExternalJob -Job $ExternalJob -Completed -InfoMessage "Some information about the completed job"
```

The first command gets the external job object named ExternalJob02 and stores the object in the $ExternalJob variable.

The second command sets the status of the job stored in $ExternalJob to completed, and adds information about the job.

### Example 3: Set an external job to failed
```
PS C:\>$ExternalJob = Get-SCJob -Name "ExternalJob03"
PS C:\> Set-SCExternalJob -Job $ExternalJob -Failed -InfoMessage "An error message for the failed job"
```

The first command gets the external job object named ExternalJob03 and stores the object in the $ExternalJob variable.

The second command sets the status of the job stored in $ExternalJob to failed, and adds information about the job.

## PARAMETERS

### -Completed
Sets the status of an external job to completed.

```yaml
Type: SwitchParameter
Parameter Sets: Completed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Failed
Sets the status of an external job to failed.

```yaml
Type: SwitchParameter
Parameter Sets: Failed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InfoMessage
Provides an informational message for external jobs.

```yaml
Type: String
Parameter Sets: Completed
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Failed
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies a VMM job object.

```yaml
Type: Task
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProgressValue
Supplies the percent complete of the progress of an external job.

```yaml
Type: Int32
Parameter Sets: Progress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Task
This cmdlet returns a **Task** object.

## NOTES

## RELATED LINKS

[New-SCExternalJob](xref:VirtualMachineManager/v1/New-SCExternalJob.md)

