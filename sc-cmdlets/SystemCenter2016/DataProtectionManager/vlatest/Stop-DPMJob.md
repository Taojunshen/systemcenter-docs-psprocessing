---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A385C368-11ED-40B6-8808-F2FDDA788FD3
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Stop-DPMJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Stop-DPMJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Stop-DPMJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Stop-DPMJob

## SYNOPSIS
Stops DPM jobs.

## SYNTAX

### CancelDpmJob (Default)
```
Stop-DPMJob [-Job] <Job[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CancelDpmTask
```
Stop-DPMJob [-Task] <Task[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-DPMJob** cmdlet stops jobs that are running in System Center 2016 - Data Protection Manager (DPM).

## EXAMPLES

### Example 1: Stop all DPM jobs
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "Contoso-DPMServer"
PS C:\> $Jobs = Get-DPMJob -ProtectionGroup $PGroup -Status InProgress
PS C:\> Stop-DPMJob -Job $Jobs
```

The first command uses the **Get-DPMProtectionGroup** cmdlet to get the protection group for the server named Contoso-DPMServer.
The command stores the group in the $PGroup variable.

The second command uses the **Get-DPMJob** cmdlet to get the jobs that are running for the protection group.
The command stores the jobs in the $Jobs variable.

The third command stops the jobs stored in $Job.

## PARAMETERS

### -Job
Specifies an array of jobs that this cmdlet stops.
To obtain **Job** objects, use the Get-DPMJob cmdlet.

```yaml
Type: Job[]
Parameter Sets: CancelDpmJob
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Task
Specifies an array of task objects.

```yaml
Type: Task[]
Parameter Sets: CancelDpmTask
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

[Get-DPMJob](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMJob.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Restart-DPMJob](xref:SystemCenter2016/DataProtectionManager/vlatest/Restart-DPMJob.md)

