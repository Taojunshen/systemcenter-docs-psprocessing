---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239484
schema: 2.0.0
ms.assetid: 9696F840-117E-4AD6-85FD-977E41CBBFE6
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/New-DefaultManagementGroupConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/New-DefaultManagementGroupConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/New-DefaultManagementGroupConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DefaultManagementGroupConnection

## SYNOPSIS
Creates a default management group connection.

## SYNTAX

```
New-DefaultManagementGroupConnection [[-managementServerName] <String>] [[-persistConnection] <Boolean>]
 [[-interactive] <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **New-DefaultManagementGroupConnection** cmdlet creates a default management group connection.

## EXAMPLES

### Example 1: Create a connection
```
PS C:\>New-DefaultManagementGroupConnection -managementServerName "server01.contoso.com"
```

This command creates a default management group connection.

## PARAMETERS

### -interactive
Specifies whether the connection is interactive.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -managementServerName
Specifies the name of the management server for the connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -persistConnection
Specifies whether the connection persists.

```yaml
Type: Boolean
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

