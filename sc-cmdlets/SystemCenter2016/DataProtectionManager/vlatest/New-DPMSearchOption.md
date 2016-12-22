---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 52AFBDC1-2746-4798-BCC7-6899C050DAF0
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMSearchOption.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMSearchOption.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMSearchOption.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DPMSearchOption

## SYNOPSIS
Creates an object that specifies search options for recoverable objects.

## SYNTAX

```
New-DPMSearchOption [-FromRecoveryPoint] <DateTime> [-ToRecoveryPoint] <DateTime>
 [-SearchDetail] <SearchForDetail> [-SearchType] <SearchFilterType> [-SearchString] <String>
 [-Location <String>] [-Recursive] [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMSearchOption** cmdlet creates an object that specifies search options for recoverable objects that System Center 2016 - Data Protection Manager (DPM) manages.
You can specify a search string, a range of recovery points to search, the type of object to search for, and also a location and whether to search recursively.

Use the Get-DPMRecoverableItem cmdlet to perform a search.

## EXAMPLES

### Example 1: Create a search option
```
PS C:\>New-DPMSearchOption -FromRecoveryPoint "15 September 2009" -ToRecoveryPoint "28 September 2009" -SearchDetail FileFolders -SearchType contains -Recursive -SearchString "tobe" -Location "D:\"
```

This command creates a search option object for recovery points between September 15, 2009 and September 28, 2009.
The object specifies searches for files and folders that contain the string to be in the location D:\.
The command specifies the search as recursive.
Therefore, the search also checks files and folders in folders in the D:\ drive.

## PARAMETERS

### -FromRecoveryPoint
Specifies a date time object.
This is the first date of the search range.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Location
Specifies the location of a recovery point.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recursive
Indicates that the search is recursive.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchDetail
Specifies the type of object to search for.

The acceptable values for this parameter are:

- FileFolders
- MailboxByAlias
- MailboxByDisplayName
- WssSite
- WssDocuments

```yaml
Type: SearchForDetail
Parameter Sets: (All)
Aliases: 
Accepted values: FilesFolders, MailboxByAlias, MailboxByDisplayName, WssSite, WssDocuments, ClientVolumes

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchString
Specifies a string to search for in the target recovery points.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchType
Specifies the type of comparison for the search.

The acceptable values for this parameter are:

- startsWith 
- contains
- endsWith 
- exactMatch

```yaml
Type: SearchFilterType
Parameter Sets: (All)
Aliases: 
Accepted values: startsWith, contains, endsWith, exactMatch

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToRecoveryPoint
Specifies a date time object.
This is the last date of the search range.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SearchOption

## NOTES

## RELATED LINKS

[Get-DPMRecoverableItem](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoverableItem.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

