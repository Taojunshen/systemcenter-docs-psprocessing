---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7A371B1B-E89A-4CA9-843C-1E59B71D1A2B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISOConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISOConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISOConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCISOConfiguration

## SYNOPSIS
Gets the ISO configuration for a virtual machine configuration.

## SYNTAX

```
Get-SCISOConfiguration [-VMMServer <ServerConnection>] -VMConfiguration <VMConfiguration> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCISOConfiguration** cmdlet gets the ISO configuration for a virtual machine configuration.
An ISO configuration allows you to customize the source and target locations for the physical resources that are needed to create a virtual machine.

## EXAMPLES

### Example 1: Get the ISO configuration for a given virtual machine configuration
```
PS C:\> $ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $ISOConfig = Get-SCISOConfiguration -VMConfiguration $VMConfig
PS C:\> $ISOConfig
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration object for the the service configuration in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration for the computer tier configuration stored in $TierConfig and stores the object in the $VMConfig variable.

The fourth command gets the ISO configuration for the first virtual machine configuration stored in $VMConfig and stores the object in the $ISOConfig variable.

The last command displays the properties of the ISO configuration stored in $ISOConfig to the user.

## PARAMETERS

### -VMConfiguration
Specifies a virtual machine configuration object.

```yaml
Type: VMConfiguration
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

### ISOConfiguration
This cmdlet returns an **ISOConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTierConfiguration.md)

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceConfiguration.md)

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMConfiguration.md)

[Set-SCISOConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCISOConfiguration.md)

