---
external help file: OperationsManager-help.xml
online version: 
schema: 2.0.0
ms.assetid: 9696F840-117E-4AD6-85FD-977E41CBBFE6
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/New-DefaultManagementGroupConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/New-DefaultManagementGroupConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/New-DefaultManagementGroupConnection.md
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

