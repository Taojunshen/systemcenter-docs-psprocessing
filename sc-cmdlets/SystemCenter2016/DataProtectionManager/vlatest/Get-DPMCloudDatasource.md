---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 869BCA9D-8652-4C19-AE09-518EF7C108CF
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudDatasource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudDatasource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudDatasource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-DPMCloudDatasource

## SYNOPSIS
Gets a list of cloud-protected data sources, protected by a DPM Server registered to the same vault as the local DPM Server.

## SYNTAX

```
Get-DPMCloudDatasource [-CloudProtectedDPMServer] <CloudBackupServer> [-EncryptionPassphrase] <SecureString>
 [-Async] [[-JobStateChangedHandler] <JobStateChangedEventHandler>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMCloudDatasource** cmdlet gets a list of cloud-protected data sources that are protected by a System Center 2016 - Data Protection Manager (DPM) Server registered to the same vault as the local DPM Server.
This cmdlet can be used to get the data sources so that data can be recovered from the cloud recovery points of the data sources.

## EXAMPLES

### Example 1: Get cloud-protected data sources from a server
```
PS C:\> $RS = Get-DPMCloudRegisteredServers -VaultCredentialsFilePath "DPMTESTVault_Friday, September 5, 2014.VaultCredentials"
PS C:\> $Passphrase = ConvertTo-SecureString -string "passphrase123456789" -AsPlainText -Force
PS C:\> $CPD = Get-DPMCloudDatasource -CloudProtectedDPMServer $RS[0] -EncryptionPassphrase $Passphrase
```

The first command returns the servers registered to the vault for which vault credential file is DPMTESTVault_Friday, September 5, 2014.VaultCredentials.

The second command converts the string passphrase123456789 to a secure string and assigns the secure string to the variable named $Passphrase.

The third command returns the cloud-protected data sources from the first server in the list of servers returned by first command.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
The command prompt returns immediately even if the job takes an extended time to finish.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudProtectedDPMServer
Specifies a server from which a list of cloud-protected data sources are to be retrieved.
This server must be registered to the same vault as the local DPM Server.
Use the [Get-DPMCloudRegisteredServers](./Get-DPMCloudRegisteredServers.md) cmdlet to get a list of all the servers registered to a particular vault.

```yaml
Type: CloudBackupServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EncryptionPassphrase
Specifies a secure string that contains a passphrase.
This passphrase should be same as the latest passphrase set on the DPM server, from which the list of data sources is retrieved to encrypt cloud backups.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobStateChangedHandler
Specifies an event handler for **Job.StateChanged** events.
This is not needed when running in the Windows PowerShell console and is required only with a Graphical User Interface (GUI) application that is fetching data using Windows PowerShell.
Use this parameter in conjunction with the *Async* parameter.

```yaml
Type: JobStateChangedEventHandler
Parameter Sets: (All)
Aliases: Handler

Required: False
Position: 4
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

## NOTES

## RELATED LINKS

[Get-DPMCloudRegisteredServers](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudRegisteredServers.md)
