---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMCloudRecoveryService.md
schema: 2.0.0
ms.assetid: 21558253-62EA-4A3B-89AD-4231C78CF15D
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Start-DPMCloudRegistration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Start-DPMCloudRegistration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Start-DPMCloudRegistration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMCloudRegistration

## SYNOPSIS
Registers a DPM server with Azure Online Backup service to enable online protection.

## SYNTAX

### CloudRegistrationByServiceResource
```
Start-DPMCloudRegistration [[-DPMServerName] <String>] [-RecoveryService] <CloudServiceResource> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### CloudRegistrationByVaultCredentialFile
```
Start-DPMCloudRegistration [[-DPMServerName] <String>] [-VaultCredentialsFilePath] <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMCloudRegistration** cmdlet registers a System Center 2016 - Data Protection Manager (DPM) server with Azure Online Backup service to enable online protection.

## EXAMPLES

### Example 1: Register a server with Azure Online Backup using cloud recovery source
```
PS C:\>$ContosoResource = Get-DPMCloudRecoveryService -DPMServerName "TestingServer" -VaultCredentialsFilePath "DPMTESTVault_Friday, September 5, 2014.VaultCredentials"
PS C:\> Start-DPMCloudRegistration -DPMServerName "TestingServer" -RecoveryService $ContosoResource
```

The first command gets the cloud service resource from the vault credential file.

The second command registers the DPM server named TestingServer with Azure Online Backup by using the cloud service resource.

### Example 2: Register a server with Azure Online Backup using vault credential file
```
PS C:\>Start-DPMCloudRegistration -DPMServerName "TestingServer" -VaultCredentialsFilePath "C:\DPMTESTVault_Friday, September 5, 2014.VaultCredentials"
```

This command registers a DPM server named TestingServer with Azure Online Backup by using vault credential file C:\DPMTESTVault_Friday, September 5, 2014.VaultCredentials.

## PARAMETERS

### -DPMServerName
Specifies the name of the DPM server that this cmdlet registers.

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

### -RecoveryService
Specifies the Cloud recovery resource for the backup vault on Azure Online Backup.

```yaml
Type: CloudServiceResource
Parameter Sets: CloudRegistrationByServiceResource
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VaultCredentialsFilePath
Specifies the vault credential file path for the Azure Online Backup.
Specify a network path for a remote user interface .

```yaml
Type: String
Parameter Sets: CloudRegistrationByVaultCredentialFile
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

[Get-DPMCloudRecoveryService](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMCloudRecoveryService.md)

