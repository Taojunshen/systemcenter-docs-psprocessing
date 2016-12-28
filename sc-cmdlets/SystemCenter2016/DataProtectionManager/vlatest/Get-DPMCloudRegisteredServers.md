---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B21AEC12-9498-4377-A569-43572122B50D
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudRegisteredServers.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudRegisteredServers.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudRegisteredServers.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMCloudRegisteredServers

## SYNOPSIS
Gets a list of servers registered to the specified vault.

## SYNTAX

```
Get-DPMCloudRegisteredServers [[-DPMServerName] <String>] [-VaultCredentialsFilePath] <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMCloudRegisteredServers** cmdlet gets a list of servers registered to a vault.
This should be the same vault to which the local System Center 2016 - Data Protection Manager (DPM) Server, which is specified in the *DPMServerName* parameter, is registered.

## EXAMPLES

### Example 1: Get the servers registered to a vault to which the local DPM server is registered
```
PS C:\>$RS = Get-DPMCloudRegisteredServers -VaultCredentialsFilePath "DPMTESTVault_Friday, September 5, 2014.VaultCredentials"
```

This command returns the servers registered to the vault for which the vault credential file is DPMTESTVault_Friday, September 5, 2014.VaultCredentials.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM Server.

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
The vault credential file should be from the vault to which the local DPM Server is registered.

```yaml
Type: String
Parameter Sets: (All)
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

[Get-DPMCloudDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudDatasource.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)
