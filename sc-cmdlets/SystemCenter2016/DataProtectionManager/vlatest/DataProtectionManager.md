---
Module Name: DataProtectionManager
Module Guid: b53b4c13-8d3d-4b58-b12d-17a6fe8493d1
Download Help Link: 
Help Version: 5.0.2.0
Locale: en-US
ms.assetid: 7BA3FAA3-C11B-452D-90E5-028AB89E9734
updated_at: 12/16/2016 7:04 PM
ms.date: 12/16/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/2c6f74b28e62db8e27906fbbbcc5b66c9910f7cb/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md
uid: SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md
ms.topic: conceptual
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# DataProtectionManager Module
## Description
This reference provides cmdlet descriptions and syntax for the System Center 2016 Data Protection Manager (DPM) cmdlets.

## DataProtectionManager Cmdlets
### [Add-DPMBackupNetworkAddress](./Add-DPMBackupNetworkAddress.md)
Specifies a backup network for a DPM server.

### [Add-DPMChildDatasource](./Add-DPMChildDatasource.md)
Adds a data source or a child data source to a protection group.

### [Add-DPMDiskStorage](./Add-DPMDiskStorage.md)
Adds a specified disk to the storage pool on a DPM server.

### [Add-DPMRecoveryItem](./Add-DPMRecoveryItem.md)


### [Add-DPMRecoveryTarget](./Add-DPMRecoveryTarget.md)
Grants the DPM role permission to recover to a location.

### [Add-DPMSecurityGroup](./Add-DPMSecurityGroup.md)
Adds security groups to a DPM role.

### [Add-DPMTape](./Add-DPMTape.md)
Adds a tape to a DPM library.

### [Connect-DPMServer](./Connect-DPMServer.md)
Opens a connection to a DPM server.

### [Copy-DPMTapeData](./Copy-DPMTapeData.md)
Copies the recovery point data from a tape.

### [Disable-DPMLibrary](./Disable-DPMLibrary.md)
Disables DPM libraries.

### [Disable-DPMProductionServer](./Disable-DPMProductionServer.md)
Disables a DPM protection agent.

### [Disable-DPMTapeDrive](./Disable-DPMTapeDrive.md)
Disables a tape drive in the DPM library.

### [Disconnect-DPMServer](./Disconnect-DPMServer.md)
Closes a DPM connection session.

### [Dismount-DPMRecoveryPoint](./Dismount-DPMRecoveryPoint.md)
Dismounts the replica or recovery point VHD of a data source.

### [Edit-DPMDiskAllocation](./Edit-DPMDiskAllocation.md)
Modifies disk allocation for a protected data source on a DPM server.

### [Enable-DPMLibrary](./Enable-DPMLibrary.md)
Enables DPM libraries.

### [Enable-DPMProductionServer](./Enable-DPMProductionServer.md)
Enables a DPM protection agent.

### [Enable-DPMTapeDrive](./Enable-DPMTapeDrive.md)
Enables the tape drives in the DPM library.

### [Get-DPMAccessLicense](./Get-DPMAccessLicense.md)
Gets licensing information for a DPM server and protected computers.

### [Get-DPMAlert](./Get-DPMAlert.md)
Gets alerts for a DPM server.

### [Get-DPMAutoProtectIntent](./Get-DPMAutoProtectIntent.md)
Gets the auto-protection setting for a SQL Server instance.

### [Get-DPMBackupNetworkAddress](./Get-DPMBackupNetworkAddress.md)
Gets addresses of backup networks for a DPM server.

### [Get-DPMBackupWindow](./Get-DPMBackupWindow.md)
Gets the backup window settings for a protection group.

### [Get-DPMChildDatasource](./Get-DPMChildDatasource.md)
Returns the protectable file system objects in a data source.

### [Get-DPMCloudCertificateListFromLocalStore](./Get-DPMCloudCertificateListFromLocalStore.md)


### [Get-DPMCloudDatasource](./Get-DPMCloudDatasource.md)
Retrieves a list of cloud-protected data sources, protected by a DPM Server registered to the same vault as the local DPM Server.

### [Get-DPMCloudRecoveryService](./Get-DPMCloudRecoveryService.md)
Gets a backup Cloud Service resource.

### [Get-DPMCloudRegisteredServers](./Get-DPMCloudRegisteredServers.md)
Retrieves a list of servers registered to the specified vault.

### [Get-DPMCloudSubscription](./Get-DPMCloudSubscription.md)
Gets an Azure Online Backup subscription object.

### [Get-DPMCloudSubscriptionSetting](./Get-DPMCloudSubscriptionSetting.md)
Returns configuration settings for an Azure Online Backup subscription.

