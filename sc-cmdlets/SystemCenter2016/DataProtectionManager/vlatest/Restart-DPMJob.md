---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 27587B4A-450B-466B-BEB7-6C45E59D991D
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Restart-DPMJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Restart-DPMJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Restart-DPMJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Restart-DPMJob

## SYNOPSIS
Restarts failed DPM jobs.

## SYNTAX

```
Restart-DPMJob [-Job] <Job[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-DPMJob** cmdlet restarts failed System Center 2016 - Data Protection Manager (DPM) jobs.

## EXAMPLES

### Example 1: Restart failed jobs
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "Contoso-DPMServer"
PS C:\> $Job = Get-DPMJob -ProtectionGroup $PGroup -Status $Failed
PS C:\> Restart-DPMJob -Job $Job
```

The first command uses the **Get-DPMProtectionGroup** cmdlet to retrieve the protection group, and then stores that group in the $PGroup variable.

The second command uses the **Get-DPMJob** cmdlet to retrieve the failed jobs for the protection group, and then stores them in the $Job variable.

The third command restarts the jobs in $Job.

## PARAMETERS

### -Job
Specifies an array of jobs that this cmdlet restarts.
To obtain **Job** objects, use the Get-DPMJob cmdlet.

```yaml
Type: Job[]
Parameter Sets: (All)
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

[Stop-DPMJob](xref:SystemCenter2016/DataProtectionManager/vlatest/Stop-DPMJob.md)

