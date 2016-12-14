---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceConfiguration.md
schema: 2.0.0
ms.assetid: 2AF46671-DF2A-4372-AED6-682619E368C1
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCComputerTierConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCComputerTierConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCComputerTierConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCComputerTierConfiguration

## SYNOPSIS
Gets the computer tier configuration for a service deployment configuration.

## SYNTAX

```
Get-SCComputerTierConfiguration [-VMMServer <ServerConnection>] -ServiceConfiguration <ServiceConfiguration>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCComputerTierConfiguration** cmdlet gets the computer tier configuration for a service deployment configuration.

## EXAMPLES

### Example 1: Get the computer tier configuration object for a service configuration
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $TierConfig
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuratoin stored in Service01 and stores the object in the $TierConfig variable.

The last command displays the properties of the computer tier configuration stored in $TierConfig to the user.

## PARAMETERS

### -ServiceConfiguration
Specifies a service configuration object.

```yaml
Type: ServiceConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### ComputerTierConfiguration
This cmdlet returns a **ComputerTierConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceConfiguration.md)

[Set-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCComputerTierConfiguration.md)
