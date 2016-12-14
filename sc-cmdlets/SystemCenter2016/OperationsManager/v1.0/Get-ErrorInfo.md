---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=212927
schema: 2.0.0
ms.assetid: 8E837BD2-5C0C-4FDF-B5F2-190965A288FD
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-ErrorInfo.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-ErrorInfo.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-ErrorInfo.md
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

