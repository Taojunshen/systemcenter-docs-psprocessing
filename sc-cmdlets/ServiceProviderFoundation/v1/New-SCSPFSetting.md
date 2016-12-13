---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=328338
schema: 2.0.0
ms.assetid: D71BEB70-FD06-49A4-8B19-5662885A6308
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/New-SCSPFSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceProviderFoundation/v1/New-SCSPFSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceProviderFoundation/v1/New-SCSPFSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSpfSetting

## SYNOPSIS
Creates a new setting for a database connection or a portal endpoint.

## SYNTAX

### FromSettingServerSettingTypeParameterSetName (Default)
```
New-SCSpfSetting [-Name <String>] -Value <String> -SettingType <String> -Server <Server> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FromSettingServerNameSettingTypeParameterSetName
```
New-SCSpfSetting [-Name <String>] -Value <String> -SettingType <String> -ServerName <String> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSPFSetting** cmdlet creates a new setting for a database connection string or a portal endpoint connection string.

## EXAMPLES

### Example 1: Create a new setting for a database connection
```
PS C:\>$Setting = New-SCSPFSetting -Name "ContosoSetting" -SettingType "DatabaseConnectionString" -SettingString "Server=ContosoServer\\ContosoInstance;Database=OperationsManagerDW;TrustedConnection=True;Connection Timeout=300" -Server $ContosoServer
```

This command creates a new setting for a database connection.
The setting is associated with the server stored in the $ContosoServer variable, which was previously obtained by using the Get-SCSPFServer cmdlet.

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

### -Name
Specifies a friendly name for the setting.

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

### -Server
Specifies the server associated with the setting.

```yaml
Type: Server
Parameter Sets: FromSettingServerSettingTypeParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the server the setting is associated with.
The actual association is made by the *Server* parameter with a server object.

```yaml
Type: String
Parameter Sets: FromSettingServerNameSettingTypeParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingType
Specifies either DatabaseConnectionString or EndPointConnectionString.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Specifies the value for the setting.

```yaml
Type: String
Parameter Sets: (All)
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

[Get-SCSPFSetting](xref:ServiceProviderFoundation/v1/Get-SCSPFSetting.md)

[Remove-SCSPFSetting](xref:ServiceProviderFoundation/v1/Remove-SCSPFSetting.md)

