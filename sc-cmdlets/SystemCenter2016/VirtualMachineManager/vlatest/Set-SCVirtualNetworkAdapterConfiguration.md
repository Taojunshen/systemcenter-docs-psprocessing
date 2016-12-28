---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8A61B375-73FA-4D09-BF28-F9D72049BF7B
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualNetworkAdapterConfiguration

## SYNOPSIS
Modifies the virtual network adapter configuration contained within a virtual machine configuration.

## SYNTAX

```
Set-SCVirtualNetworkAdapterConfiguration [-IPv4PAAddressPool <StaticIPAddressPool>]
 [-IPv4AddressPool <StaticIPAddressPool>] [-PinIPv4PAAddressPool <Boolean>] [-PinIPv4AddressPool <Boolean>]
 [-IPv6PAAddressPool <StaticIPAddressPool>] [-IPv6AddressPool <StaticIPAddressPool>]
 [-PinIPv6AddressPool <Boolean>] [-PinIPv6PAAddressPool <Boolean>] [-MACAddressPool <MACAddressPool>]
 [-PinMACAddressPool <Boolean>] [-IPv4PAAddress <String>] [-IPv4Address <String>] [-IPv6PAAddress <String>]
 [-IPv6Address <String>] [-MACAddress <String>]
 -VirtualNetworkAdapterConfiguration <VirtualNetworkAdapterConfiguration> [-VMSubnet <VMSubnet>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualNetworkAdapterConfiguration** cmdlet modifies the virtual network adapter configuration information that is contained within a virtual machine configuration.

## EXAMPLES

### Example 1: Set the properties of the virtual network adapter configuration for a virtual machine configuration
```
PS C:\> $ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $VNAConfig = Get-SCVirtualNetworkAdapterConfiguration -VMConfiguration $VMConfig[0]
PS C:\> Set-SCVirtualNetworkAdapterConfiguration -VirtualNetworkAdapterConfiguration $VNAConfig -IPv4Address "10.255.234.155" -PinIPv4AddressPool $True
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration for the computer tier configuration stored in $TierConfig and stores the object in the $VMConfig variable.

The fourth command gets the virtual network adapter configuration for the first virtual machine configuration stored in $VMConfig and stores the object in the $VNAConfig variable.

The last command changes the IPv4Address property of the network adapter configuration stored in $VNAConfig, and pins the value of the IP address, which prevents it from being changed during placement.

## PARAMETERS

### -IPv4Address
Specifies an IPv4 address.

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

### -IPv4AddressPool
Specifies a static address pool that contains IPv4 addresses.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4PAAddress
Specifies a provider IP address in IPv4 format.

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

### -IPv4PAAddressPool
Specifies a provider IP address pool that contains IP addresses in IPv4 format.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6Address
Specifies an IPv6 address.

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

### -IPv6AddressPool
Specifies a static address pool that contains IPv6 addresses.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv6PAAddress
Specifies a provider IP address in IPv6 format.

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

### -IPv6PAAddressPool
Specifies a provider IP address pool that contains IP addresses in IPv6 format.

```yaml
Type: StaticIPAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -MACAddress
Specifies the media access control (MAC) address, or a set of MAC addresses, for a physical or virtual network adapter on a computer.

- Example format for a single MAC address: `-MACAddress "00-15-5D-B4-DC-00"`
- Example format for a set of MAC addresses: `-MACAddress "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`

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

### -MACAddressPool
Specifies a MAC address pool.

```yaml
Type: MACAddressPool
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PinIPv4AddressPool
Indicates whether the IPv4 address pool chosen by the user is retained during service deployment configuration.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PinIPv4PAAddressPool
Indicates whether the IPv4 provider address pool chosen by the user is retained during service deployment configuration.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PinIPv6AddressPool
Indicates whether the IPv6 address pool chosen by the user is retained during service deployment configuration.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PinIPv6PAAddressPool
Indicates whether the IPv6 provider address pool chosen by the user is retained during service deployment configuration.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PinMACAddressPool
Indicates whether the MAC address pool chosen by the user is retained during service deployment configuration.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -VMSubnet
Specifies a virtual machine subnet object.

To obtain a **VMSubnet** object, use the **Get-SCVMSubnet** cmdlet.

```yaml
Type: VMSubnet
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkAdapterConfiguration
Specifies a virtual network adapter configuration object.

```yaml
Type: VirtualNetworkAdapterConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-SCVirtualNetworkAdapterConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterConfiguration.md)

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMConfiguration.md)

