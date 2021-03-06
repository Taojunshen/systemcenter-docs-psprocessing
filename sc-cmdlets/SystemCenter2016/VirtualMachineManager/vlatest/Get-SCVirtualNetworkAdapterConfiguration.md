---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A519812E-B547-46CD-BE70-AB2BF7CFF163
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVirtualNetworkAdapterConfiguration

## SYNOPSIS
Gets the virtual network adapter configuration information contained in a virtual machine configuration.

## SYNTAX

```
Get-SCVirtualNetworkAdapterConfiguration [-VMMServer <ServerConnection>] -VMConfiguration <BaseVMConfiguration>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualNetworkAdapterConfiguration** cmdlet gets the virtual network adapter configuration information that is contained within a virtual machine configuration.

## EXAMPLES

### Example 1: Get a virtual network adapter configuration from a virtual machine configuration
```
PS C:\> $ServiceConfig = Get-SCServiceConfiguration -Name "Service01" 
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig 
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $VNAConfig = Get-SCVirtualNetworkAdapterConfiguration -VMConfiguration $VMConfig[0]
PS C:\> $VNAConfig
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration for the computer tier configuration stored in $TierConfig and stores the object in the $VMConfig variable.

The fourth command gets the virtual network adapter configuration for the first virtual machine configuration stored in $VMConfig.

The last command displays the properties of the virtual network adapter configuration stored in $VMConfig to the user.

## PARAMETERS

### -VMConfiguration
Specifies a virtual machine configuration object.

```yaml
Type: BaseVMConfiguration
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

### VirtualNetworkAdapterConfiguration
This cmdlet returns a **VirtualNetworkAdapterConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTierConfiguration.md)

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceConfiguration.md)

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMConfiguration.md)

[Set-SCVirtualNetworkAdapterConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterConfiguration.md)

