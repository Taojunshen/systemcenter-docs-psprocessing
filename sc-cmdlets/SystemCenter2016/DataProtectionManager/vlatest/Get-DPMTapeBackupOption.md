---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D74221D0-D62A-4635-8991-C46F0DF7ECE7
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTapeBackupOption.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTapeBackupOption.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTapeBackupOption.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMTapeBackupOption

## SYNOPSIS
Retrieves library, drive, and other backup or archive options for a protection group.

## SYNTAX

```
Get-DPMTapeBackupOption [-ProtectionGroup] <ProtectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMTapeBackupOption** cmdlet retrieves library, drive, and other backup or archive options for a System Center 2016 - Data Protection Manager (DPM) protection group.

## EXAMPLES

### Example 1: Retrieve tape backup options
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "Contoso-DPMServer"
PS C:\> Get-DPMTapeBackupOption -ProtectionGroup $PGroup
```

The first command uses the **Get-DPMProtectionGroup** cmdlet to get the protection group for the server named Contoso-DPMServer.
The command stores the group in the $PGroup variable.

The second command gets the settings for the group in $PGroup.

## PARAMETERS

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets options.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.
A protection group consists of data sources, such as volumes or shares, that have a common protection configuration and schedule.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ProtectionGroup

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Set-DPMTapeBackupOption](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMTapeBackupOption.md)

