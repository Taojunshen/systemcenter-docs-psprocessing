---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 229414EE-CC6B-4271-A26C-15ACB118A4F8
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryOption.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryOption.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryOption.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DPMRecoveryOption

## SYNOPSIS
Creates recovery options.

## SYNTAX

### StagingAreaRestoreOption
```
New-DPMRecoveryOption [[-DPMServerName] <String>] [-DPMLibrary <Library>] [-RecoverToReplicaFromTape <Boolean>]
 [-OverwriteType] <OverwriteType> [-RestoreSecurity] [-StagingAreaPath] <String>
 [-DestinationServerName] <String> [-DestinationPath] <String> [-DatasourceName] <String>
 -DPMComponentName <Guid> [-FileSystemDatasource] [<CommonParameters>]
```

### FsRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-FileSystem] [-AlternateLocation <String>]
 [-OverwriteType] <OverwriteType> [-RestoreSecurity] -RecoveryType <RecoveryType> [<CommonParameters>]
```

### SQLRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] [-SQL] -RecoveryType <RecoveryType>
 [-RollForwardRecovery] [-TargetLocation <String>] [-AlternateDatabaseDetails <AlternateDatabaseDetailsType>]
 [-LeaveDBInRestoringState] [-CopyLogFiles] [-LogFileCopyLocation <String>] [<CommonParameters>]
```

### SharePointRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] -RecoveryType <RecoveryType>
 [-TargetLocation <String>] [-SharePoint] [<CommonParameters>]
```

### SharePointSiteRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] -RecoveryType <RecoveryType>
 [-TargetLocation <String>] [-SharePointSite] -DatabaseFileTempLocation <String> -IntermediateServer <String>
 -IntermediateSqlInstance <String> -ExportFileTempLocation <String> [-TargetSiteUrl <String>]
 [-ItemLevelRecoveryType <SharepointRecoveryType>] [<CommonParameters>]
```

### GenericDatasourceRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] -RecoveryType <RecoveryType>
 [-TargetLocation <String>] [-GenericDatasource] [<CommonParameters>]
```

### HyperVDatasourceRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] -RecoveryType <RecoveryType>
 [-TargetLocation <String>] [-HyperVDatasource] [<CommonParameters>]
```

### ClientDatasourceRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-AlternateLocation <String>]
 [-OverwriteType] <OverwriteType> [-RestoreSecurity] -RecoveryType <RecoveryType> [-ClientDatasource]
 [<CommonParameters>]
```

### SystemProtectionRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] -RecoveryType <RecoveryType>
 [-TargetLocation <String>] [-SystemProtectionDatasource] [<CommonParameters>]
```

### ExchangeRecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] -RecoveryType <RecoveryType>
 [-RollForwardRecovery] [-TargetLocation <String>] [-Exchange] [-AlternateDatabase <String>]
 [-AlternateStorageGroup <String>] [-IsRecoveryStorageGroup] [-MountDatabaseAfterRestore]
 -ExchangeOperationType <ExchangeOperationType> [-MailboxDisplayName <String>] [-DatabaseName <String>]
 [-StorageGroupName <String>] [<CommonParameters>]
```

### E14RecoveryOption
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-SANRecovery] [-RestoreSecurity] -RecoveryType <RecoveryType>
 [-RollForwardRecovery] [-TargetLocation <String>] [-E14Datasource] [-AlternateDatabase <String>]
 [-IsRecoveryDatabase] [-MountDatabaseAfterRestore] -ExchangeOperationType <ExchangeOperationType>
 [<CommonParameters>]
```

