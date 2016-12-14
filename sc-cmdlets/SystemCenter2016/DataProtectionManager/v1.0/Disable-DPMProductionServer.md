---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProductionServer.md
schema: 2.0.0
ms.assetid: 05D17F23-4E0F-43E2-964E-66B255B14CA0
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Disable-DPMProductionServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Disable-DPMProductionServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Disable-DPMProductionServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-DPMProductionServer

## SYNOPSIS
Disables a DPM protection agent.

## SYNTAX

```
Disable-DPMProductionServer [-ProductionServer] <ProductionServer> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-DPMProductionServer** cmdlet disables the System Center 2016 - Data Protection Manager (DPM) protection agent on a computer.
After you disable a DPM protection agent, backup jobs for the computer do not run.

## EXAMPLES

### Example 1: Disable a protection agent
```
PS C:\>$DpmServer = Get-DPMProductionServer -DPMServerName "DpmWest01" | Where {$_.Name -eq "dist01.contoso.com"}
PS C:\> Disable-DPMProductionServer -ProductionServer $DpmServer
```

The first command gets the DPM protection agent on the computer named dist01.contoso.com for the DPM server named DpmWest01.
The command stores the result in the $DpmServer variable.

The second command disables the protection agent stored in $DpmServer.

## PARAMETERS

### -ProductionServer
Specifies a computer on which a DPM protection agent is installed.
This cmdlet disables the protection agent.

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

[Get-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProductionServer.md)

[Enable-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/v1.0/Enable-DPMProductionServer.md)

[Update-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/v1.0/Update-DPMProductionServer.md)

