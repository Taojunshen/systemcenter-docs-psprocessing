---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A3467FE7-F0E7-41FD-9453-0B01C43F122D
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWSource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWSource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWSource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Enable-SCDWSource

## SYNOPSIS
Enables all jobs that are associated with the specified data source.

## SYNTAX

```
Enable-SCDWSource [-DataSourceTypeName] <String> [-DataSourceName] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCDWSource** cmdlet enables all jobs that are associated with the specified data source.

## EXAMPLES

### Example 1: Enable a datasource using stored credentials
```
PS C:\>$userCred = Get-Credential
PS C:\> Enable-SCDWSource â€"ComputerName "serverDW72" -DataSourceTypeName "ServiceManager" -DataSourceName "SM12" â€"Credential $userCred
```

This first command stores user credentials in the `$userCred` variable for the *Credential* parameter.

The second command enables the `SM12` data source, using the stored credentials.

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

### -DataSourceName
Specifies the name of the data source to disable.
You can use the **Get-SCDWSource** cmdlet to retrieve registered data sources.

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
Specifies the type of the data source.
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

[Disable-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWSource.md)

[Get-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWSource.md)

[Set-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWSource.md)

[Register-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Register-SCDWSource.md)

[Unregister-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Unregister-SCDWSource.md)

