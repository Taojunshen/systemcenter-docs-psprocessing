---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2F341760-3B8E-43DF-8BA6-71AB6C3B0DB7
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMServerScope.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMServerScope.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMServerScope.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-DPMServerScope

## SYNOPSIS
Creates a DPM server scope object.

## SYNTAX

```
New-DPMServerScope [[-DPMServerName] <String>] [-ObjectType] <ScopedObjectType> [-ObjectId] <String[]>
 [-AlertType <AlertEnum>] [-ErrorId <Int32>] [-DetailedErrorId <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMServerScope** cmdlet creates a System Center 2016 - Data Protection Manager (DPM) server scope object.
You can create a scoped DPM server connection by using the  cmdlet with a scope object.

## EXAMPLES

### Example 1: Create server scope for a connection
```
PS C:\>$ServerScope = New-DPMServerScope -DPMServerName "DPMServer07" -ObjectType ProtectionGroup -ObjectID "Protection Group 01"
PS C:\> $DpmServer = Connect-DPMServer -DPMServerScope $ServerScope
```

The first command creates a server scope for the DPM server named DPMServer07, and then stores that scope in the $ServerScope variable.
The command specifies ProtectionGroup as the object type, with an object ID of Protection Group 01.

The second command uses the **Connect-DPMServer** cmdlet to create a connection that uses the server scope in $ServerScope.

### Example 2: Create server scope that has alerts specified
```
PS C:\>$ServerScope = New-DPMServerScope -DPMServerName "DPMServer07" -ObjectType Datasource -ObjectID "70fd1133-1bab-4178-8e8c-24d928b6b16c" -AlertType BackupToTapeFailedAlert -DetailedErrorID 910 -ErrorID 3113 
PS C:\> $DpmServer = Connect-DPMServer -DPMServerScope $ServerScope
```

The first command creates a server scope for the DPM server named DPMServer07, and then stores that scope in the $ServerScope variable.
The command specifies Datasource as the object type and specifies an object ID.
The command also specifies an alert type and both detailed error ID and error ID.

The second command uses the **Connect-DPMServer** cmdlet to create a connection that has the server scope in $ServerScope.

## PARAMETERS

### -AlertType
Specifies the type of alert for the connection scope.

The acceptable values for this parameter are:

- RestoreDBAlert 
- NullType 
- AgentIncompatibleAlert 
- AgentUnreachableAlert 
- MediaVerificationFailedAlert 
- MediaEraseFailedAlert 
- DetailedInventoryFailedAlert 
- MediaDecommissionedAlert 
- MediaDataEraseAlert 
- FreeMediaThresholdAlert 
- DataSetCopyFailedAlert 
- BackupToTapeFailedAlert 
- BackupToTapeCatalogFailedAlert 
- LibraryDriveAlert 
- LibraryNotAvailableAlert 
- LibraryNotWorkingEfficientlyAlert 
- MediaRequiredAlert 
- ReplicaInitializationInProgressAlert 
- SynchronizationFailedAlert 
- StopProtectionFailedAlert 
- RecoveryInProgressAlert 
- RecoveryPartiallySuccessfulAlert 
- RecoverySuccessfulAlert 
- RecoveryFailedAlert 
- ShadowCopyFailedAlert 
- ReplicaInMissingStateAlert 
- ReplicaInInvalidStateAlert 
- PartialDeployedClusterAlert 
- AgentTaskFailAlert 
- SqmOptInAlert 
- DiskThresholdCrossedAlert 
- VerificationInProgressAlert 
- DiskMissingAlert 
- CatalogThresholdCrossedAlert 
- DatasetDataVerificationFailed 
- SCDiskThresholdCrossedAlert 
- ConfigureProtectionFailedAlert 
- ReplicaManualLoadPendingAlert 
- ReplicaInitializationPendingAlert 
- CertificateExpiringAlert 
- EvalShareInquiryAlert 
- ShadowCopyConsolidationRequired 
- PathChangedForShareAlert 
- BackupMetadataEnumerationFailedAlert 
- DuplicateDisksDetectedAlert 
- DataCorruptionDetectedAlert 
- DataCorruptionDetectedDuringReadAlert 
- StagingAreaRestoreInProgressAlert 
- StagingAreaRestorePartiallySuccessfulAlert 
- StagingAreaRestoreSuccessfulAlert 
- StagingAreaRestoreFailedAlert 
- AgentOwnershipRequiredAlert 
- AutoInstanceProtectionFailedAlert 
- AgentAttachFailedAlert 
- BackupSLAFailedAlert 
- DpmoRPCreationFailureAlert 
- DOCVolumeMissing 
- SharepointROAddedAlert 
- SharepointRORemovedAlert 
- PartialBackupSuccessAlert 
- GlobalDbNotAvailable 
- LibraryDevicesDisabledAlert 
- LdmWarningThresholdReachedAlert 
- LdmErrorThresholdReachedAlert 
- CertificateExpiryWarningAlert 
- CertificateExpiryErrorAlert 
- RecoveryFailedWarningAlert 
- ExternalAlert 
- OnlineBackupServiceUnreachableAlert 
- OnlineBackupPoliciesInconsistentAlert 
- CloudBackupFailedAlert 
- PartialCloudBackupSuccessAlert

```yaml
Type: AlertEnum
Parameter Sets: (All)
Aliases: 
Accepted values: NullType, AgentIncompatibleAlert, AgentUnreachableAlert, MediaVerificationFailedAlert, MediaEraseFailedAlert, DetailedInventoryFailedAlert, MediaDecommissionedAlert, MediaDataEraseAlert, FreeMediaThresholdAlert, DataSetCopyFailedAlert, BackupToTapeFailedAlert, BackupToTapeCatalogFailedAlert, LibraryDriveAlert, LibraryNotAvailableAlert, LibraryNotWorkingEfficientlyAlert, MediaRequiredAlert, ReplicaInitializationInProgressAlert, SynchronizationFailedAlert, StopProtectionFailedAlert, RecoveryInProgressAlert, RecoveryPartiallySuccessfulAlert, RecoverySuccessfulAlert, RecoveryFailedAlert, ShadowCopyFailedAlert, ReplicaInMissingStateAlert, ReplicaInInvalidStateAlert, PartialDeployedClusterAlert, AgentTaskFailAlert, SqmOptInAlert, DiskThresholdCrossedAlert, VerificationInProgressAlert, DiskMissingAlert, CatalogThresholdCrossedAlert, DatasetDataVerificationFailed, SCDiskThresholdCrossedAlert, ConfigureProtectionFailedAlert, ReplicaManualLoadPendingAlert, ReplicaInitializationPendingAlert, CertificateExpiringAlert, EvalShareInquiryAlert, ShadowCopyConsolidationRequired, PathChangedForShareAlert, BackupMetadataEnumerationFailedAlert, DuplicateDisksDetectedAlert, DataCorruptionDetectedAlert, DataCorruptionDetectedDuringReadAlert, StagingAreaRestoreInProgressAlert, StagingAreaRestorePartiallySuccessfulAlert, StagingAreaRestoreSuccessfulAlert, StagingAreaRestoreFailedAlert, AgentOwnershipRequiredAlert, AutoInstanceProtectionFailedAlert, AgentAttachFailedAlert, BackupSLAFailedAlert, DpmoRPCreationFailureAlert, DOCVolumeMissing, SharepointROAddedAlert, SharepointRORemovedAlert, PartialBackupSuccessAlert, GlobalDbNotAvailable, LibraryDevicesDisabledAlert, LdmWarningThresholdReachedAlert, LdmErrorThresholdReachedAlert, CertificateExpiryWarningAlert, CertificateExpiryErrorAlert, RecoveryFailedWarningAlert, ExternalAlert, OnlineBackupServiceUnreachableAlert, OnlineBackupPoliciesInconsistentAlert, CloudBackupFailedAlert, PartialCloudBackupSuccessAlert, SLAMissedAlert, OfflineInitialCloudBackupPendingAlert, RestoreDBAlert

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DetailedErrorId
Specifies the ID of a detailed error.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet creates a server scope.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorId
Specifies the ID of an error.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Specifies an array of IDs for objects that scope a connection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectType
Specifies the type of objects defined in the *ObjectId* parameter. 

The acceptable values for this parameter are:

- Datasource.
DatasourceID. 
- ProtectionGroup.
ProtectionGroupID/ProtectionGroupName. 
- ProductionServer.
ProductionServerID/ProductionServerName. 
- Disk.
DiskID. 
- Volume.
VolumeID. 
- Library.
LibraryID. 
- Drive.
DriveID. 
- AdhocAction.
ActionID. 
- DPMServer.
DPMServerName.

```yaml
Type: ScopedObjectType
Parameter Sets: (All)
Aliases: 
Accepted values: DpmServer, Datasource, ProtectionGroup, ProductionServer, Disk, Volume, Library, Drive, AdhocAction

Required: True
Position: 2
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

[Connect-DPMServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Connect-DPMServer.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

