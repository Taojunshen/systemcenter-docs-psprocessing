---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=330323
schema: 2.0.0
ms.assetid: 352F4E0F-9E7A-4E64-8AE3-B53C17254568
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFExtensibleEventHandler.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFExtensibleEventHandler.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/v1.0/Get-SCSPFExtensibleEventHandler.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfExtensibleEventHandler

## SYNOPSIS
Gets the configuration of a runbook in Orchestrator.

## SYNTAX

```
Get-SCSpfExtensibleEventHandler -EventName <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFExtensibleEventHandler** cmdlet gets the configuration for an Orchestrator runbook that is invoked whenever the VirtualMachineCreated or ServiceCreated extensible events are raised.

## EXAMPLES

### Example 1: Get the current configuration
```
PS C:\>Get-SCSPFExtensibleEventHandler -EventName "VirtualMachineCreated"
```

This command gets the runbook that is configured to be invoked when the VirtualMachineCreated extensible event is raised.
This command gets the event name, the uniform resource identifier (URI) for the runbook, and the path for the runbook.

## PARAMETERS

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-SCSPFExtensibleEventHandler](xref:SystemCenter2016/ServiceProviderFoundation/v1.0/Set-SCSPFExtensibleEventHandler.md)

