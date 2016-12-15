---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=330330
schema: 2.0.0
ms.assetid: 70442882-EC21-438B-98F7-128A6AFA447E
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSpfServer

## SYNOPSIS
Adds a server to the Service Provider Foundation database.

## SYNTAX

```
New-SCSpfServer -Name <String> [-SpfSettings <SpfSetting[]>] -ServerType <String> [-Stamps <Stamp[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSPFServer** cmdlet adds a server to the Service Provider Foundation database.

## EXAMPLES

### Example 1: Add a server
```
PS C:\>$Stamp = Get-SCSPFStamp -Name "ContosoStampName01"
PS C:\> New-SCSPFServer -Name "ContosoServer23" -ServerType "0" -Stamps $Stamp
```

The first command gets a stamp.

The second command creates a server with a specified name and VMM server type, and associates the server with a stamp.

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
Specifies the fully qualified domain name (FQDN) of the Virtual Machine Manager (VMM) server.

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

### -ServerType
Specifies the type of server.

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

### -SpfSettings
Specifies an array of Service Provider Foundation settings.

```yaml
Type: SpfSetting[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stamps
Specifies the name of one or more stamp objects to associate with the new server.
To obtain a stamp, use the Get-SCSPFStamp cmdlet.

```yaml
Type: Stamp[]
Parameter Sets: (All)
Aliases: 

Required: False
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

[Get-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFServer.md)

[Get-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFStamp.md)

[Remove-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFServer.md)

[Set-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFServer.md)

