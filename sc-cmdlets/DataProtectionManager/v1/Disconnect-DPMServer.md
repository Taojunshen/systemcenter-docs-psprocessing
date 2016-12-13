---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Connect-DPMServer.md
schema: 2.0.0
ms.assetid: D464A43B-54C6-44D3-BD60-12592991E99A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Disconnect-DPMServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Disconnect-DPMServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Disconnect-DPMServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disconnect-DPMServer

## SYNOPSIS
Closes a DPM connection session.

## SYNTAX

```
Disconnect-DPMServer [[-DPMServerName] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-DPMServer** cmdlet closes a System Center 2016 - Data Protection Manager (DPM) connection session and releases all objects for that session.
Specify a connection to close by using the name of a DPM server.

## EXAMPLES

### Example 1: Disconnect a server
```
PS C:\>Disconnect-DPMServer -DPMServerName "DPMServer07"
```

This command closes a connection to a DPM server named DPMServer07.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet closes a connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
Position: 1
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

[Connect-DPMServer](xref:DataProtectionManager/v1/Connect-DPMServer.md)

