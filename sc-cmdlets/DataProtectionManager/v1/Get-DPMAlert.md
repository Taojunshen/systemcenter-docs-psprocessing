---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./DataProtectionManager.md
schema: 2.0.0
ms.assetid: 0C42210C-2158-4180-B4FD-1EA99C7EE1E7
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMAlert.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMAlert.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMAlert.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMAlert

## SYNOPSIS
Gets alerts for a DPM server.

## SYNTAX

```
Get-DPMAlert [[-DPMServerName] <String>] [-IncludeInactiveAlerts] [-Async] [-IncludeAlerts <IncludeAlertsType>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMAlert** cmdlet gets alerts for a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Get all active alerts for a specified server
```
PS C:\>Get-DPMAlert -DPMServerName DPMServer073 -IncudeAlerts AllActive
```

This command gets alerts for the DPM server named DPMServer073.
The command includes all active alerts.

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

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet gets alerts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeAlerts
Specifies which alert to display.

The acceptable values for this parameter are:

- AllActive 
- FromContext

```yaml
Type: IncludeAlertsType
Parameter Sets: (All)
Aliases: 
Accepted values: AllActive, FromContext

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeInactiveAlerts
Indicates that the cmdlet displays inactive alerts.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### DPMServerName
Specifies the name of a DPM server.

## OUTPUTS

## NOTES

## RELATED LINKS

[Data Protection Manager Cmdlets](xref:DataProtectionManager/v1/DataProtectionManager.md)

