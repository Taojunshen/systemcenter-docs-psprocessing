---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9F2D19A1-CD1B-4915-BAB0-CE0A1CE7D93C
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Resume-DPMBackup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Resume-DPMBackup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Resume-DPMBackup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Resume-DPMBackup

## SYNOPSIS
Attempts to resume stalled DPM backup jobs.

## SYNTAX

### ResumeAlertBackups (Default)
```
Resume-DPMBackup [-Alert] <Alert[]> [-BackupTargetType] <BackupTargetType>
 [[-AdhocJobsContext] <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResumeDsBackups
```
Resume-DPMBackup [-Datasource] <Datasource[]> [-BackupTargetType] <BackupTargetType>
 [[-AdhocJobsContext] <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResumePsBackups
```
Resume-DPMBackup [-ProductionServer] <ProductionServer[]> [-BackupTargetType] <BackupTargetType>
 [[-AdhocJobsContext] <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResumePgBackups
```
Resume-DPMBackup [-ProtectionGroup] <ProtectionGroup[]> [-BackupTargetType] <BackupTargetType>
 [[-AdhocJobsContext] <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-DPMBackup** cmdlet attempts to resume stalled System Center 2016 - Data Protection Manager (DPM) backup jobs.
Specify the backup target type and one of the following backup types: 

- Alert 
- Datasource 
- ProtectionGroup 
- ProductionServer

## EXAMPLES

### Example 1: Resume backing up production servers
```
PS C:\>$DpmPServer = Get-DPMProductionServer -DPMServerName "DPMServer07"
PS C:\> Resume-DPMBackup -DPMServerName "DPMServer07" -ProductionServer $DpmPServer
```

The first command uses the **Get-DPMProductionServer** cmdlet to get the production servers for the DPM server named DPMServer07.
The command stores the results in the $DpmPServer variable.

The second command resumes backing up the production servers in $DpmPServer for the DPM server named DPMServer07.

## PARAMETERS

### -AdhocJobsContext
Specifies the context details of the ad hoc job.
Do not use this parameter from the Windows PowerShell command line.

```yaml
Type: AdhocJobsContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Alert
Specifies an array of alerts for which backups resume.

```yaml
Type: Alert[]
Parameter Sets: ResumeAlertBackups
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BackupTargetType
Specifies the type of backup target.

The acceptable values for this parameter are:

- Disk 
- Tape 
- Online 
- Invalid

```yaml
Type: BackupTargetType
Parameter Sets: (All)
Aliases: 
Accepted values: Disk, Tape, Online, Invalid

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies an array of data sources for which this cmdlet resumes backups.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource[]
Parameter Sets: ResumeDsBackups
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProductionServer
Specifies an array of computers on which DPM protection agents are installed.
This cmdlet resumes backups for protection groups on the computers that this parameter specifies.

```yaml
Type: ProductionServer[]
Parameter Sets: ResumePsBackups
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies an array of protection groups for which backups resume.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup[]
Parameter Sets: ResumePgBackups
Aliases: 

Required: True
Position: 2
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

[Get-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionServer.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

