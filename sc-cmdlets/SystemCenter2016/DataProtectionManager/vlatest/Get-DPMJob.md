---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CCBB6876-08A8-4F5B-BB01-9A1D46856978
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-DPMJob

## SYNOPSIS
Gets current and previous jobs on a DPM server.

## SYNTAX

### GetJobsDPM (Default)
```
Get-DPMJob [[-DPMServerName] <String>] [[-From] <DateTime>] [[-To] <DateTime>] [-NoLimitOnJobCount]
 [-AllJobsInInterval] [[-Type] <DPMJobType[]>] [[-Status] <JobStatusType[]>] [-Newest] [-AdhocJobs]
 [<CommonParameters>]
```

### GetJobsPSName
```
Get-DPMJob [[-DPMServerName] <String>] [[-From] <DateTime>] [[-To] <DateTime>] [-NoLimitOnJobCount]
 [-AllJobsInInterval] [-ProductionServerName] <String[]> [[-Type] <DPMJobType[]>] [[-Status] <JobStatusType[]>]
 [-Newest] [-AdhocJobs] [<CommonParameters>]
```

### GetJobsDSName
```
Get-DPMJob [[-DPMServerName] <String>] [[-From] <DateTime>] [[-To] <DateTime>] [-NoLimitOnJobCount]
 [-AllJobsInInterval] [-DatasourceName] <String[]> [[-Type] <DPMJobType[]>] [[-Status] <JobStatusType[]>]
 [-Newest] [-AdhocJobs] [<CommonParameters>]
```

### GetJobsDS
```
Get-DPMJob [[-From] <DateTime>] [[-To] <DateTime>] [-NoLimitOnJobCount] [-AllJobsInInterval]
 [-Datasource] <Datasource[]> [[-Type] <DPMJobType[]>] [[-Status] <JobStatusType[]>] [-Newest] [-AdhocJobs]
 [<CommonParameters>]
```

### GetJobsPG
```
Get-DPMJob [[-From] <DateTime>] [[-To] <DateTime>] [-NoLimitOnJobCount] [-AllJobsInInterval]
 [-ProtectionGroup] <ProtectionGroup[]> [[-Type] <DPMJobType[]>] [[-Status] <JobStatusType[]>] [-Newest]
 [-AdhocJobs] [<CommonParameters>]
```

### GetJobsPS
```
Get-DPMJob [[-From] <DateTime>] [[-To] <DateTime>] [-NoLimitOnJobCount] [-AllJobsInInterval]
 [-ProductionServer] <ProductionServer[]> [[-Type] <DPMJobType[]>] [[-Status] <JobStatusType[]>] [-Newest]
 [-AdhocJobs] [<CommonParameters>]
```

### UpdateJobsDPM
```
Get-DPMJob [-Job] <Job[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMJob** cmdlet gets current and previous jobs on a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Retrieve recent jobs
```
PS C:\> Get-DPMJob -DPMServerName "Contoso-DPMServer" -Newest
```

This command returns the latest jobs run on the DPM server named Contoso-DPMServer.

### Example 2: Retrieve recent jobs for a protection group
```
PS C:\> $PGroup = Get-DPMProtectionGroup -DPMServerName "Contoso-DPMServer"
PS C:\> Get-DPMJob -ProtectionGroup $PGroup
```

The first command uses the **Get-ProtectionGroup** cmdlet to get the protection group, and then stores the group in the $PGroup variable.

The second command uses the **Get-DPMJob** cmdlet to retrieve the recent jobs for the protection group in $PGroup.

## PARAMETERS

### -AdhocJobs
Indicates that this cmdlet gets only ad hoc jobs, not scheduled jobs.

```yaml
Type: SwitchParameter
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies an array of data source objects for which this cmdlet gets jobs.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource[]
Parameter Sets: GetJobsDS
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DatasourceName
Specifies an array of names of data sources.

```yaml
Type: String[]
Parameter Sets: GetJobsDSName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server.
This cmdlet gets jobs that run on the server that this parameter specifies.

```yaml
Type: String
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName
Aliases: ComputerName, CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -From
Specifies the starting time in a range.
The cmdlet gets jobs that fall into this range.
Use the *To* parameter to specify the ending time in the range.

```yaml
Type: DateTime
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies an array of jobs that this cmdlet gets.

```yaml
Type: Job[]
Parameter Sets: UpdateJobsDPM
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Newest
Indicates that this cmdlet gets only the last job that ran on the filter objects.

```yaml
Type: SwitchParameter
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductionServer
Specifies an array of computers on which DPM protection agents are installed.

```yaml
Type: ProductionServer[]
Parameter Sets: GetJobsPS
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProductionServerName
Specifies an array names of computers on which DPM protection agents are installed.

```yaml
Type: String[]
Parameter Sets: GetJobsPSName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies an array of protection groups for which this cmdlet gets jobs.
To obtain a **ProtectionGroup** object, use the [Get-DPMProtectionGroup](./Get-DPMProtectionGroup.md) cmdlet.

```yaml
Type: ProtectionGroup[]
Parameter Sets: GetJobsPG
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Status
Specifies an array of job status types.

```yaml
Type: JobStatusType[]
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -To
Specifies the ending time in a range.
The cmdlet retrieves jobs that fall into this range.
Use the *From* parameter to specify the starting time in the range.

```yaml
Type: DateTime
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies an array of DPM job types.

The acceptable values for this parameter are:

- Recovery
- InitialReplication
- Validation
- ShadowCopy
- Replication
- MediaErase
- DriveCleaning
- DetailedInventory
- Verification
- DatasetCopy
- ArchiveFromSC
- RecoveryTape
- LibraryRescan
- DumpMedia
- MediaRecatalog
- OnlineRecatalog
- FastInventory
- CopyDataFromVolume
- StagingAreaRestore
- SharePointImportAndExport
- SharePointCatalog
- CloudBackup
- CloudToStagingAreaRestore
- StagingAreaToPsRecovery
- StagingAreaToPsRestore

```yaml
Type: DPMJobType[]
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
Aliases: JobCategory, JobType

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllJobsInInterval
Indicates that this cmdlet gets all jobs.

```yaml
Type: SwitchParameter
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoLimitOnJobCount
Indicates there is no limit on the job count to get.

```yaml
Type: SwitchParameter
Parameter Sets: GetJobsDPM, GetJobsPSName, GetJobsDSName, GetJobsDS, GetJobsPG, GetJobsPS
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Restart-DPMJob](xref:SystemCenter2016/DataProtectionManager/vlatest/Restart-DPMJob.md)

[Stop-DPMJob](xref:SystemCenter2016/DataProtectionManager/vlatest/Stop-DPMJob.md)
