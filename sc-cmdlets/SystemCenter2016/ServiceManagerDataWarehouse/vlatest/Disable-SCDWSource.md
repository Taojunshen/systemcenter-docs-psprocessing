---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Enable-SCDWSource.md
schema: 2.0.0
ms.assetid: 112389DD-DE52-4A21-8B5D-439DD2AED3E2
updated_at: 12/15/2016 6:30 PM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWSource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWSource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/59ca46449cbaf6c065d4887fdd68c8de98ef34f0/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWSource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCDWSource

## SYNOPSIS
Disables all jobs that are affiliated with the specified data source.

## SYNTAX

```
Disable-SCDWSource [-DataSourceTypeName] <String> [-DataSourceName] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCDWSource** cmdlet disables all jobs that are affiliated with the specified data source.

## EXAMPLES

### Example 1: Disable a datasource and associated jobs
```
PS C:\>Disable-SCDWSource â€"ComputerName "serverDW72" -DataSourceTypeName ServiceManager -DataSourceName "SM12"
```

This command disables the `SM12` data source and all the jobs that use it.

### Example 2: Disable a datasource using credentials
```
PS C:\>$credUser = Get-Credential
PS C:>Disable-SCDWSource â€"ComputerName "serverDW72" -DataSourceTypeName "ServiceManager" -DataSourceName "SM12" â€"Credential $credUser
```

The first command stores user credentials for the *Credential* parameter.

The second command disables the data source using the specified credentials.

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

[Enable-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWSource.md)

[Get-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWSource.md)

[Set-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWSource.md)

[Register-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Register-SCDWSource.md)

[Unregister-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Unregister-SCDWSource.md)

