---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMSecurityGroup.md
schema: 2.0.0
ms.assetid: E8286F4A-968A-4849-8397-49F83083068D
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Remove-DPMSecurityGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Remove-DPMSecurityGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Remove-DPMSecurityGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-DPMSecurityGroup

## SYNOPSIS
Removes security groups from a DPM role.

## SYNTAX

```
Remove-DPMSecurityGroup [-DpmRole] <DpmRole> [[-SecurityGroups] <String[]>] [-All] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMSecurityGroup** cmdlet removes one or more security groups from a System Center 2016 - Data Protection Manager (DPM) role.
You can use the Get-DPMRole to specify a DPM role.
Use the Set-DPMRole cmdlet to save your changes.

You can see the security groups for a DPM role by using the Get-DPMSecurityGroup cmdlet.
You can use the Add-DPMSecurityGroup cmdlet to add security groups to a DPM role.

## EXAMPLES

### Example 1: Remove a security group from a role
```
PS C:\>$DpmRole = Get-DPMRole -Name "OpsMgrSQL" -Editable
PS C:\> Remove-DPMSecurityGroup -DpmRole $DpmRole -SecurityGroups "DpmDom02\Administrator"
```

The first command uses the **Get-DPMRole** cmdlet to get the role named OpsMgrSQL, and then stores it in the $DpmRole variable.
The command makes the role editable.

The second command removes the security group DpmDom02\Administrator from the role in $DpmRole.

## PARAMETERS

### -All
Indicates that the action affects all objects that the cmdlet refers to.

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

### -DpmRole
Specifies a DPM role from which this cmdlet removes security groups.
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
The cmdlet removes these groups from the DPM role.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
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

[Add-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/v1.0/Add-DPMSecurityGroup.md)

[Get-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMSecurityGroup.md)

[Get-DPMRole](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMRole.md)

[Set-DPMRole](xref:SystemCenter2016/DataProtectionManager/v1.0/Set-DPMRole.md)

