---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 96d82e13-7c44-4002-9520-ceadb1770bcc
schema: 2.0.0
ms.assetid: 4F43534F-4EC0-41E9-A565-E665D557C6B5
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/Get-SCDWSourceType.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/Get-SCDWSourceType.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/Get-SCDWSourceType.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDWSourceType

## SYNOPSIS
Gets the types of data sources that can be registered to the data warehouse.

## SYNTAX

```
Get-SCDWSourceType [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWSourceType** cmdlet gets the types of data sources that can be registered to the data warehouse.

For updated information about this cmdlet, see Get-SCDWSourceTypehttp://go.microsoft.com/fwlink/p/?LinkId=234995.

## EXAMPLES

### Example 1: Get available data source types
```
PS C:\>Get-SCDWSourceType â€"ComputerName "serverDW72"
```

This command gets the available source types.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
The user account that is defined in the **Credential** parameter must have access rights to the specified computer.
You can omit this parameter only if the System Center Data Access Service is running on the same computer that has Service Manager installed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials to use when you are connecting to the server on which the System Center Data Access service is running.
The provided user account must have access to that server.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Warehouse.Cmdlets.GetSCDWSourceType+DataSourceType

## NOTES

## RELATED LINKS