### [Get-DPMConsistencyCheckWindow](./Get-DPMConsistencyCheckWindow.md)
Gets the consistency check window settings for a protection group.

### [Get-DPMDatasetStatus](./Get-DPMDatasetStatus.md)
Gets the status of datasets on an archive tape.

### [Get-DPMDatasource](./Get-DPMDatasource.md)
Gets protected and unprotected data in a computer or protection group.

### [Get-DPMDatasourceProtectionOption](./Get-DPMDatasourceProtectionOption.md)
Returns protection options in a protection group.

### [Get-DPMDiskStorage](./Get-DPMDiskStorage.md)
Retrieves list of disks and volumes on a DPM server.

### [Get-DPMGlobalProperty](./Get-DPMGlobalProperty.md)
Retrieves the global properties for a DPM server.

### [Get-DPMHeadlessDataset](./Get-DPMHeadlessDataset.md)
Returns incomplete datasets on the archive tape.

### [Get-DPMInitialOnlineBackupCreationMethod](./Get-DPMInitialOnlineBackupCreationMethod.md)
Gets the method of initial online backup for a protection group.

### [Get-DPMJob](./Get-DPMJob.md)
Gets current and previous jobs on a DPM server.

### [Get-DPMLibrary](./Get-DPMLibrary.md)
Gets libraries associated with a DPM server.

### [Get-DPMMaintenanceJobStartTime](./Get-DPMMaintenanceJobStartTime.md)
Gets the start times of DPM maintenance jobs.

### [Get-DPMModifiableProtectionGroup](./Get-DPMModifiableProtectionGroup.md)
Gets a DPM protection group in an editable mode.

### [Get-DPMPGSet](./Get-DPMPGSet.md)
Gets protection group sets on a DPM server.

### [Get-DPMPolicyObjective](./Get-DPMPolicyObjective.md)
Gets the protection policy for a protection group.

### [Get-DPMPolicySchedule](./Get-DPMPolicySchedule.md)
Returns the schedule for protection jobs.

### [Get-DPMProductionCluster](./Get-DPMProductionCluster.md)
Gets clusters on which the DPM agent is installed.

### [Get-DPMProductionServer](./Get-DPMProductionServer.md)
Gets computers on which the DPM protection agent is installed.

### [Get-DPMProductionVirtualName](./Get-DPMProductionVirtualName.md)
Gets the virtual names for a cluster.

### [Get-DPMProtectionGroup](./Get-DPMProtectionGroup.md)
Gets the protection groups on a DPM server.

### [Get-DPMProtectionGroupSla](./Get-DPMProtectionGroupSla.md)
Gets the SLA for a protection group.

### [Get-DPMProtectionJobStartTime](./Get-DPMProtectionJobStartTime.md)
Gets the start time of a protection job.

### [Get-DPMRecoverableItem](./Get-DPMRecoverableItem.md)
Gets a list of recoverable items in a recovery point.

### [Get-DPMRecoveryItem](./Get-DPMRecoveryItem.md)


### [Get-DPMRecoveryPoint](./Get-DPMRecoveryPoint.md)
Gets recovery points for a data source.

### [Get-DPMRecoveryPointLocation](./Get-DPMRecoveryPointLocation.md)
Gets the location of a recovery point.

### [Get-DPMRecoveryTarget](./Get-DPMRecoveryTarget.md)


### [Get-DPMReplicaCreationMethod](./Get-DPMReplicaCreationMethod.md)
Gets the replica creation method for a protection group.

### [Get-DPMRole](./Get-DPMRole.md)
Gets a DPM role to view or edit.

### [Get-DPMSecurityGroup](./Get-DPMSecurityGroup.md)
Gets the security groups for a DPM role.

### [Get-DPMTape](./Get-DPMTape.md)
Returns tapes in the library.

### [Get-DPMTapeBackupOption](./Get-DPMTapeBackupOption.md)
Retrieves library, drive, and other backup or archive options for a protection group.

### [Get-DPMTapeDrive](./Get-DPMTapeDrive.md)
Retrieves the tape drives in a library.

### [Get-DPMTapeSlot](./Get-DPMTapeSlot.md)
Gets tape slots in the DPM library.

### [Get-DPMVolume](./Get-DPMVolume.md)
Gets the volumes on the DPM server.

### [Lock-DPMLibraryDoor](./Lock-DPMLibraryDoor.md)
Locks the door of a DPM library.

### [Lock-DPMLibraryIEPort](./Lock-DPMLibraryIEPort.md)
Locks the I/E port for a DPM library and loads the media present in the I/E port.

