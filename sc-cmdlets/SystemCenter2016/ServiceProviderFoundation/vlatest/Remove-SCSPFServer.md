---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1397071E-B3A4-4A81-988C-AACF7999F996
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSpfServer

## SYNOPSIS
Removes one or more server objects.

## SYNTAX

### Empty (Default)
```
Remove-SCSpfServer [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromServerParameterSetName
```
Remove-SCSpfServer -Server <Server[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSPFServer** cmdlet removes one or more Virtual Machine Manager (VMM) servers from the Service Provider Foundation database.

## EXAMPLES

### Example 1: Remove a server
```
PS C:\>$Server = Get-SCSPFServer -Name "ContosoServer23"
PS C:\> Remove-SCSPFServer -Server $Server
```

The first command gets the server object named ContosoServer23, and stores it in the $Server variable.

The second command removes the server.

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
Specifies the name of one or more VMM server objects.
To obtain a server object, use the Get-SCSPFServer cmdlet.

```yaml
Type: Server[]
Parameter Sets: FromServerParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[New-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFServer.md)

[Set-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFServer.md)

