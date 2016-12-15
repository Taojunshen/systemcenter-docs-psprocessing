---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Dismount-DPMRecoveryPoint.md
schema: 2.0.0
ms.assetid: AA3227F9-9386-4DE4-A710-2F42450CA90A
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMRecoveryPoint

## SYNOPSIS
Gets recovery points for a data source.

## SYNTAX

### Datasource
```
Get-DPMRecoveryPoint [-Datasource] <Datasource> [-Async] [-Online] [-OnlyActive] [<CommonParameters>]
```

### Tape
```
Get-DPMRecoveryPoint [-Tape] <Media> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMRecoveryPoint** cmdlet gets all available recovery points for a data source.

## EXAMPLES

### Example 1: Get a recovery point
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> Get-DPMRecoveryPoint -Datasource $PObjects
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the results in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group stored in $PGroup.
The command stores the results in the $PObjects variable.

The third command gets the recovery point for the data source stored in $PObjects.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

```yaml
Type: SwitchParameter
Parameter Sets: Datasource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies a data source object for which this cmdlet gets recovery points.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, System Center 2016 - Data Protection Manager (DPM) database, or system state that is a member of a protection group.

```yaml
Type: Datasource
Parameter Sets: Datasource
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Online
Specifies that DPM enables online protection.

```yaml
Type: SwitchParameter
Parameter Sets: Datasource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnlyActive
Indicates that this cmdlet returns only recovery points that have not expired.

```yaml
Type: SwitchParameter
Parameter Sets: Datasource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tape
Specifies a tape from which this cmdlet gets recovery points.
To obtain a **Tape** object, use the Get-DPMTape cmdlet.

```yaml
Type: Media
Parameter Sets: Tape
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### RecoveryPoint

## NOTES

## RELATED LINKS

[Dismount-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Dismount-DPMRecoveryPoint.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Mount-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Mount-DPMRecoveryPoint.md)

[New-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryPoint.md)

[Remove-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMRecoveryPoint.md)

[Get-DPMRecoveryPointLocation](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPointLocation.md)

