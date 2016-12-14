---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCComputerTierConfiguration.md
schema: 2.0.0
ms.assetid: A2CC16CA-9A21-4BF3-B96B-DDF7085C5C1D
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualHardDiskConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualHardDiskConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualHardDiskConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualHardDiskConfiguration

## SYNOPSIS
Gets the virtual hard disk configuration contained within a virtual machine configuration.

## SYNTAX

```
Get-SCVirtualHardDiskConfiguration [-VMMServer <ServerConnection>] -VMConfiguration <VMConfiguration>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualHardDiskConfiguration** cmdlet gets the virtual hard disk configuration information that is contained within a virtual machine configuration.

## EXAMPLES

### Example 1: Get the virtual hard disk configuration for a virtual machine configuration
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01" 
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $VHDConfig = Get-SCVirtualHardDiskConfiguration -VMConfiguration $VMConfig[0]
PS C:\> $VHDConfig
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration for the computer tier configuration stored in $TierConfig and stores the object in the $VMConfig variable.

The fourth command gets the virtual hard disk configuration for the first virtual machine configuration stored in $VMConfig.

The last command displays the properties of the virtual hard disk configuration stored in $VMConfig to the user.

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

### VirtualHardDiskConfiguration
This cmdlet returns a **VirtualHardDiskConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCComputerTierConfiguration.md)

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCServiceConfiguration.md)

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMConfiguration.md)

[Set-SCVirtualHardDiskConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualHardDiskConfiguration.md)

