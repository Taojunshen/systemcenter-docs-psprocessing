---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMSecurityGroup.md
schema: 2.0.0
ms.assetid: 0D5CD01F-43BA-4CE8-86B0-F52F610D27CF
updated_at: 12/20/2016 10:56 PM
ms.date: 12/20/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMSecurityGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMSecurityGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/39ebc8b68768998222371964f8e90b8160cbfe0a/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Add-DPMSecurityGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-DPMSecurityGroup

## SYNOPSIS
Adds security groups to a DPM role.

## SYNTAX

```
Add-DPMSecurityGroup [-DpmRole] <DpmRole> [-SecurityGroups] <String[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-DPMSecurityGroup** cmdlet adds one or more security groups to a System Center 2016 - Data Protection Manager (DPM) role.
You can use the [Get-DPMRole](./Get-DPMRole.md) to specify a DPM role.
Use the [Set-DPMRole](./Set-DPMRole.md) cmdlet to save your changes.

You can see the security groups for a DPM role by using the [Get-DPMSecurityGroup](./Get-DPMSecurityGroup.md) cmdlet.
You can use the [Remove-DPMSecurityGroup](./Remove-DPMSecurityGroup.md) cmdlet to remove security groups from a DPM role.

## EXAMPLES

### Example 1: Add a security group to a role
```
PS C:\>$DpmRole = Get-DPMRole -Name "OpsMgrSQL" -Editable
PS C:\> Add-DPMSecurityGroup -DpmRole $DpmRole -SecurityGroups "Hq\OpsMgrSQL"
```

The first command uses the **Get-DPMRole** cmdlet to get the role named OpsMgrSQL and then stores it in the $DpmRole variable.
The command makes the role editable.

The second command adds the specified security group to the role stored in the $DpmRole variable.

## PARAMETERS

### -DpmRole
Specifies a DPM role to which this cmdlet adds a security group.
To obtain a DPM role object, use the **Get-DPMRole** cmdlet.

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

### -SecurityGroups
Specifies an array of security groups.
The cmdlet adds these groups to the DPM role.

```yaml
Type: String[]
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

[Get-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMSecurityGroup.md)

[Remove-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMSecurityGroup.md)

[Get-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRole.md)

[Set-DPMRole](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMRole.md)
