---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FBED9FF4-71EF-44C0-B647-BC24B4D3B644
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProtectionGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProtectionGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProtectionGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-DPMProtectionGroup

## SYNOPSIS
Updates a protection group configuration.

## SYNTAX

```
Update-DPMProtectionGroup [-ProtectionGroup] <ProtectionGroup> [[-Datasource] <Datasource[]>] [-Inquire]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-DPMProtectionGroup** cmdlet updates the protection group configuration to capture changes to protected data sources in System Center 2016 - Data Protection Manager (DPM).
This cmdlet modifies the protection group without changing any settings to reflect changes to protected data sources.

## EXAMPLES

### Example 1: Update a production group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObject = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> Update-DPMProtectionGroup -ProtectionGroup $PGroup -Datasource $PObject[0] -Inquire
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the results in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group in $PGroup.
The command stores the results in the $PObjects variable.

The third command updates the protection group in $PGroup with a data source in $PObjects.

## PARAMETERS

### -Datasource
Specifies a data source object for which this cmdlet updates configuration.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Inquire
Indicates that this cmdlet performs a fresh inquiry, DPM queries the protected computer and returns the data sources or child data sources on it.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group that this cmdlet updates.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

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

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Set-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionGroup.md)

[New-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md)

[Rename-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMProtectionGroup.md)

