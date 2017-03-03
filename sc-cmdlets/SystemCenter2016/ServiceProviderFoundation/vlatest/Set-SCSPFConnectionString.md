---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 946AAEA9-E6A4-4C1C-A38A-88179E5A3B1C
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFConnectionString.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFConnectionString.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFConnectionString.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCSpfConnectionString

## SYNOPSIS
Sets the connection string to the database used by the Service Provider Foundation service.

## SYNTAX

### Empty (Default)
```
Set-SCSpfConnectionString [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromConnectionStringConnectionStringParameterSetName
```
Set-SCSpfConnectionString -ConnectionString <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSPFConnectionString** cmdlet sets the database connection string to the database used by the Service Provider Foundation service.
The database used by the Service Provider Foundation and the Service Provider Foundation service do not have to be on the same server.

This cmdlet requires running Windows PowerShell as an administrator.

## EXAMPLES

### Example 1: Set the connection string
```
PS C:\>Set-SCSPFConnectionString -ConnectionString "Data Source=ContosoServerSFPDB_72,1433;Database=SCSPFDB;Integrated Security=True;MultipleActiveResultSets=True;"
```

This command sets the connection string to the database used by the Service Provider Foundation service on a server with the name ContosoServerSFPDB_72.

## PARAMETERS

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

### -ConnectionString
Specifies the connection string to the database used by the Service Provider Foundation service.

```yaml
Type: String
Parameter Sets: FromConnectionStringConnectionStringParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCSPFConnectionString](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFConnectionString.md)

