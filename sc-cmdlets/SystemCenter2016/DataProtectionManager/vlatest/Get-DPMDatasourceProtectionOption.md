---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMDatasourceProtectionOption.md
schema: 2.0.0
ms.assetid: 1D87C419-D4DB-4149-90C5-6DBF69F97458
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasourceProtectionOption.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasourceProtectionOption.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasourceProtectionOption.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMDatasourceProtectionOption

## SYNOPSIS
Returns protection options in a protection group.

## SYNTAX

### ExchangeOptions
```
Get-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup> [-ExchangeOptions] [<CommonParameters>]
```

### E14Options
```
Get-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup> [-E14Options] [<CommonParameters>]
```

### FileSystem
```
Get-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup> [-FileSystem] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMDatasourceProtectionOption** cmdlet returns protection options for data sources in a System Center 2016 - Data Protection Manager (DPM) protection group.
Specify the type of data source in the protection group for which the cmdlet returns the protection options.

## EXAMPLES

### Example 1: Get protection options from a server
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Get-DPMDatasourceProtectionOption -ProtectionGroup $PGroup[0] -FileSystem
```

The first command gets the protection groups from the server named DPMServer02, and then stores those groups in the $PGroup variable.

The second command gets the protection options for a protection group.
The command uses standard array notation to specify the first member of the $PGroup array.

## PARAMETERS

### -E14Options
Indicates that the cmdlet operates on a Microsoft Exchange Server 2010 data sources.

```yaml
Type: SwitchParameter
Parameter Sets: E14Options
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeOptions
Indicates that this cmdlet operates on Exchange Server data sources.

```yaml
Type: SwitchParameter
Parameter Sets: ExchangeOptions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystem
Indicates that the cmdlet operates on file system data sources.

```yaml
Type: SwitchParameter
Parameter Sets: FileSystem
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group for which this cmdlet returns options.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Datasource

## NOTES

## RELATED LINKS

[Set-DPMDatasourceProtectionOption](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceProtectionOption.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

