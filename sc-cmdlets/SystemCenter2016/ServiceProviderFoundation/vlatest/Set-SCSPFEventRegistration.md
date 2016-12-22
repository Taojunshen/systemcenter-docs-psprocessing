---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: FE302D37-70DC-448C-ADA3-288292BDF2B2
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFEventRegistration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFEventRegistration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFEventRegistration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSPFEventRegistration

## SYNOPSIS
Sets a Service Management Automation event to automate a runbook.

## SYNTAX

```
Set-SCSPFEventRegistration -Resource <String> -Action <EventRegistrationActionNames> [-RunbookName <String>]
 [-Enabled] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSPFEventRegistration** cmdlet registers a Service Management Automation event to automate a runbook.

## EXAMPLES

### Example 1: Set an event
```
PS C:\>Set-SCSPFEventRegistration -ResourceName "VMM.VirtualMachine" -ActionName "Create" -RunbookName "Invoke-SampleCmdlet"
```

This command sets a runbook to invoke when the create event for a new virtual machine is executed.

## PARAMETERS

### -Action
Specifies the action on a resource for which an orchestrator event is registered.
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
Parameter Sets: (All)
Aliases: 
Accepted values: Create, Update, Delete, Action_Pause, Action_Publish, Action_Repair, Action_Restart, Action_Resume, Action_Scale, Action_Shutdown, Action_Start, Action_Stop, Action_Unpublish, UpdateStatus

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

### -Enabled
Indicates that the event is enabled.

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

### -Resource
Specifies the resource for which the orchestrator event is registered.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunbookName
Specifies the runbook to invoke when the orchestrator event is executed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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

[Get-SCSPFEventRegistration](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFEventRegistration.md)

