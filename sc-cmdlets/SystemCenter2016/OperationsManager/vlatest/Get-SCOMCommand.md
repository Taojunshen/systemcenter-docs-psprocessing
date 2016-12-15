---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239447
schema: 2.0.0
ms.assetid: EAF6274F-299B-45C2-82CC-593B28668B56
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMCommand

## SYNOPSIS
Gets Operations Manager commands in the current session.

## SYNTAX

### CmdletSet (Default)
```
Get-SCOMCommand [-Verb <String[]>] [-Noun <String[]>] [<CommonParameters>]
```

### AllCommandSet
```
Get-SCOMCommand [[-Name] <String[]>] [-CommandType <CommandTypes>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMCommand** cmdlet gets System Center 2016 - Operations Manager commands in the current session.
If you do not specify any parameters for the cmdlet, the cmdlet returns all commands in the current session.

## EXAMPLES

### Example 1: Get commands by using a name
```
PS C:\>Get-SCOMCommand "*agent*"
```

This command gets all commands in the Operations Manager module that have agent in the name of the command.

### Example 2: Get commands by using a cmdlet verb
```
PS C:\>Get-SCOMCommand -Verb "Get"
```

This command gets all commands in the Operations Manager module that use the verb Get.

## PARAMETERS

### -CommandType
Specifies a Operations Manager command type.

```yaml
Type: CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of Operations Manager commands.

```yaml
Type: String[]
Parameter Sets: AllCommandSet
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Noun
Specifies an array of nouns in Operations Manager cmdlet names.

```yaml
Type: String[]
Parameter Sets: CmdletSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Verb
Specifies an array of verbs in Operations Manager cmdlet names.

```yaml
Type: String[]
Parameter Sets: CmdletSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Write-SCOMCommand](xref:SystemCenter2016/OperationsManager/vlatest/Write-SCOMCommand.md)

