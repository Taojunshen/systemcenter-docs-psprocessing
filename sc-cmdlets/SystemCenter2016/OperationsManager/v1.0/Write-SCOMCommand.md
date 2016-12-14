---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239456
schema: 2.0.0
ms.assetid: D734B081-C824-4EE3-9CDE-3C7AB05E173F
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Write-SCOMCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Write-SCOMCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Write-SCOMCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Write-SCOMCommand

## SYNOPSIS
Writes a new command to interact with Operations Manager.

## SYNTAX

### Name (Default)
```
Write-SCOMCommand -Name <String> [<CommonParameters>]
```

### NoName
```
Write-SCOMCommand [-NoName] [<CommonParameters>]
```

## DESCRIPTION
The **Write-SCOMCommand** cmdlet writes a new Windows PowerShell command to interact with System Center 2016 - Operations Manager.
The new command uses the same common SDK connection code as the standard Operations Manager cmdlets.

## EXAMPLES

### Example 1: Write a new script command
```
PS C:\>Write-SCOMCommand -Name "Test-DivBManagementPack"
```

This command outputs a new script command template named Test-DivBManagementPack.

## PARAMETERS

### -Name
Specifies the name of the command.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoName
Indicates that the cmdlet creates an unnamed script.

```yaml
Type: SwitchParameter
Parameter Sets: NoName
Aliases: 

Required: True
Position: Named
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

[Get-SCOMCommand](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMCommand.md)

