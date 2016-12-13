---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMSecurityGroup.md
schema: 2.0.0
ms.assetid: 162012EA-B755-4395-9203-6D56D53EE7E7
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMSecurityGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMSecurityGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMSecurityGroup.md
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

[Add-DPMSecurityGroup](xref:DataProtectionManager/v1/Add-DPMSecurityGroup.md)

[Remove-DPMSecurityGroup](xref:DataProtectionManager/v1/Remove-DPMSecurityGroup.md)

[Get-DPMRole](xref:DataProtectionManager/v1/Get-DPMRole.md)

