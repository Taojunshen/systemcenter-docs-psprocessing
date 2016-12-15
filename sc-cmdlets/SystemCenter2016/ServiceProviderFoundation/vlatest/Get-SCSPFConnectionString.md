---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkID=330321
schema: 2.0.0
ms.assetid: 4BA1E347-8216-43EC-935F-0B1C282F00BB
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFConnectionString.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFConnectionString.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFConnectionString.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfConnectionString

## SYNOPSIS
Gets the connection string for the database used by the Service Provider Foundation service.

## SYNTAX

```
Get-SCSpfConnectionString [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFConnectionString** cmdlet gets the connection string for the database used by the Service Provider Foundation service.
The database and the Service Provider Foundation service do not have to be on the same server.
This cmdlet requires that you run Windows PowerShell as an administrator.

## EXAMPLES

### Example 1: Get the connection string
```
PS C:\>Get-SCSPFConnectionString
```

This command gets the connection string for the database used by the Service Provider Foundation service.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-SCSPFConnectionString](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFConnectionString.md)

