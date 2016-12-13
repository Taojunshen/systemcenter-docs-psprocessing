---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=199889
schema: 2.0.0
ms.assetid: A7C085B8-2FA8-453B-8239-1C3D306E12E5
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Out-StringNoWrap.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Out-StringNoWrap.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Out-StringNoWrap.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Out-StringNoWrap

## SYNOPSIS
Returns string that you specify.

## SYNTAX

```
Out-StringNoWrap [[-indent] <Int32>] [[-string] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Out-StringNoWrap** cmdlet returns a string that you specify with a specified indent.

## EXAMPLES

### Example 1: Return an indented string
```
PS C:\>Out-StringNoWrap -indent 20 -string "Hello, world"
                    Hello, world
```

This command returns a string with twenty spaces preceding it.

## PARAMETERS

### -indent
Specifies the number of spaces to indent the string.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -string
Specifies the string to return.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

