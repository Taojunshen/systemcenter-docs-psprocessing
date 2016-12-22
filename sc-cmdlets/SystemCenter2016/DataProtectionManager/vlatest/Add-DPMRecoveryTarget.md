---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D325BA6D-3775-4135-9DA8-807F3525C145
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryTarget.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryTarget.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryTarget.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-DPMRecoveryTarget

## SYNOPSIS
Grants the DPM role permission to recover to a location.

## SYNTAX

```
Add-DPMRecoveryTarget [-DpmRole] <DpmRole> [-RecoveryTargets] <TargetRecoveryItem[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DPMRecoveryTarget** cmdlet grants the System Center 2016 - Data Protection Manager (DPM) role permission to recover to a location.

## EXAMPLES

### Example 1: Grant a role permission to recover to a location
```
PS C:\>$DpmRole = Get-DPMRole -Name "OpsMgrSQL"
PS C:\> $RecoveryTargetInstance = Get-DPMRecoveryTarget -DpmRole $DpmRole -Type SQLInstance
PS C:\> Add-DPMRecoveryTarget -Role $DpmRole -RecoveryTargets $RecoveryTargetInstance
```

The first command gets a DPM role named OpsMgrSQL, and then stores the result in the $DpmRole variable.

The second command gets the recovery target for the role stored in the $DpmRole variable, and then stores the result in the $RecoveryTargetInstance variable.

The third command grants the DPM role stored in $DpmRole permission to recover to the target instance of SQL Server stored in $RecoveryTargetInstance.

## PARAMETERS

### -DpmRole
Specifies a DPM role that this cmdlet modifies.
To obtain a DPM role object, use the [Get-DPMRole](./Get-DPMRole.md) cmdlet.

```yaml
Type: DpmRole
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryTargets
Specifies an array of target recovery items which consist of the instance of SQL Server and the folder to use for alternate instance recovery.

```yaml
Type: TargetRecoveryItem[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[Get-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRole.md)
