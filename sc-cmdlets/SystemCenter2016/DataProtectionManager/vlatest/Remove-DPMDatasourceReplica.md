---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 78B7C0CD-084C-4EFC-8FF0-60BF9CE32B8F
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMDatasourceReplica.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMDatasourceReplica.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMDatasourceReplica.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-DPMDatasourceReplica

## SYNOPSIS
Removes an inactive replica.

## SYNTAX

### Disk (Default)
```
Remove-DPMDatasourceReplica [-Datasource] <Datasource> [-Disk] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Tape
```
Remove-DPMDatasourceReplica [-Datasource] <Datasource> [-Tape] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Online
```
Remove-DPMDatasourceReplica [-Datasource] <Datasource> [-Online] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMDatasourceReplica** cmdlet removes an inactive replica from disk or tape.

## EXAMPLES

### Example 1: Remove a data source replica
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> Remove-DPMDatasourceReplica -Datasource $PObjects -Disk
```

The first command gets the protection group from the DPM server named DPMServer02, and then stores that group in the $PGroup variable.

The second command gets the data source from the protection group in $PGroup, and then stores that data source in the $PObject variable.

The last command removes the replica of the data source in $PObjects from disk.

## PARAMETERS

### -Datasource
Specifies a data source object for which this cmdlet removes a replica.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, System Center 2016 - Data Protection Manager (DPM) database, or system state that is a member of a protection group.

```yaml
Type: Datasource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Disk
Indicates that the cmdlet removes the replica from disk.

```yaml
Type: SwitchParameter
Parameter Sets: Disk
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Online
Indicates that the data source uses online protection.

```yaml
Type: SwitchParameter
Parameter Sets: Online
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Tape
Indicates that the cmdlet removes the replica from tape.

```yaml
Type: SwitchParameter
Parameter Sets: Tape
Aliases: 

Required: True
Position: Named
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

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

