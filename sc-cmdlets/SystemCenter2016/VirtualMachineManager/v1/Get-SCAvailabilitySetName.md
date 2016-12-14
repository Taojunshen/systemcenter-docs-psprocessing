---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 4776c225-8a45-4453-847d-e4f16a57a44e
schema: 2.0.0
ms.assetid: 0D6240D6-4F66-4952-9061-305E6E21634B
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCAvailabilitySetName.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCAvailabilitySetName.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCAvailabilitySetName.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
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
PS C:\>Get-SCAvailabilitySetName -VMMServer "VMMServer01"
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

