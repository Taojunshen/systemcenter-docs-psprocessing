---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 96D82E13-7C44-4002-9520-CEADB1770BCC
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWEntity.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWEntity.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWEntity.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDWEntity

## SYNOPSIS
Gets the list of fact tables, dimensions, tables, and outriggers that exist in a data warehouse.

## SYNTAX

```
Get-SCDWEntity [-DatamartComputerName <String>] [-DatamartDatabaseName <String>] [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWEntity** cmdlet gets the list entity names and their types.
Entities include act tables, dimensions, tables, and outriggers that exist in the data warehouse.

Entity names are required for setting watermarks, and for setting and getting retention periods; by using the **Set-SCDWWatermark**, **Set-SCDWRetentionPeriod**, and **Get-SCDWRetentionPeriod** cmdlets.

## EXAMPLES

### Example 1: Display entity name and type values
```
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" | Format-Table -AutoSize | Out-Host -Paging
```

This command displays the **EntityName** values and their **EntityType**, and displays the output in pages.

### Example 2: Display entity data using stored credentials
```
PS C:\>$credUser = Get-Credential
PS C:\> Get-SCDWEntity -ComputerName "serverDW72" â€"Credential $credUser| Format-Table -AutoSize | Out-Host -Paging
```

The first command stores user credentials for the Credential parameter.

The second command displays the entity data using the specified credentials.

### Example 3: Display entity names sorted by entity type
```
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" | Sort-Object -Property EntityType, EntityName | Format-Table â€"AutoSize | Out-Host -Paging
```

This command displays the **EntityName** values sorted by their **EntityType**.

### Example 4: Display all entity names of a specific type
```
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" | Where-Object {$_.EntityType -eq "Fact"} | Sort-Object -Property EntityType, EntityName | Format-Table -AutoSize
```

This command displays the **EntityName** values whose **EntityType** value is Fact.

### Example 5: Display all entities
```
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName OMDWDatamart | Format-Table -AutoSize | Out-Host -Paging
```

This command displays the entities in the `OMDWDatamart` database.

### Example 6: Use hash tables to investigate entity data
```
PS C:\>$DWDatamart = @{}
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "DWDatamart" | ForEach-Object {$DWDatamart.Add($_.EntityName, $_.EntityType)}
PS C:\>$OMDWDatamart = @{}
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "OMDWDatamart" | ForEach-Object {$OMDWDatamart.Add($_.EntityName, $_.EntityType)}
PS C:\>$CMDWDatamart = @{}
PS C:\>Get-SCDWEntity -ComputerName "serverDW72" -DatamartComputerName "serverDW72" -DatamartDatabaseName "CMDWDatamart" | ForEach-Object {$CMDWDatamart.Add($_.EntityName, $_.EntityType)}
```

This command and the one that follows show how to use hash tables to investigate the entity data.
This example shows how to create hash tables of the entities according to their database and then how to derive hash tables from them to obtain specific data.

The first, third, and fifth command create hash tables.

The second, fourth, and sixth commands populate the hash tables with the entity names and types in the `DWDatamart`, `OMDWDatamart`, and `CMDWDatamart` databases.
The key is the entity name, and the value is the entity type.

### Example 7: Create a hash table and populate it with entity data
```
PS C:\>$DWDatamart_Outrigger = @()
PS C:\>foreach ($key in $DWDatamart.Keys) {
>>    if ($DWDatamart[$key] -eq "Outrigger") {
>>    $DWDatamart_Outrigger.Add($key,$DWDatamart[$key])
>>    }
>>}
```

This example assumes you still have the `$DWDatamart` hash table created in the previous example.

The first command creates a hash table named `$DWDatamart_Outrigger`.

The second command populates the `$DWDatamart_Outrigger` hash table with the Outrigger entities in the `DWDatamart` database.

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
Typically, this is the Structured Query Language (SQL) database server that the data warehouse uses.
If no value is provided, smshort inspects the configuration of the data warehouse and discovers the value.

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

### -DatamartDatabaseName
Specifies the name of the database of the datamart.
Typically, this is the SQL database server that the data warehouse uses.
The default value is the data warehouse repository.
Entity values can be retrieved from the **Staging** or from the **DataMart** databases.

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

### Microsoft.EnterpriseManagement.Warehouse.Cmdlets.GetSCDWEntity
A collection of Microsoft.EnterpriseManagement.Warehouse.Cmdlets.GetSCDWEntity objects.

## NOTES

## RELATED LINKS

[Set-SCDWWatermark](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWWatermark.md)

[Set-SCDWRetentionPeriod](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWRetentionPeriod.md)

[Get-SCDWRetentionPeriod](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWRetentionPeriod.md)

