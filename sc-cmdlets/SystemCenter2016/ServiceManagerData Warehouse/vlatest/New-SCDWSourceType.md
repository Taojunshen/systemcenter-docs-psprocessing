---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: a3467fe7-f0e7-41fd-9453-0b01c43f122d
schema: 2.0.0
ms.assetid: 8471C34D-0953-4082-ABD9-7BF2BB506898
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/New-SCDWSourceType.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/New-SCDWSourceType.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/New-SCDWSourceType.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCDWSourceType

## SYNOPSIS
Creates a data source type that can be registered to the data warehouse.

## SYNTAX

```
New-SCDWSourceType [-SourceConfigFile] <String> [-ComputerName <String>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCDWSourceType** cmdlet creates a new data source type that can be registered to the data warehouse.
Each data source type is defined by the classes and the relationships in the management pack bundle that is imported when the data source type is defined.

## EXAMPLES

### Example 1: Create a data source type from a management pack bundle
```
PS C:\>New-SCDWSourceType -ComputerName "serverDW72" -SourceConfigFile "C:\Program Files\Microsoft System Center\Management Packs\CustomHumanRelationsDataSource.mpb"
```

This command creates a new data source type from a specified management pack bundle.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
The user account that is defined in the *Credential* parameter must have access rights to the specified computer.

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
The user account that is provided must have access to that server.

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

### -SourceConfigFile
Specifies the path to the management pack bundle (.mpb) file that contains the management packs and other resources that define the data source.

Each management pack in the management pack bundle must contain a class that derives from the **Microsoft.SystemCenter.DataWarehouse.DataSource** class, and an enumeration that derives from **DW.DataSourceType**.
The base class and the enumeration must exist in the **Microsoft.SystemCenter.DataWarehouse.Base.mp** management pack.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

