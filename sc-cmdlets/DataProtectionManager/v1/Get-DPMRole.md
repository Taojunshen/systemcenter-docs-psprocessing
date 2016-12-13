---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./New-DPMRole.md
schema: 2.0.0
ms.assetid: 66DEE29D-46EB-4856-B811-65B37BE74181
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMRole

## SYNOPSIS
Gets a DPM role to view or edit.

## SYNTAX

```
Get-DPMRole [[-DPMServerName] <String>] [[-Name] <String>] [-Editable] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMRole** cmdlet gets a System Center 2016 - Data Protection Manager (DPM) role for you to view or edit.
You can use this cmdlet to display the properties of a DPM role, or all the DPM roles for a DPM server.
DPM roles let Microsoft SQL Server database owners to recover databases without assistance from a DPM administrator.

To open a role for editing, use the *Editable* parameter.
After you make changes to a DPM role, use the Set-DPMRole cmdlet to save those changes.

## EXAMPLES

### Example 1: Get a role
```
PS C:\>Get-DpmRole -Name "OpsMgrSQL"
```

This command gets a DPM role named OpsMgrSQL.
If you intend to make changes to the role, specify the *Editable* parameter.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet acts.

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

### -Editable
Indicates that you can edit the DPM role.

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

### -Name
Specify the name of a protection group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

[New-DPMRole](xref:DataProtectionManager/v1/New-DPMRole.md)

[Remove-DPMRole](xref:DataProtectionManager/v1/Remove-DPMRole.md)

[Rename-DPMRole](xref:DataProtectionManager/v1/Rename-DPMRole.md)

[Set-DPMRole](xref:DataProtectionManager/v1/Set-DPMRole.md)

