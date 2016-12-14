---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8B8FA797-FAAC-4969-80DE-D29FB99AAEDA
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMCloudRecoveryService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMCloudRecoveryService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMCloudRecoveryService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMCloudRecoveryService

## SYNOPSIS
Gets a backup Cloud Service resource.

## SYNTAX

### CloudRegistrationByCertificate
```
Get-DPMCloudRecoveryService [[-DPMServerName] <String>] [-Certificate] <CloudCertificate> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CloudRegistrationByVaultCredentialFile
```
Get-DPMCloudRecoveryService [[-DPMServerName] <String>] [-VaultCredentialsFilePath] <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMCloudRecoveryService** cmdlet gets a Windows Azure Online Backup Cloud Service resource object.

## EXAMPLES

### Example 1: Returns the cloud service resource for given vault credential file
```
PS C:\>Get-DPMCloudRecoveryService -DPMServerName "TestingServer" -VaultCredentialsFilePath "DPMTESTVault_Friday, September 5, 2014.VaultCredentials"
```

This command returns the Azure Online Backup recovery resource for the DPM server named TestingServer that has vault credential file DPMTESTVault_Friday, September 5, 2014.VaultCredentials.

## PARAMETERS

### -Certificate
Specifies a certificate.

```yaml
Type: CloudCertificate
Parameter Sets: CloudRegistrationByCertificate
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of the System Center 2016 - Data Protection Manager (DPM) server on which this cmdlet acts.

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

### -VaultCredentialsFilePath
Specifies the vault credential file path for the Azure online backup.
Specify a network path for a remote user interface.

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

### CloudServiceResource

## NOTES

## RELATED LINKS

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/v1.0/DataProtectionManager.md)

