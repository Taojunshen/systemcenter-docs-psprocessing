---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Get-SCDWEntity.md
schema: 2.0.0
ms.assetid: 438B6165-EC62-48A6-A9F9-EF03F04B659F
updated_at: 12/15/2016 6:30 PM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWRetentionPeriod.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWRetentionPeriod.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/59ca46449cbaf6c065d4887fdd68c8de98ef34f0/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWRetentionPeriod.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDWRetentionPeriod

## SYNOPSIS
Gets the data retention period for a fact table.

## SYNTAX

### EntitySet (Default)
```
Get-SCDWRetentionPeriod [-EntityName <String>] [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### DatamartConnectionSet
```
Get-SCDWRetentionPeriod [-EntityName <String>] [-DatamartComputerName] <String>
 [-DatamartDatabaseName] <String> [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWRetentionPeriod** cmdlet gets the data retention period, in minutes, for either a specific fact table within a specific data warehouse database or for the default fact table within the database. 
The Data Warehouse grooms out rows after a predefined retention period.
Data that is eligible for grooming and that is older than the retention period will be groomed out of the database.

## EXAMPLES

### Example 1: Get the data retention period for an entity
```
PS C:\>Get-SCDWRetentionPeriod -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "DWDataMart" -EntityName "IncidentStatusDurationFact"
```

This command gets the data retention period for a specified entity name.

### Example 2: Populate a hash table with entity retention period information
```
PS C:\>$AllEntitiesRP = @{}
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "DWDatamart" | ForEach-Object {
>>     $ent = $_.EntityName
>>     $rp = Get-SCDWRetentionPeriod -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "DWDatamart" -Entity $ent
>>     $AllEntitiesRP.Add($ent + " (DWDatamart)", $rp.RetentionPeriodInMinutes)
>> }
>>
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "CMDWDatamart" | ForEach-Object {
>>     $ent = $_.EntityName
>>     $rp = Get-SCDWRetentionPeriod -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "CMDWDatamart" -Entity $ent
>>     $AllEntitiesRP.Add($ent + " (CMDWDatamart)", $rp.RetentionPeriodInMinutes)
>> }
>>
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "OMDWDatamart" | ForEach-Object {
>>     $ent = $_.EntityName
>>     $rp = Get-SCDWRetentionPeriod -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "OMDWDatamart" -Entity $ent
>>     $AllEntitiesRP.Add($ent + " (OMDWDatamart)", $rp.RetentionPeriodInMinutes)
}
```

The first command creates a variable for a hash table.

The second, third, and fourth commands populate the hash table with the retention period for each entity in three databases (`DWDatamart`, `CMDWDataMart`, and `OMDWDataMart`).
The key for the hash table is the entity name with its database name in parenthesis, and the value is the retention period.

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
This is usually the SQL database server that the data warehouse uses.
By default, smshort discovers the value by inspecting the data warehouse configuration.

```yaml
Type: String
Parameter Sets: DatamartConnectionSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatamartDatabaseName
Specifies the name of the database of the datamart.
This is usually the SQL database server that the data warehouse uses.
The default value is the data warehouse repository.
It is possible to retrieve the entities from the Staging or DataMart databases.

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

### -EntityName
Specifies the Dimension, Fact, or Outrigger on which to set the watermark.
You can use the **Get-SCDWEntity** cmdlet to retrieve the entities.

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

[Get-SCDWEntity](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWEntity.md)

