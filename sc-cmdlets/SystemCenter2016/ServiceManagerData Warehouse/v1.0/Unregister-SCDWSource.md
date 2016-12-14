---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Enable-SCDWSource.md
schema: 2.0.0
ms.assetid: 940C3AF4-E6E3-4873-82D9-8CEAAA6784D1
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Unregister-SCDWSource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Unregister-SCDWSource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Unregister-SCDWSource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Unregister-SCDWSource

## SYNOPSIS
Unregisters a data source from the data warehouse.

## SYNTAX

```
Unregister-SCDWSource [-AdditionalData <Object>] [-DataSourceTypeName] <String> [-DataSourceName] <String>
 [-ComputerName <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-SCDWSource** cmdlet unregisters a data source from the data warehouse.
Any jobs that extract data from the unregistered data source are deleted.
Any management packs that are synchronized from the unregistered data source are uninstalled.
Any data that has already been retrieved from the data warehouse for the unregistered data source remains.

## EXAMPLES

### Example 1: Unregister a data source
```
PS C:\>UnRegister-SCDWSource â€"ComputerName "serverDW72" â€"DataSourceTypeName "ServiceManager" â€"DataSourceName "Contoso_22"
```

This command unregisters a specified data source.

## PARAMETERS

### -AdditionalData
Specifies any additional data that a particular source has to send during registration.
For example, a Configuration Manager source is registered, this parameter is used to pass a credential object that is later used by the Configuration Manager source to contact the Configuration Manager server.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DataSourceName
Specifies the name of the data source to use.
Registered data sources may be retrieved by the **Get-SCDWSource** cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataSourceTypeName
Specifies the name of the type of the data source.
You can use the **Get-SCDWSourceType** cmdlet to retrieve **TypeNames**.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

[Enable-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Enable-SCDWSource.md)

[Get-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Get-SCDWSource.md)

[Set-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Set-SCDWSource.md)

[Register-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Register-SCDWSource.md)

[Disable-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/v1.0/Disable-SCDWSource.md)

