---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Get-SCDWEntity.md
schema: 2.0.0
ms.assetid: 775D522C-34CD-46E1-AE2F-D552A2F710F7
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Set-SCDWRetentionPeriod.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Set-SCDWRetentionPeriod.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Set-SCDWRetentionPeriod.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCDWRetentionPeriod

## SYNOPSIS
Sets the data retention period for a fact table.

## SYNTAX

### EntitySet (Default)
```
Set-SCDWRetentionPeriod [-DurationInMinutes <Int32>] [-EntityName <String>] [-ComputerName <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DatamartConnectionSet
```
Set-SCDWRetentionPeriod [-DurationInMinutes <Int32>] [-EntityName <String>] [-DatamartComputerName] <String>
 [-DatamartDatabaseName] <String> [-ComputerName <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCDWRetentionPeriod** cmdlet sets the data retention period, in minutes, for either a specific fact table within a specific data warehouse database or the default for fact tables within the database.
Data that is eligible for grooming and older than the retention period will be groomed out of the database.

## EXAMPLES

### Example 1: Set a retention period
```
PS C:\>Set-SCDWRetentionPeriod -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "CMDWDataMart" -EntityName
"ComputerHasSoftwareUpdateInstalledFact" -DurationInMinutes 1576800
```

This command sets a retention period.

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

### -DatamartComputerName
Specifies the name of the computer on which the datamart resides.
This is usually the SQL database server that services the data warehouse.
If a value is not provided, the value is discovered by inspecting the warehouse configuration.

```yaml
Type: String
Parameter Sets: DatamartConnectionSet
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatamartDatabaseName
Specifies the name of the datamart database.
This is typically the SQL database server that services the data warehouse.
The default value is the warehouse repository.
You can retrieve the entities from the Staging or DataMart databases to provide a value for this parameter.

```yaml
Type: String
Parameter Sets: DatamartConnectionSet
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DurationInMinutes
Specifies the duration, in minutes, before the entity is groomed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntityName
Specifies the Dimension, Fact, or Outrigger on which to set the watermark.
You can use the **Get-SCDWEntity** cmdlet to retrieve entity names.

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

[Get-SCDWEntity](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Get-SCDWEntity.md)

