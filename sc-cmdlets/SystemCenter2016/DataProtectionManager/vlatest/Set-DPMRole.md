---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMRole.md
schema: 2.0.0
ms.assetid: DCD43071-5D8D-4495-A8A2-E7E57198ECAA
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMRole

## SYNOPSIS
Saves changes to a DPM role.

## SYNTAX

```
Set-DPMRole [-DpmRole] <DpmRole> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMRole** cmdlet saves changes you make to a System Center 2016 - Data Protection Manager (DPM) role.
DPM roles let Microsoft SQL Server database owners to recover databases without assistance from a DPM administrator.

You can change the name or description of a DPM by using the Rename-DPMRole cmdlet.
Use the Add-DPMSecurityGroup cmdlet to add the role to appropriate security groups.
Use the Add-DPMRecoveryItem cmdlet to specify instances of SQL Server and SQL Server databases that DPM protects.
Use the Add-DPMRecoveryTarget cmdlet to specify target computers that run SQL Server.

## EXAMPLES

### Example 1: Save a change to a role
```
PS C:\>$DpmRole = Get-DpmRole -Name "OpsMgrSQL" -Editable
PS C:\> Rename-DPMRole -DpmRole $DpmRole -Name "OpsMgrSQL23" 
PS C:\> Set-DPMRole -DPMRole $DpmRole
```

The first command gets the role by using the **Get-DpmRole** cmdlet, and then stores it in the $DpmRole variable.
The command makes the role editable.

The second command renames the role stored in $DpmRole by using the **Rename-DPMRole** cmdlet.

The third command saves the change made in the second command for the role stored in $DpmRole.

## PARAMETERS

### -DpmRole
Specifies a DPM role that this cmdlet modifies.
To obtain a DPM role object, use the Get-DPMRole cmdlet.

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

[New-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMRole.md)

[Remove-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRole.md)

[Rename-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMRole.md)

[Add-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMSecurityGroup.md)

[Add-DPMRecoveryItem](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryItem.md)

[Add-DPMRecoveryTarget](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMRecoveryTarget.md)

