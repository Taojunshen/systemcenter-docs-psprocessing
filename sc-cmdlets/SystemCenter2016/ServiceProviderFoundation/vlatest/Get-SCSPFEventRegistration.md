---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CCACE15B-A541-4502-B4B9-D40C6BA890D9
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFEventRegistration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFEventRegistration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFEventRegistration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSPFEventRegistration

## SYNOPSIS
Gets the event used to automate runbooks.

## SYNTAX

### Empty (Default)
```
Get-SCSPFEventRegistration [<CommonParameters>]
```

### FromEventRegistrationResourceActionEnabledParameterSetName
```
Get-SCSPFEventRegistration [-Resource <String>] [-Action <EventRegistrationActionNames>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFEventRegistration** cmdlet gets an event registered to automate a runbook as performed by Service Management Automation.

## EXAMPLES

### Example 1: Get an event registration by name
```
PS C:\>$EventBackup = Get-SCSPFEventRegistration -Action "Backup"
```

This command gets an event with the *Action* parameter and stores it in the $EventBackup variable.

## PARAMETERS

### -Action
Specifies the name of the event.
The acceptable values for this parameter are:

- Action_Pause
- Action_Publish
- Action_Repair
- Action_Restart
- Action_Resume
- Action_Scale
- Action_Shutdown
- Action_Start
- Action_Stop
- Action_Unpublish
- Create
- Delete
- Update
- UpdateStatus

```yaml
Type: EventRegistrationActionNames
Parameter Sets: FromEventRegistrationResourceActionEnabledParameterSetName
Aliases: 
Accepted values: Create, Update, Delete, Action_Pause, Action_Publish, Action_Repair, Action_Restart, Action_Resume, Action_Scale, Action_Shutdown, Action_Start, Action_Stop, Action_Unpublish, UpdateStatus

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resource
Specifies the path to the resource.

```yaml
Type: String
Parameter Sets: FromEventRegistrationResourceActionEnabledParameterSetName
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-SCSPFEventRegistration](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFEventRegistration.md)

