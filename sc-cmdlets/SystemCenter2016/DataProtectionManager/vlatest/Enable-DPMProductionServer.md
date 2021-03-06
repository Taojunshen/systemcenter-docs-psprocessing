---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0DC8F1ED-97F6-438B-8337-84E4590714D3
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMProductionServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMProductionServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMProductionServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Enable-DPMProductionServer

## SYNOPSIS
Enables a DPM protection agent.

## SYNTAX

```
Enable-DPMProductionServer [-ProductionServer] <ProductionServer> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-DPMProductionServer** cmdlet enables a System Center 2016 - Data Protection Manager (DPM) protection agent on a computer.
After you enable a protection agent, DPM enables backup jobs that you schedule for the computer to run.

## EXAMPLES

### Example 1: Enable a protection agent
```
PS C:\>$DpmPServer = Get-DPMProductionServer -DPMServerName "DpmTsqa01" | Where {$_.Name -eq "dist01.contoso.com"}
PS C:\> Enable-DPMProductionServer -ProductionServer $DpmPServer
```

The first command gets the DPM protection agent on the computer named dist01.contoso.com for the DPM server named DpmTsqa01.
The command stores the result in the $DpmPServer variable.

The second command enables the protection agent stored in $DpmPServer.

## PARAMETERS

### -ProductionServer
Specifies a computer on which a DPM protection agent is installed.
This cmdlet enables the protection agent.

```yaml
Type: ProductionServer
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

### ProductionServer

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Disable-DPMProductionServer.md)

[Get-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionServer.md)

[Update-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProductionServer.md)
