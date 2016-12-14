---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMSecurityGroup.md
schema: 2.0.0
ms.assetid: 162012EA-B755-4395-9203-6D56D53EE7E7
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMSecurityGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMSecurityGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Get-DPMSecurityGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMSecurityGroup

## SYNOPSIS
Gets the security groups for a DPM role.

## SYNTAX

```
Get-DPMSecurityGroup [-DpmRole] <DpmRole> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMSecurityGroup** cmdlet gets the security groups for a System Center 2016 - Data Protection Manager (DPM) role.

## EXAMPLES

### Example 1: Get security groups for a role
```
PS C:\>$DpmRole = Get-DpmRole -Name "OpsMgrSQL"
PS C:\> Get-DPMSecurityGroup -DPMRole $DpmRole
```

The first command uses the **Get-DPMRole** cmdlet to get the role named OpsMgrSQL, and then stores it in the $DpmRole variable.

The second command gets the security groups for the role in $DpmRole.

## PARAMETERS

### -DpmRole
Specifies a DPM role from which this cmdlet gets security groups.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/v1/Add-DPMSecurityGroup.md)

[Remove-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/v1/Remove-DPMSecurityGroup.md)

[Get-DPMRole](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMRole.md)

