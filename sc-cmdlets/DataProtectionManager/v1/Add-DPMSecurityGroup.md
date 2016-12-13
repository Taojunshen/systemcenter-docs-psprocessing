---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMSecurityGroup.md
schema: 2.0.0
ms.assetid: 0D5CD01F-43BA-4CE8-86B0-F52F610D27CF
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Add-DPMSecurityGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Add-DPMSecurityGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Add-DPMSecurityGroup.md
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
You can use the Get-DPMRoleto specify a DPM role.
Use the Set-DPMRole cmdlet to save your changes.

You can see the security groups for a DPM role by using the Get-DPMSecurityGroup cmdlet.
You can use the Remove-DPMSecurityGroup cmdlet to remove security groups from a DPM role.

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

[Get-DPMSecurityGroup](xref:DataProtectionManager/v1/Get-DPMSecurityGroup.md)

[Remove-DPMSecurityGroup](xref:DataProtectionManager/v1/Remove-DPMSecurityGroup.md)

[Get-DPMRole](xref:DataProtectionManager/v1/Get-DPMRole.md)

[Set-DPMRole](xref:DataProtectionManager/v1/Set-DPMRole.md)