### RecoverToDpm
```
New-DPMRecoveryOption [-TargetServer] <String> [-RecoveryLocation] <RecoveryLocation> [-DPMLibrary <Library>]
 [-RecoverToReplicaFromTape <Boolean>] [-PrimaryDpmServer] [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMRecoveryOption** cmdlet creates recovery options for file servers, computers that run Exchange Server, SharePoint Server, and Microsoft SQL Server, and other data sources.

## EXAMPLES

### Example 1: Recover a file system
```
PS C:\>New-DPMRecoveryOption -TargetServer "tsqa.contoso.com" -RecoveryLocation "D:\copytofolder" -FileSystem -AlternateLocation "F:\restore" -OverwriteType Overwrite -RestoreSecurity -RecoveryType Restore
```

This command creates a recovery option that restores the file system to tsqa.contoso.com and restores the original security settings.

### Example 2: Recover a file system by using a replica
```
PS C:\>Connect-DPMServer -DPMServerName "DPMServer01"
PS C:\> $PServer = Get-DPMProductionServer -DPMServerName "DPMServer01"
PS C:\> $PObjects = Get-DPMDatasource -ProductionServer $PServer
PS C:\> $DpmLibrary = Get-DPMLibrary -DPMServerName "DPoreMServer01"
PS C:\> $RPoint = Get-DPMRecoveryPoint -Datasource $PObjects
PS C:\> $ROption = New-DPMRecoveryOption -Filesystem -RecoverToReplicaFromTape $True -RecoveryLocation DPMReplicaVolume -DPMLibrary $DpmLibrary[0] -TargetServer "DPMServer02" -OverwriteType Overwrite
```

The first command opens a connection to a DPM server.

The second command gets the computer named DPMServer01.
The DPM protection agent is installed on this server.
The command stores the server in the $PServer variable.

The third command gets the list of protected and unprotected data on the protection server in $PServer.
The command stores the result in the $PObject variable.

The fourth command gets the libraries associated with the DPM server named DPoreMServer01.
The command stores the libraries in the $DpmLibrary variable.

The fifth command gets the recovery point for the data source in $PObject, and then stores that recovery point result in the $RPoint variable.

The sixth command creates a recovery option on a file system data source.
The command specifies that data is recovered to the replica on the target server named DPMServer02 from a tape.

### Example 3: Recover a file system from a replica on tape
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObject = Get-DPMDatasource -ProductionServer $PGroup
PS C:\> $RPoint = Get-DPMRecoveryPoint -Datasource $PObject
PS C:\> $DpmLibraries = Get-DPMLibrary -DPMServerName "DPoreMServer01"
PS C:\> $ROption = New-DPMRecoveryOption -RecoverToReplicaFromTape $True -RecoveryLocation DPMReplicaVolume -FileSystem -TargetServer "DPMServer02" -OverwriteType Overwrite -RecoveryType Recover -DpmLibrary $DpmLibraries
PS C:\> Restore-DPMRecoverableItem -RecoverableItem $RPoint -RecoveryOption $ROption
```

The first command gets the protection group on the DPM server named DPMServer02.
The command stores the result in the $PGroup variable.

The second command gets the protected and unprotected data on the production server in $PServer.
The command stores the results in the $PObject variable.

The third command gets the recovery point for the data source in $PObject, and stores that recovery point in the $RPoint variable.

The fourth command gets the libraries associated with the DPM server named DPoreMServer01.
The command stores the libraries in the $DpmLibraries variable.

The fifth command creates a recovery option on a file system data source.
The command specifies that data is recovered to the replica on the target server named DPMServer02 from a tape.

The sixth command restores a version of the data source in $RPoint by using the recovery option in $ROption.

## PARAMETERS

### -AlternateDatabase
Specifies the name of an alternate database for recovery.

```yaml
Type: String
Parameter Sets: ExchangeRecoveryOption, E14RecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlternateDatabaseDetails
Specifies the type of the alternate database.

```yaml
Type: AlternateDatabaseDetailsType
Parameter Sets: SQLRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlternateLocation
Specifies an alternate location where System Center 2016 - Data Protection Manager (DPM) creates a recovery point.

```yaml
Type: String
Parameter Sets: FsRecoveryOption, ClientDatasourceRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlternateStorageGroup
Specifies an alternate storage group for a new recovery point.

```yaml
Type: String
Parameter Sets: ExchangeRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientDatasource
Indicates that the restored data is a file system or an application.

```yaml
Type: SwitchParameter
Parameter Sets: ClientDatasourceRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CopyLogFiles
Indicates that DPM copies the log files.

```yaml
Type: SwitchParameter
Parameter Sets: SQLRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseFileTempLocation
Specifies a temporary location for the database file.

```yaml
Type: String
Parameter Sets: SharePointSiteRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database.

```yaml
Type: String
Parameter Sets: ExchangeRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasourceName
Specifies the name of the data source.

```yaml
Type: String
Parameter Sets: StagingAreaRestoreOption
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPath
Specifies the recovery location.

```yaml
Type: String
Parameter Sets: StagingAreaRestoreOption
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationServerName
Specifies the name of the server to which DPM recovers data.

```yaml
Type: String
Parameter Sets: StagingAreaRestoreOption
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMComponentName
Specifies the GUID of the data source that DPM recovers.

```yaml
Type: Guid
Parameter Sets: StagingAreaRestoreOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMLibrary
Specifies a DPM library object for which this cmdlet creates a recovery option.
To obtain a DPM library object, use the Get-DPMLibrary cmdlet.

