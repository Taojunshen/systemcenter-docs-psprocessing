---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 501F4868-1F7B-4D68-A2D4-3160771807AA
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfSetting

## SYNOPSIS
Gets a setting for a database connection or for a portal endpoint.

## SYNTAX

### Empty (Default)
```
Get-SCSpfSetting [-SettingType <String>] [<CommonParameters>]
```

### FromSettingIdParameterSetName
```
Get-SCSpfSetting -ID <Guid[]> [<CommonParameters>]
```

### FromSettingNameParameterSetName
```
Get-SCSpfSetting -Name <String[]> [<CommonParameters>]
```

### FromSettingServerSettingTypeParameterSetName
```
Get-SCSpfSetting -Server <Server> [-SettingType <String>] [<CommonParameters>]
```

### FromSettingServerNameSettingTypeParameterSetName
```
Get-SCSpfSetting -ServerName <String> [-SettingType <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFSetting** cmdlet gets the setting for a database connection or for a portal endpoint connection.

## EXAMPLES

### Example 1: Get a setting
```
PS C:\>$Setting = Get-SCSPFSetting -ID f3b39608-ac58-40b7-853c-241e343b256a
```

This command gets an existing setting by its ID.

## PARAMETERS

### -ID
Specifies the GUID for the setting.

```yaml
Type: Guid[]
Parameter Sets: FromSettingIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the setting.

```yaml
Type: String[]
Parameter Sets: FromSettingNameParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies a server object associated with the setting.

```yaml
Type: Server
Parameter Sets: FromSettingServerSettingTypeParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the sever associated with the setting.

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
Parameter Sets: Empty, FromSettingServerSettingTypeParameterSetName, FromSettingServerNameSettingTypeParameterSetName
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

## OUTPUTS

## NOTES

## RELATED LINKS

[New-SCSPFSetting](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFSetting.md)

[Remove-SCSPFSetting](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFSetting.md)

