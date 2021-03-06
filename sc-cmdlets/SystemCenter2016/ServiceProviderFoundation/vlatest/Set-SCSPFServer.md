---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D71B9CA9-0E36-4C69-A598-6D6CB5A305B8
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCSpfServer

## SYNOPSIS
Associates a server with one or more stamps.

## SYNTAX

```
Set-SCSpfServer -Server <Server> [-Stamps <Stamp[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSPFServer** cmdlet associates a server with a stamp in the Service Provider Foundation service.
You can only associate a Virtual Machine Manager (VMM) server with a stamp.

If you want to associate a stamp with a server without changing the current stamps, use the Set-SCSPFStamp cmdlet.

## EXAMPLES

### Example 1: Associate a server with a stamp
```
PS C:\>$Stamp = Get-SCSPFStamp -Name "ContosoStamp"
PS C:\> $Server = Get-SCSPFServer -Name "ContosoServer17"
PS C:\> Set-SCSPFServer -Server $Server -Stamps $Stamp
```

The first command gets a stamp.

The second command gets a server.
The third command associates the server with the stamp.

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

### -Server
Specifies a server object to associate with new stamps.
To obtain a server object, use the Get-SCSPFServer cmdlet.

```yaml
Type: Server
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stamps
Specifies one or more stamps to associate with the server.
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

[New-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFServer.md)

[Remove-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFServer.md)

[Set-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFStamp.md)

