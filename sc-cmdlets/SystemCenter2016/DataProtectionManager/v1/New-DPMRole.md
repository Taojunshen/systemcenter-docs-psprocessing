---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMRole.md
schema: 2.0.0
ms.assetid: 645484F5-2C60-4111-910F-4D7AAFAD0BEF
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/New-DPMRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/New-DPMRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/New-DPMRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DPMRole

## SYNOPSIS
Creates a DPM role.

## SYNTAX

```
New-DPMRole [[-DPMServerName] <String>] [-Name] <String> [[-Description] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMRole** cmdlet creates a System Center 2016 - Data Protection Manager (DPM) role.
DPM roles let Microsoft SQL Server database owners to recover databases without assistance from a DPM administrator.

After you create a DPM role, use the Add-DPMSecurityGroup cmdlet to add the role to appropriate security groups.
Use the Add-DPMRecoveryItem cmdlet to specify instances of SQL Server and SQL Server databases that DPM protects.
Use the Add-DPMRecoveryTarget cmdlet to specify target computers that SQL Server.
After you make any changes to a DPM role, use the Set-DPMRole cmdlet to save those changes.

## EXAMPLES

### Example 1: Create a role
```
PS C:\>New-DPMRole -DPMServerName "DPMServer07" -Name "OpsMgrSQL" -Description "Operations Manager SQL"
```

This command creates a DPM role named OpsMgrSQL on the server named DPMServer07.
The command includes a description for the role.

## PARAMETERS

### -Description
Specifies a description for the DPM role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet creates a role.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the DPM role.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DPMRole](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMRole.md)

[Remove-DPMRole](xref:SystemCenter2016/DataProtectionManager/v1/Remove-DPMRole.md)

[Rename-DPMRole](xref:SystemCenter2016/DataProtectionManager/v1/Rename-DPMRole.md)

[Set-DPMRole](xref:SystemCenter2016/DataProtectionManager/v1/Set-DPMRole.md)

[Add-DPMSecurityGroup](xref:SystemCenter2016/DataProtectionManager/v1/Add-DPMSecurityGroup.md)

[Add-DPMRecoveryItem](xref:SystemCenter2016/DataProtectionManager/v1/Add-DPMRecoveryItem.md)

[Add-DPMRecoveryTarget](xref:SystemCenter2016/DataProtectionManager/v1/Add-DPMRecoveryTarget.md)

