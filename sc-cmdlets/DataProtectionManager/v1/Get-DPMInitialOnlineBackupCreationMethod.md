---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMInitialOnlineBackupCreationMethod.md
schema: 2.0.0
ms.assetid: 4344048C-15A8-4E67-ACD7-44FF631BDBBB
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMInitialOnlineBackupCreationMethod.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMInitialOnlineBackupCreationMethod.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMInitialOnlineBackupCreationMethod.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMInitialOnlineBackupCreationMethod

## SYNOPSIS
Gets the method of initial online backup for a protection group.

## SYNTAX

```
Get-DPMInitialOnlineBackupCreationMethod [-ProtectionGroup] <ProtectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMInitialOnlineBackupCreationMethod** cmdlet gets the method of initial online backup for a System Center 2016 - Data Protection Manager (DPM) protection group.

## EXAMPLES

### Example 1: Get initial online backup method for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup | Where {$_.FriendlyName -like "MyPG"}
PS C:\> Get-DPMInitialOnlineBackupCreationMethod -ProtectionGroup $PGroup
```

The first command gets a protection group by using the **Get-DPMProtectionGroup** cmdlet.
That cmdlet gets all protection groups, and passes them to the **Where-Object** cmdlet by using the pipeline operator.
That cmdlet finds the desired group, and then stores that group in the $PGroup variable.
For more information, type `Get-Help Where-Object`.

The second command gets the method of initial online backup for the protection group in $PGroup.

## PARAMETERS

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets an online backup method.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.OMCommon.InitialOnlineBackupMethod
This cmdlet generates an **InitialOnlineBackupMethod** object that contains the following properties: 

- **IBMethod**.
The method of initial online backup.
Valid values are: Network and OfflineBackup.
- **OfflineBackupParams**.
The offline backup properties are the following: **StagingLocation**, **AzurePublishSettingsFile**, **AzureImportJobName**, **AzureSubscriptionID**, **AzureStorageAccount**, and **AzureStorageContainer**.

## NOTES

## RELATED LINKS

[Set-DPMInitialOnlineBackupCreationMethod](xref:DataProtectionManager/v1/Set-DPMInitialOnlineBackupCreationMethod.md)

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

