---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: ./Get-SCSPFExtensibleEventHandler.md
schema: 2.0.0
ms.assetid: 42928832-A48E-4426-A41E-5EAB06255052
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Set-SCSPFExtensibleEventHandler.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Set-SCSPFExtensibleEventHandler.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Set-SCSPFExtensibleEventHandler.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSpfExtensibleEventHandler

## SYNOPSIS
Sets an extensible event handler in Service Provider Foundation.

## SYNTAX

```
Set-SCSpfExtensibleEventHandler -EventName <String> [-OrchestratorUri <String>] [-RunbookPath <String>]
 [-Enable] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSPFExtensibleEventHandler** cmdlet invokes a runbook in System Center 2016 - Orchestrator to run whenever a new virtual machine or new service is created.
The virtual machine or service must be created by calls to Service Provider Foundation with the Virtual Machine Manager (VMM) service.
Service Provider Foundation raises internal events to invoke the runbook, and the runbook will be invoked continuously as long as the extensible event handler is enabled.

Service Provider Foundation will not invoke the runbook if the virtual machine or service was created by other means, such as by using PowerShell cmdlets for by using the console in VMM.

To support the infrastructure for invoking a runbook, Service Provider Foundation calls the Start-SCOrchestratorRunbook cmdlet internally; the user does not need to call it explicitly.

## EXAMPLES

### Example 1: Set an event handler
```
PS C:\>Set-SCSPFExtensibleEventHandler -EventName "VirtualMachineCreated" -OrchestratorUri "https://scxspf-ws8-24:82/Orchestrator2012/Orchestrator.svc" -RunbookPath "\SPF Runbooks\Extensibility\VM Created" -Enable
```

This command enables an event handler to invoke a runbook.

### Example 2: Disable an event handler
```
PS C:\>Set-SCSPFExtensibleEventHandler -EventName "VirtualMachineCreated" -OrchestratorUri "https://scxspf-ws8-24:82/Orchestrator2012/Orchestrator.svc" -RunbookPath "\SPF Runbooks\Extensibility\VM Created"
```

This command disables an event handler from invoking a runbook because the *Enable* parameter is omitted.

## PARAMETERS

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

### -Enable
Indicates that the extensible event handler is enabled.
Omit this parameter to disable the handler.

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

### -EventName
Specifies either VirtualMachineCreated or ServiceCreated for the event that invokes an Orchestrator runbook.

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

### -OrchestratorUri
Specifies the URI of the Orchestrator web service as specified by the web.config file in C:\Program Files (x86)\Microsoft System Center 2012\Orchestrator\Orchestration Console.

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

### -RunbookPath
Specifies the path to a runbook in Orchestrator.

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

[Get-SCSPFExtensibleEventHandler](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFExtensibleEventHandler.md)