### [Mount-DPMRecoveryPoint](./Mount-DPMRecoveryPoint.md)
Mounts the replica or recovery point VHD of a data source.

### [New-DPMPGSet](./New-DPMPGSet.md)
Creates a DPM protection group set.

### [New-DPMProtectionGroup](./New-DPMProtectionGroup.md)
Creates a protection group on the DPM server.

### [New-DPMRecoveryNotification](./New-DPMRecoveryNotification.md)
Creates a notification object.

### [New-DPMRecoveryOption](./New-DPMRecoveryOption.md)
Creates recovery options.

### [New-DPMRecoveryPoint](./New-DPMRecoveryPoint.md)
Creates a recovery point.

### [New-DPMRecoveryTarget](./New-DPMRecoveryTarget.md)


### [New-DPMRole](./New-DPMRole.md)
Creates a DPM role.

### [New-DPMSearchOption](./New-DPMSearchOption.md)
Creates an object that specifies search options for recoverable objects.

### [New-DPMServerScope](./New-DPMServerScope.md)
Creates a DPM server scope object.

### [Remove-DPMBackupNetworkAddress](./Remove-DPMBackupNetworkAddress.md)
Removes a backup network from a DPM server.

### [Remove-DPMChildDatasource](./Remove-DPMChildDatasource.md)
Removes a data source or child data source from a protection group.

### [Remove-DPMDatasourceReplica](./Remove-DPMDatasourceReplica.md)
Removes an inactive replica.

### [Remove-DPMDiskStorage](./Remove-DPMDiskStorage.md)
Removes disk-based storage from the storage pool on a DPM server.

### [Remove-DPMPGSet](./Remove-DPMPGSet.md)
Deletes a protection group set.

### [Remove-DPMRecoveryItem](./Remove-DPMRecoveryItem.md)


### [Remove-DPMRecoveryPoint](./Remove-DPMRecoveryPoint.md)
Removes a recovery point from tape or disk.

### [Remove-DPMRecoveryTarget](./Remove-DPMRecoveryTarget.md)


### [Remove-DPMRole](./Remove-DPMRole.md)
Deletes a DPM role.

### [Remove-DPMSecurityGroup](./Remove-DPMSecurityGroup.md)
Removes security groups from a DPM role.

### [Remove-DPMTape](./Remove-DPMTape.md)
Removes a tape from a DPM library.

### [Rename-DPMLibrary](./Rename-DPMLibrary.md)
Renames a DPM library.

### [Rename-DPMProtectionGroup](./Rename-DPMProtectionGroup.md)
Renames a protection group.

### [Rename-DPMRole](./Rename-DPMRole.md)
Changes the name or description of a DPM role.

### [Restart-DPMJob](./Restart-DPMJob.md)
Restarts failed DPM jobs.

### [Restore-DPMRecoverableItem](./Restore-DPMRecoverableItem.md)
Restores a version of the data source to a target location.

### [Resume-DPMBackup](./Resume-DPMBackup.md)
Attempts to resume stalled DPM backup jobs.

### [Set-DPMAutoProtectIntent](./Set-DPMAutoProtectIntent.md)
Turns DPM auto-protection on or off for a SQL Server instance.

### [Set-DPMBackupWindow](./Set-DPMBackupWindow.md)
Sets the backup window settings for a protection group.

### [Set-DPMCloudSubscriptionSetting](./Set-DPMCloudSubscriptionSetting.md)
Updates subscription settings in Azure Online Backup for a DPM server.

### [Set-DPMConsistencyCheckWindow](./Set-DPMConsistencyCheckWindow.md)
Sets the consistency check window for a protection group.

### [Set-DPMCredentials](./Set-DPMCredentials.md)
Configures authentication for computers in untrusted domains.

### [Set-DPMDatasourceDefaultDiskAllocation](./Set-DPMDatasourceDefaultDiskAllocation.md)
Retrieves the amount of disk space that is allocated to protected data.

### [Set-DPMDatasourceDiskAllocation](./Set-DPMDatasourceDiskAllocation.md)
Changes disk allocation for protected data.

### [Set-DPMDatasourceProtectionOption](./Set-DPMDatasourceProtectionOption.md)
Sets protection options for a DPM data source.

### [Set-DPMGlobalProperty](./Set-DPMGlobalProperty.md)
Sets the global properties for a DPM installation.

### [Set-DPMInitialOnlineBackupCreationMethod](./Set-DPMInitialOnlineBackupCreationMethod.md)
Modifies the method of initial online backup for a protection group.

