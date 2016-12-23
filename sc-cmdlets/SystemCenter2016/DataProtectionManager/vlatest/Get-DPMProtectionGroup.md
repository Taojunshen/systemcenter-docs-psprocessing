---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 39D0F0FF-982F-4D93-887D-39F69BECC0C1
updated_at: 12/23/2016 8:51 PM
ms.date: 12/23/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/66515d87034fb4944dd2b7035563d20b1b00d010/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMProtectionGroup

## SYNOPSIS
Gets the protection groups on a DPM server.

## SYNTAX

```
Get-DPMProtectionGroup [[-DPMServerName] <String>] [-Async] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMProtectionGroup** cmdlet gets the protection groups on a System Center 2016 - Data Protection Manager (DPM) server.
You cannot modify a protection group that this cmdlet gets.
To modify a protection group, run the [Get-DPMModifiableProtectionGroup](./Get-DPMModifiableProtectionGroup.md) cmdlet.

## EXAMPLES

### Example 1: Get a protection group
```
PS C:\> Get-DPMProtectionGroup -DPMServerName "DPMServer02"
```

This command gets the protection group on the DPM server named DPMServer02.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet gets protection groups.
If you do not specify a name, the cmdlet uses the current computer name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionGroup.md)

[New-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md)

[Rename-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMProtectionGroup.md)

[Update-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProtectionGroup.md)

[Get-DPMModifiableProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMModifiableProtectionGroup.md)
