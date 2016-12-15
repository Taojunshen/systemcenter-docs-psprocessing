---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9F12F2BD-E7D0-4244-A662-CC8C46A4C2C0
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMConsistencyCheckWindow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMConsistencyCheckWindow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMConsistencyCheckWindow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMConsistencyCheckWindow

## SYNOPSIS
Gets the consistency check window settings for a protection group.

## SYNTAX

```
Get-DPMConsistencyCheckWindow [-ProtectionGroup] <ProtectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMConsistencyCheckWindow** cmdlet gets the consistency check window settings for a System Center 2016 - Data Protection Manager (DPM) protection group.
For more information about consistency check windows, see the Set-DPMConsistencyCheckWindow cmdlet.

## EXAMPLES

### Example 1: Get consistency check window settings
```
PS C:\>$PGroup = Get-DPMProtectionGroup | Where {$_.FriendlyName -like "*ContosoPG*"}
PS C:\> Get-DPMConsistencyCheckWindow -ProtectioGroup $PGroup
```

The first command gets protection groups.
This command passes the results to the **Where-Object** cmdlet.
That cmdlet drops all except ones that match the specified friendly name.
For more information, type `Get-Help Where-Object`.
The command stores the protection group in the $PGroup variable.

The second command gets settings for the consistency check window of the protection group in $PGroup.

## PARAMETERS

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets settings.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

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

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Set-DPMConsistencyCheckWindow](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMConsistencyCheckWindow.md)