### [Set-DPMMaintenanceJobStartTime](./Set-DPMMaintenanceJobStartTime.md)
Sets the start time of a maintenance job or stops such a job from running.

### [Set-DPMPerformanceOptimization](./Set-DPMPerformanceOptimization.md)
Enables or disables on-the-wire compression for a DPM protection group.

### [Set-DPMPolicyObjective](./Set-DPMPolicyObjective.md)
Sets the policy objective for a protection group.

### [Set-DPMPolicySchedule](./Set-DPMPolicySchedule.md)
Sets the schedule for protection jobs.

### [Set-DPMProtectionGroup](./Set-DPMProtectionGroup.md)
Saves all the actions performed on the protection group on the DPM server.

### [Set-DPMProtectionGroupSla](./Set-DPMProtectionGroupSla.md)
Sets an SLA for a protection group.

### [Set-DPMProtectionJobStartTime](./Set-DPMProtectionJobStartTime.md)
Sets the start time of a protection job.

### [Set-DPMProtectionType](./Set-DPMProtectionType.md)
Sets the protection type for a protection group.

### [Set-DPMReplicaCreationMethod](./Set-DPMReplicaCreationMethod.md)
Sets the replica creation method for disk-based protection.

### [Set-DPMRole](./Set-DPMRole.md)
Saves changes to a DPM role.

### [Set-DPMTape](./Set-DPMTape.md)
Marks a tape as Archive, Cleaner, Free or Not Free.

### [Set-DPMTapeBackupOption](./Set-DPMTapeBackupOption.md)
Modifies the tape backup and library options for a DPM protection group.

### [Start-DPMAutoProtection](./Start-DPMAutoProtection.md)
Adds SQL Server databases to a DPM protection group.

### [Start-DPMCloudRecatalog](./Start-DPMCloudRecatalog.md)
Recatalogs a cloud recovery point.

### [Start-DPMCloudRegistration](./Start-DPMCloudRegistration.md)
Registers a DPM server with Azure Online Backup service to enable online protection.

### [Start-DPMCreateCatalog](./Start-DPMCreateCatalog.md)
Creates a catalog for a data source.

### [Start-DPMDatasourceConsistencyCheck](./Start-DPMDatasourceConsistencyCheck.md)
Performs a consistency check on a DPM data source.

### [Start-DPMDiskRescan](./Start-DPMDiskRescan.md)
Scans for disks and disk configuration changes.

### [Start-DPMLibraryInventory](./Start-DPMLibraryInventory.md)
Starts an inventory of tapes in a DPM library.

### [Start-DPMLibraryRescan](./Start-DPMLibraryRescan.md)
Starts a scan to identify new libraries and update existing libraries.

### [Start-DPMManualReplicaCreation](./Start-DPMManualReplicaCreation.md)
Prepares a replica VHD for manual data copy.

### [Start-DPMOnlineRecatalog](./Start-DPMOnlineRecatalog.md)
Returns a detailed list of data for a DPM recovery point.

### [Start-DPMProductionServerSwitchProtection](./Start-DPMProductionServerSwitchProtection.md)


### [Start-DPMSwitchProtection](./Start-DPMSwitchProtection.md)
Switches protection of data sources to a secondary DPM server.

### [Start-DPMTapeDriveCleaning](./Start-DPMTapeDriveCleaning.md)
Starts a job to clean a tape drive.

### [Start-DPMTapeErase](./Start-DPMTapeErase.md)
Deletes the contents of a tape.

### [Start-DPMTapeRecatalog](./Start-DPMTapeRecatalog.md)
Recatalogs the data on a tape.

### [Stop-DPMJob](./Stop-DPMJob.md)
Stops DPM jobs.

### [Stop-DPMManualReplicaCreation](./Stop-DPMManualReplicaCreation.md)
Unmounts a replica VHD after manual data copy.

### [Test-DPMTapeData](./Test-DPMTapeData.md)
Verifies a data set for a recovery point.

### [Unlock-DPMLibraryDoor](./Unlock-DPMLibraryDoor.md)
Unlocks the door of a DPM library.

### [Unlock-DPMLibraryIEPort](./Unlock-DPMLibraryIEPort.md)
Unlocks the I/E port for a DPM library.

### [Update-DPMDiskStorage](./Update-DPMDiskStorage.md)
Updates properties of a volume in the storage pool on a DPM server.

### [Update-DPMPGSet](./Update-DPMPGSet.md)
Updates and saves changes to a protection group set.

### [Update-DPMProductionServer](./Update-DPMProductionServer.md)
Gets updated information about a protected computer.

### [Update-DPMProtectionGroup](./Update-DPMProtectionGroup.md)
Updates a protection group configuration.

