---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCMACAddressPool.md
schema: 2.0.0
ms.assetid: 0B534A30-37EC-4038-A89A-832008E28119
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCMACAddressPool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCMACAddressPool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCMACAddressPool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCMACAddressPool

## SYNOPSIS
Gets a MAC address pool.

## SYNTAX

```
Get-SCMACAddressPool [-VMMServer <ServerConnection>] [-MACAddress <String>] [[-Name] <String>]
 [-VMHostGroup <HostGroup>] [-VirtualizationPlatform <VirtualizationPlatform>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCMACAddressPool** cmdlet gets one or more (Media Access Control) MAC address pools.
A MAC address pool can be associated with one or more Virtual Machine Manager (VMM) host groups.

## EXAMPLES

### Example 1: Get all MAC address pools for a host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> Get-SCMACAddressPool -VMHostGroup $HostGroup
```

The first command gets the host group named Production and stores it in the $HostGroup variable.

The second command gets all MAC address pools for the host group stored in $HostGroup (including its parent host group if inheritance is enabled).

## PARAMETERS

### -MACAddress
Specifies the MAC address or a set of MAC addresses for a physical or virtual network adapter on a computer.

Example format for a single MAC address: 

`-MACAddress "00-15-5D-B4-DC-00"`

Example formats for a set of MAC addresses: 

`-MACAddress "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`
`$Macs = "00-15-5D-B4-DC-00", "00-1A-A0-E3-75-29"`

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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

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

### -VirtualizationPlatform
Specifies the virtualization platform of a virtual machine host managed by VMM.
The acceptable values for this parameter are:

- HyperV
- VMwareESX
- XENServer

```yaml
Type: VirtualizationPlatform
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, VirtualServer, HyperV, VMWareVC, VMWareESX, XENServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MACAddressPool
This cmdlet returns a **MACAddressPool** object.

## NOTES

## RELATED LINKS

[New-SCMACAddressPool](xref:VirtualMachineManager/v1/New-SCMACAddressPool.md)

[Remove-SCMACAddressPool](xref:VirtualMachineManager/v1/Remove-SCMACAddressPool.md)

[Set-SCMACAddressPool](xref:VirtualMachineManager/v1/Set-SCMACAddressPool.md)

