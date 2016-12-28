---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F3A58022-E6BA-42C7-80BB-75BD769C77E0
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMInitialOnlineBackupCreationMethod.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMInitialOnlineBackupCreationMethod.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMInitialOnlineBackupCreationMethod.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMInitialOnlineBackupCreationMethod

## SYNOPSIS
Modifies the method of initial online backup for a protection group.

## SYNTAX

```
Set-DPMInitialOnlineBackupCreationMethod [-ProtectionGroup] <ProtectionGroup>
 [-IBMethod] <InitialOnlineBackupMethodType> [[-StagingLocation] <String>] [[-AzurePublishSettings] <String>]
 [[-AzureImportJobName] <String>] [[-AzureSubscriptionID] <String>] [[-AzureStorageAccount] <String>]
 [[-AzureStorageContainer] <String>] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMInitialOnlineBackupCreationMethod** cmdlet modifies the method of initial online backup.
Specify a method for a System Center 2016 - Data Protection Manager (DPM) protection group during creation of that protection group.
You can select Network or OfflineBackup as the initial online backup method.

## EXAMPLES

### Example 1: Modify the initial online backup method for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Set-InitialOnlineBackupCreationMethod -ProtectionGroup $PGroup -IBMethod Network
```

The first command gets a protection group that has DPM server name DPMServer02, and then stores it in the $PGroup variable.

The second command sets the initial online backup method for the group in $PGroup to be Network.

### Example 2: Set the initial online backup method as OfflineBackup for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Set-InitialOnlineBackupCreationMethod -ProtectionGroup $PGroup -IBMethod OfflineBackup -StagingLocation 'C:\StagingLocation' -AzurePublishSettings 'C:\Files\AzurePublishSettings.publishsettings' -AzureImportJobName 'ImportJobName' -AzureSubscriptionID 7c9e6679-7425-40de-944b-e07fc1f90ae7 -AzureStorageAccount 'AccountName' -AzureStorageContainer 'ContainerName'
```

The first command gets a protection group that has DPM server name DPMServer02, and then stores it in the $PGroup variable.

The second command sets the initial online backup method for the group stored in $PGroup to be OfflineBackup.

## PARAMETERS

### -AzureImportJobName
Specifies the name of the Azure import job.
The value of this parameter is used as a reference to ship the initial copy of disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzurePublishSettings
Specifies the Azure publish settings file for the Azure account where the initial backup copy is shipped.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureStorageAccount
Specifies the Azure Storage account associated with the Azure import job that the *AzureImportJobName* parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureStorageContainer
Specifies the destination blob storage container to which to import the files.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AzureSubscriptionID
Specifies the Azure subscription ID associated with the Azure import job that the *AzureImportJobName* parameter specifies.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IBMethod
Specifies the method of initial online backup.

The acceptable values for this parameter are:

- Network
- OfflineBackup

```yaml
Type: InitialOnlineBackupMethodType
Parameter Sets: (All)
Aliases: 
Accepted values: Network, OfflineBackup

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group on which this cmdlet operates.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StagingLocation
Specifies a staging location for the initial backup copy.
You can specify a local folder or network shared folder.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

[Get-DPMInitialOnlineBackupCreationMethod](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMInitialOnlineBackupCreationMethod.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