```yaml
Type: Library
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet acts.
If you do not specify a name, the cmdlet uses the name of the current computer.

```yaml
Type: String
Parameter Sets: StagingAreaRestoreOption
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -E14Datasource
Indicates that the data source is Exchange Server 2010.

```yaml
Type: SwitchParameter
Parameter Sets: E14RecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exchange
Indicates that DPM performs the current operation on a Exchange Server data source.

```yaml
Type: SwitchParameter
Parameter Sets: ExchangeRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeOperationType
Specifies the type of operation that DPM performs on a Exchange Server data source.

The acceptable values for this parameter are:

- NoOperation 
- MailBoxLevelRecovery 
- NeedCleanShutdown

```yaml
Type: ExchangeOperationType
Parameter Sets: ExchangeRecoveryOption, E14RecoveryOption
Aliases: 
Accepted values: NoOperation, MailBoxLevelRecovery, NeedCleanShutdown

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExportFileTempLocation
Specifies the location of the export file.

```yaml
Type: String
Parameter Sets: SharePointSiteRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystem
Indicates that DPM performs the current operation on a file system data source.

```yaml
Type: SwitchParameter
Parameter Sets: FsRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystemDatasource
Indicates that DPM recovers a file system data source.

```yaml
Type: SwitchParameter
Parameter Sets: StagingAreaRestoreOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenericDatasource
Indicates that DPM performs the current operation on a data source such as Microsoft Virtual Server.

```yaml
Type: SwitchParameter
Parameter Sets: GenericDatasourceRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HyperVDatasource
Indicates that the data source is nextref_virtualname.

```yaml
Type: SwitchParameter
Parameter Sets: HyperVDatasourceRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntermediateServer
Specifies the server that DPM uses for SharePoint site recovery.

```yaml
Type: String
Parameter Sets: SharePointSiteRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntermediateSqlInstance
Specifies an instance of SQL Server that DPM uses for SharePoint site recovery.
DPM uses the instance of SQL Server to temporarily host a SQL Server database.

```yaml
Type: String
Parameter Sets: SharePointSiteRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsRecoveryDatabase
Indicates that the database is a recovery database.

```yaml
Type: SwitchParameter
Parameter Sets: E14RecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsRecoveryStorageGroup
Indicates that the recovery is a recovery storage group.

```yaml
Type: SwitchParameter
Parameter Sets: ExchangeRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ItemLevelRecoveryType
Specifies the recovery type.

The acceptable values for this parameter are:

- RecoveryFarm 
- UnattachedInstance

```yaml
Type: SharepointRecoveryType
Parameter Sets: SharePointSiteRecoveryOption
Aliases: 
Accepted values: RecoveryFarm, UnattachedInstance

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LeaveDBInRestoringState
Indicates that DPM leaves the database non-operational but in a restorable state.
Specify this parameter to leave the database operational.

```yaml
Type: SwitchParameter
Parameter Sets: SQLRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogFileCopyLocation
Specifies the location where DPM copies log files.

```yaml
Type: String
Parameter Sets: SQLRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MailboxDisplayName
Specifies a name that DPM displays on the mailbox.

```yaml
Type: String
Parameter Sets: ExchangeRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MountDatabaseAfterRestore
Indicates that DPM mounts the database after it restores the database.

```yaml
Type: SwitchParameter
Parameter Sets: ExchangeRecoveryOption, E14RecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverwriteType
Specifies the action that DPM takes when the file it is recovering already exists.

The acceptable values for this parameter are:
- CreateCopy
- Skip
- Overwrite

```yaml
Type: OverwriteType
Parameter Sets: StagingAreaRestoreOption, FsRecoveryOption, ClientDatasourceRecoveryOption
Aliases: 
Accepted values: Overwrite, NoOverwrite, CopyOnExist

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryDpmServer
Indicates that the server where DPM recovers data is a DPM server.

```yaml
Type: SwitchParameter
Parameter Sets: RecoverToDpm
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoverToReplicaFromTape
Indicates whether recovery to the replica is from a tape.

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

### -RecoveryLocation
Specifies the location where DPM recovers data.

The acceptable values for this parameter are:
- OriginalServer 
- CopyToFolder 
- OriginalServerWithDBRename 
- AlternateExchangeServer 
- ExchangeServerDatabase

```yaml
Type: RecoveryLocation
Parameter Sets: FsRecoveryOption, SQLRecoveryOption, SharePointRecoveryOption, SharePointSiteRecoveryOption, GenericDatasourceRecoveryOption, HyperVDatasourceRecoveryOption, ClientDatasourceRecoveryOption, SystemProtectionRecoveryOption, ExchangeRecoveryOption, E14RecoveryOption, RecoverToDpm
Aliases: 
Accepted values: OriginalServer, CopyToFolder, OriginalServerWithDBRename, AlternateExchangeServer, ExchangeServerDatabase, PrimaryDPMServer, DPMReplicaVolume, AlternateHyperVServer

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryType
Specifies the recovery type.
If you specify the *HyperVDatasource* parameter, the only valid value is Recover.
The acceptable values for this parameter are: Recover or Restore.

