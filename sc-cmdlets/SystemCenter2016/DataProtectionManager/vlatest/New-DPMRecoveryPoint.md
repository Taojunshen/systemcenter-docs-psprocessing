---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0D6E8F3F-7A1F-49D9-B507-D55FC6758310
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryPoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryPoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryPoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DPMRecoveryPoint

## SYNOPSIS
Creates a recovery point.

## SYNTAX

### FileSystemOnDisk
```
New-DPMRecoveryPoint [-Datasource] <Datasource[]> [-Disk] [-WithDataIntegrityCheck]
 -DiskRecoveryPointOption <CreateDiskRecoveryPointOption>
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-AdhocJobsContext <AdhocJobsContext>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ApplicationOnDisk
```
New-DPMRecoveryPoint [-Datasource] <Datasource[]> [-Disk] [-WithDataIntegrityCheck] [-BackupType <BackupType>]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-AdhocJobsContext <AdhocJobsContext>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### TapeData
```
New-DPMRecoveryPoint [-Datasource] <Datasource[]> [-Tape] -ProtectionType <ProtectionType>
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-AdhocJobsContext <AdhocJobsContext>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### LongTermCloud
```
New-DPMRecoveryPoint [-Datasource] <Datasource[]> [-Online]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-AdhocJobsContext <AdhocJobsContext>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMRecoveryPoint** cmdlet creates a recovery point for a data source.
You can create a recovery point for short-term and long-term protection types.

## EXAMPLES

### Example 1: Create a recovery point and run a backup
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> New-DPMRecoveryPoint -Datasource $PObjects -Disk -BackupType ExpressFull
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the results in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group stored in $PGroup.
The command stores the results in the $PObjects variable.

The third command creates a recovery point for the data source stored in $PObjects, and performs an ExpressFull backup.

### Example 2: Create a recovery point and synchronize with the data source
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> New-DPMRecoveryPoint -Datasource $PObjects -Disk -DiskRecoveryPointOption WithSynchronize
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the results in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group stored in $PGroup.
The command stores the results in the $PObjects variable.

The third command creates a recovery point for the data source stored in the $PObjects variable, and synchronizes the recovery point with the data source.

### Example 3: Create a short-term recovery point on tape
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> New-DPMRecoveryPoint -Datasource $PObjects -Tape -ProtectionType ShortTerm
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the results in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group stored in $PGroup.
The command stores the results in the $PObjects variable.

The third command creates a recovery point on tape for the data source stored in $PObjects, and sets the protection type to short-term.

## PARAMETERS

### -AdhocJobsContext
Specifies the context details of the ad hoc job.
Do not use this parameter from the Windows PowerShell command line.

```yaml
Type: AdhocJobsContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupType
Specifies the type of backup.

The acceptable values for this parameter are:

- ExpressFull
- Incremental

```yaml
Type: BackupType
Parameter Sets: ApplicationOnDisk
Aliases: 
Accepted values: ExpressFull, Incremental

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies an array of data source objects for which this cmdlet creates recovery points.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, System Center 2016 - Data Protection Manager (DPM) database, or system state that is a member of a protection group.

```yaml
Type: Datasource[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Disk
Indicates that DPM creates the recovery point on a disk.

```yaml
Type: SwitchParameter
Parameter Sets: FileSystemOnDisk, ApplicationOnDisk
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskRecoveryPointOption
Specifies whether DPM creates a recovery point while it synchronizes, or whether DPM synchronizes only and does not create a recovery point.

The acceptable values for this parameter are:

- WithSynchronize
- WithoutSynchronize
- OnlySynchronize

```yaml
Type: CreateDiskRecoveryPointOption
Parameter Sets: FileSystemOnDisk
Aliases: 
Accepted values: WithSynchronize, WithoutSynchronize, OnlySynchronize

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobStateChangedEventHandler
Specifies an event handler for **Job.StateChanged** events.
Use this parameter to build a graphical user interface based on cmdlets.
Do not use this parameter in the DPM Management Shell.

```yaml
Type: JobStateChangedEventHandler
Parameter Sets: (All)
Aliases: Handler

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Online
Specifies that DPM enables online protection.

```yaml
Type: SwitchParameter
Parameter Sets: LongTermCloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionType
Specifies a protection type.

```yaml
Type: ProtectionType
Parameter Sets: TapeData
Aliases: 
Accepted values: ShortTerm, LongTerm

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tape
Indicates that the recovery point is on a tape.

```yaml
Type: SwitchParameter
Parameter Sets: TapeData
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WithDataIntegrityCheck
Indicates that DPM performs a data integrity check during recovery.

```yaml
Type: SwitchParameter
Parameter Sets: FileSystemOnDisk, ApplicationOnDisk
Aliases: 

Required: False
Position: Named
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

## OUTPUTS

### Job

## NOTES

## RELATED LINKS

[Dismount-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Dismount-DPMRecoveryPoint.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md)

[Mount-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Mount-DPMRecoveryPoint.md)

[Remove-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryPoint.md)

[Get-DPMRecoveryPointLocation](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPointLocation.md)

