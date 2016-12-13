---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMBackupNetworkAddress.md
schema: 2.0.0
ms.assetid: 45B9517D-8879-4C76-9975-655FCECD6E6F
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Add-DPMBackupNetworkAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Add-DPMBackupNetworkAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Add-DPMBackupNetworkAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-DPMBackupNetworkAddress

## SYNOPSIS
Specifies a backup network for a DPM server.

## SYNTAX

```
Add-DPMBackupNetworkAddress [[-DPMServerName] <String>] [-Address] <String> [-SequenceNumber] <UInt32>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DPMBackupNetworkAddress** cmdlet specifies an address of a backup network for a System Center 2016 - Data Protection Manager (DPM) server to use.
DPM lets you configure backup network addresses so that DPM backups do not slow down your primary network.
Assign a priority for each backup network you add.

## EXAMPLES

### Example 1: Add a backup network address
```
PS C:\>Add-DPMBackupNetworkAddress -DpmServername "DPMServer07" -Address "10.10.10.0/16" -SequenceNumber 1
```

This command adds the subnet address 10.10.10.0/16 as the backup network address for a DPM server named DPMServer07.
The command specifies a sequence value of 1.

## PARAMETERS

### -Address
Specifies the IP address or subnet mask of a backup network that this cmdlet adds for the server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet adds an address.

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

### -SequenceNumber
Specifies the priority of this address for use as a backup network.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

[Get-DPMBackupNetworkAddress](xref:DataProtectionManager/v1/Get-DPMBackupNetworkAddress.md)

[Remove-DPMBackupNetworkAddress](xref:DataProtectionManager/v1/Remove-DPMBackupNetworkAddress.md)

