---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=212927
schema: 2.0.0
ms.assetid: 8E837BD2-5C0C-4FDF-B5F2-190965A288FD
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-ErrorInfo.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-ErrorInfo.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-ErrorInfo.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-ErrorInfo

## SYNOPSIS
Gets an error information object.

## SYNTAX

```
Get-ErrorInfo [[-errorIndex] <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-ErrorInfo** cmdlet gets an error information object.

## EXAMPLES

### 1:
```
PS C:\>Get-ErrorInfo -errorIndex 3
```

This command gets the error object at the index 3.

### 2:
```
PS C:\>Get-ErrorInfo
```

This command gets the error object at the index 0.
This is the most recent error object.

## PARAMETERS

### -errorIndex
Specifies the index of the error object to get.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

