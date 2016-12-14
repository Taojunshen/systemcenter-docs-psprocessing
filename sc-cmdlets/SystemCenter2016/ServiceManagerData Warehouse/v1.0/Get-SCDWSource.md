---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Enable-SCDWSource.md
schema: 2.0.0
ms.assetid: C3D27615-06B3-478F-B180-A4866832D7E6
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Get-SCDWSource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Get-SCDWSource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Get-SCDWSource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDWSource

## SYNOPSIS
Gets registered instances of data sources.

## SYNTAX

```
Get-SCDWSource [[-DataSourceTypeName] <String>] [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWSource** cmdlet gets specific instances of data sources that are registered to the data warehouse.

For updated information about this cmdlet, see Get-SCDWSourcehttp://go.microsoft.com/fwlink/p/?LinkId=234994.

## EXAMPLES

### Example 1: Get all data sources
```
PS C:\>Get-SCDWSource -ComputerName "serverDW72"
```

This command retrieves all data sources from the `serverDW72` computer.

### Example 2: Get all data sources of a particular type
```
PS C:\>Get-SCDWSource -DataSourceTypeName "ServiceManager" -ComputerName "serverDW72"
```

This command retrieves all data sources from the `serverDW72` computer, for which the data source type is `ServiceManager`.

### Example 3: Get data sources by date
```
PS C:\>Get-SCDWSource -ComputerName "serverDW72" | Where-Object {$_.DateRegistered -lt [System.DateTime]"June 12 2012"}
```

This command finds any data sources that were registered before a specified date.

### Example 4: Get unregistered data sources
```
PS C:\>Get-SCDWSource -ComputerName "serverDW72" | Where-Object {$_.DateUnRegistered -ne $Null}
```

This command finds any data sources that have been unregistered.

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

### -DataSourceTypeName
Specifies the type of the data source.
You can use the **Get-SCDWSourceType** cmdlet to retrieve **TypeNames**.

```yaml
Type: String
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.DataWarehouse.DataSource

## NOTES

## RELATED LINKS

[Enable-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Enable-SCDWSource.md)

[Disable-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Disable-SCDWSource.md)

[Set-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Set-SCDWSource.md)

[Register-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Register-SCDWSource.md)

[Unregister-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Unregister-SCDWSource.md)