```yaml
Type: RecoveryType
Parameter Sets: FsRecoveryOption, SQLRecoveryOption, SharePointRecoveryOption, SharePointSiteRecoveryOption, GenericDatasourceRecoveryOption, HyperVDatasourceRecoveryOption, ClientDatasourceRecoveryOption, SystemProtectionRecoveryOption, ExchangeRecoveryOption, E14RecoveryOption
Aliases: 
Accepted values: Recover, Restore

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreSecurity
Indicates that DPM uses the security settings from the recovery point.
If you do not specify this parameter, DPM uses the security settings of the destination server.

```yaml
Type: SwitchParameter
Parameter Sets: StagingAreaRestoreOption, FsRecoveryOption, SQLRecoveryOption, SharePointRecoveryOption, SharePointSiteRecoveryOption, GenericDatasourceRecoveryOption, HyperVDatasourceRecoveryOption, ClientDatasourceRecoveryOption, SystemProtectionRecoveryOption, ExchangeRecoveryOption, E14RecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RollForwardRecovery
Indicates that DPM recovers the application from the latest recovery point and applies all logs after that recovery point to bring the application to the latest state.

```yaml
Type: SwitchParameter
Parameter Sets: SQLRecoveryOption, ExchangeRecoveryOption, E14RecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SANRecovery
Indicates that DPM performs the current operation on a Storage Area Network (SAN) data source.

```yaml
Type: SwitchParameter
Parameter Sets: FsRecoveryOption, SQLRecoveryOption, SharePointRecoveryOption, SharePointSiteRecoveryOption, GenericDatasourceRecoveryOption, HyperVDatasourceRecoveryOption, ClientDatasourceRecoveryOption, SystemProtectionRecoveryOption, ExchangeRecoveryOption, E14RecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePoint
Indicates that DPM performs the current operation on a SharePoint data source.

```yaml
Type: SwitchParameter
Parameter Sets: SharePointRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePointSite
Indicates that DPM performs the current operation on a SharePoint site.

```yaml
Type: SwitchParameter
Parameter Sets: SharePointSiteRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQL
Indicates that DPM performs the current operation on a SQL Server data source.

```yaml
Type: SwitchParameter
Parameter Sets: SQLRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StagingAreaPath
Specifies the path of the staging area.

```yaml
Type: String
Parameter Sets: StagingAreaRestoreOption
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageGroupName
Specifies the name of the storage group.

```yaml
Type: String
Parameter Sets: ExchangeRecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SystemProtectionDatasource
Indicates that DPM performs the current operation on a system protection data source.

```yaml
Type: SwitchParameter
Parameter Sets: SystemProtectionRecoveryOption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetLocation
Specifies the location where DPM stores the replica.

```yaml
Type: String
Parameter Sets: SQLRecoveryOption, SharePointRecoveryOption, SharePointSiteRecoveryOption, GenericDatasourceRecoveryOption, HyperVDatasourceRecoveryOption, SystemProtectionRecoveryOption, ExchangeRecoveryOption, E14RecoveryOption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetServer
Specifies the target server for recovery.

If you use this cmdlet in a clustered environment, specify the target server parameter in the format *ResourceGroupName.ClusterName.DomainName*.

```yaml
Type: String
Parameter Sets: FsRecoveryOption, SQLRecoveryOption, SharePointRecoveryOption, SharePointSiteRecoveryOption, GenericDatasourceRecoveryOption, HyperVDatasourceRecoveryOption, ClientDatasourceRecoveryOption, SystemProtectionRecoveryOption, ExchangeRecoveryOption, E14RecoveryOption, RecoverToDpm
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetSiteUrl
Specifies the URL of the target where DPM recovers data.

```yaml
Type: String
Parameter Sets: SharePointSiteRecoveryOption
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

### RecoveryOption

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

[Restore-DPMRecoverableItem](xref:SystemCenter2016/DataProtectionManager/vlatest/Restore-DPMRecoverableItem.md)

