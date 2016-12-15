---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: d3dfe385-039f-4fb5-a6ac-6d05c3b55292
schema: 2.0.0
ms.assetid: CAB90DE3-F5F4-41FA-9067-FDB5210B9AF5
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMAccessLicense.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMAccessLicense.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMAccessLicense.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMAccessLicense

## SYNOPSIS
Gets licensing information for a DPM server and protected computers.

## SYNTAX

### License (Default)
```
Get-DPMAccessLicense [[-DPMServerName] <String>] [-License] [<CommonParameters>]
```

### LicenseName
```
Get-DPMAccessLicense [[-DPMServerName] <String>] [-LicenseName] <LicenseNames> [[-Period] <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMAccessLicense** cmdlet gets licensing information for a System Center 2016 - Data Protection Manager (DPM) server and protected computers.

## EXAMPLES

### Example 1: Get licenses for servers
```
PS C:\>Get-DPMAccessLicense -LicenseName SML -DPMServerName "DPMServer07"
```

This command gets licenses for computers that run server operating systems that a DPM server named DPMServer07 manages.

### Example 2: Get licenses for server for the last five days
```
PS C:\>Get-DPMAccessLicense -LicenseName SML -Period 5 -DPMServerName "DPMServer07"
```

This command gets all active licenses for last five days for computers that run server operating systems that a DPM server named DPMServer07 manages.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet gets licensing information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -License
Indicates that the cmdlet displays the following license information.

The acceptable values for this parameter are:

- Name of the product
- Name of the license
- Type of license
- Tabulation method

```yaml
Type: SwitchParameter
Parameter Sets: License
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseName
Specifies a type of license.

The acceptable values for this parameter are:

- SML.
All computers managed by DPM that run a server operating system.
- CML.
All computers managed by DPM that run a client operating system.

```yaml
Type: LicenseNames
Parameter Sets: LicenseName
Aliases: 
Accepted values: SML, CML

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Period
Specifies a period from zero (0) to seven (7).
The cmdlet displays licenses used between the current day and (Period - n - 90).
If you do not provide a value for this parameter, the cmdlet uses the value 0.

```yaml
Type: Int32
Parameter Sets: LicenseName
Aliases: PeriodInDays

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

