---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Update-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 922D0C3D-6CD3-41CE-A0CE-390FB1DE18F4
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMProtectionGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMProtectionGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMProtectionGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Rename-DPMProtectionGroup

## SYNOPSIS
Renames a protection group.

## SYNTAX

```
Rename-DPMProtectionGroup [-ProtectionGroup] <ProtectionGroup> [-NewName] <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Rename-DPMProtectionGroup** cmdlet renames a protection group on the System Center 2016 - Data Protection Manager (DPM) server.
The process of renaming a protection group requires the following steps:

- 1.
Retrieve the protection group by using the Get-DPMProtectionGroup cmdlet.
- 2.
Make the protection group modifiable by using the Get-DPMModifiableProtectionGroup cmdlet.
- 3.
Rename the protection group by using the Rename-DPMProtectionGroup cmdlet.
- 4.
Save the changes by using the Set-DPMProtectionGroup cmdlet.

## EXAMPLES

### Example 1: Rename a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup 
PS C:\> Rename-DPMProtectionGroup -ProtectionGroup $MPGroup -NewName "ProtectGroup02"
PS C:\> Set-DPMProtectionGroup -ProtectionGroup $MPGroup
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores it in the $PGroup variable.

The second command gets the protection group in a modifiable mode, and then stores the results in the $MPGroup variable.

The third command renames the protection group in $MPGroup to ProtectGroup02.

The fourth command saves all the actions on the DPM server that you performed on the protection group in $MPGroup.

## PARAMETERS

### -NewName
Specifies a new name for the protection group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ProtectionGroup
Specifies a protection group that this cmdlet renames.
To obtain a **ProtectionGroup** object, use the **Get-DPMProtectionGroup** cmdlet.

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

### ProtectionGroup

## NOTES

## RELATED LINKS

[Update-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProtectionGroup.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Set-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionGroup.md)

[New-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md)

