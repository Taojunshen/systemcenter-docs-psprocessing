---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C5C333BD-70C3-452A-8226-70E87C9D7BBF
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMBackupNetworkAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMBackupNetworkAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMBackupNetworkAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-DPMBackupNetworkAddress

## SYNOPSIS
Removes a backup network from a DPM server.

## SYNTAX

```
Remove-DPMBackupNetworkAddress [[-DPMServerName] <String>] [-Address] <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMBackupNetworkAddress** cmdlet removes a backup network from a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Remove a backup network
```
PS C:\>Remove-DPMBackupNetworkAddress -DpmServername "DPMServer07" -Address "10.10.10.1/16"
```

This command removes the network address 10.10.10.1/16 as a backup network address for the DPM server named DPMServer07.

## PARAMETERS

### -Address
Specifies the IP address or subnet mask of a backup network that this cmdlet removes from the server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of the DPM server that this cmdlet removes.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-DPMBackupNetworkAddress](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMBackupNetworkAddress.md)

[Get-DPMBackupNetworkAddress](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMBackupNetworkAddress.md)

