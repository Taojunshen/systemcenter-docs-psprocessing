---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0D6240D6-4F66-4952-9061-305E6E21634B
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCAvailabilitySetName.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCAvailabilitySetName.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCAvailabilitySetName.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCAvailabilitySetName

## SYNOPSIS
Gets the names of availability sets associated with virtual machines or computer tier configurations.

## SYNTAX

```
Get-SCAvailabilitySetName [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCAvailabilitySetName** cmdlet gets the names of availability sets that are associated with virtual machines or computer tier configurations.

You can specify availability set names in a virtual machine configuration or a computer tier template.

## EXAMPLES

### Example 1: Get the names of all availability sets on a specified VMM management server
```
PS C:\> Get-SCAvailabilitySetName -VMMServer "VMMServer01"
```

This command gets all the names of availability sets on VMMServer01.

## PARAMETERS

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String[]
This cmdlet returns an array of **String** objects.

## NOTES

## RELATED LINKS

