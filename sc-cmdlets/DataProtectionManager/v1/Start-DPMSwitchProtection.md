---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: D8229B5B-2FA1-44AF-AF26-83515B979289
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMSwitchProtection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMSwitchProtection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMSwitchProtection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMSwitchProtection

## SYNOPSIS
Switches protection of data sources to a secondary DPM server.

## SYNTAX

```
Start-DPMSwitchProtection [-ProtectionGroup] <ProtectionGroup> [-Async] -Datasource <Datasource[]> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMSwitchProtection** cmdlet switches protection of a set of data sources to a secondary System Center 2016 - Data Protection Manager (DPM) server.
Run this cmdlet on the secondary DPM server.

## EXAMPLES

### Example 1: Switch protection for a data source to the secondary server
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName DPMServer073
PS C:\> $PObject = Get-DPMDatasource $PGroup[0]
PS C:\> Start-DPMSwitchProtection -ProtectionGroup $PGroup -Datasource $PObject
```

The first command gets the data protection group for a server by using the **Get-DPMProtectionGroup** cmdlet, and then stores it in the $PGroup variable.

The second command uses the **Get-DPMDatasource** cmdlet to obtain a data source.
The command uses standard array syntax to specify the first member of the $PGroup array.
The command stores the data source in the $PObject variable.

The third command switches protection to the secondary server for the data source in $Ds variable that is part of the protection group stored in $PGroup variable.
Run this example on the secondary server.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

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

### -Datasource
Specifies a data source object for which this cmdlet switches protection.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group on which this cmdlet operates.
To obtain a protection group object, use the Get-DPMProtectionGroup cmdlet.

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

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:DataProtectionManager/v1/Get-DPMDatasource.md)

