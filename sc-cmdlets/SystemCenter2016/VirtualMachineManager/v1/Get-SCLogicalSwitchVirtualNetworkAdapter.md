---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCUplinkPortProfileSet.md
schema: 2.0.0
ms.assetid: 7518BDC1-D025-4B25-9792-B480D71F451F
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalSwitchVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalSwitchVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCLogicalSwitchVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCLogicalSwitchVirtualNetworkAdapter

## SYNOPSIS
Gets a logical switch virtual network adapter.

## SYNTAX

### All (Default)
```
Get-SCLogicalSwitchVirtualNetworkAdapter [[-Name] <String>] [-VMMServer <ServerConnection>]
 [-UplinkPortProfileSet <UplinkPortProfileSet>] [<CommonParameters>]
```

### ById
```
Get-SCLogicalSwitchVirtualNetworkAdapter [[-Name] <String>] [-VMMServer <ServerConnection>] -ID <Guid>
 [-UplinkPortProfileSet <UplinkPortProfileSet>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLogicalSwitchVirtualNetworkAdapter** cmdlet gets a logical switch virtual network adapter.

## EXAMPLES

### Example 1: Get a logical switch virtual network adapter
```
PS C:\>$HostVNicVar = Get-SCLogicalSwitchVirtualNetworkAdapter -Name "LogSw01_hostMgmt"
```

This command gets a logical switch virtual network adapter by its name.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -UplinkPortProfileSet
Specifies an uplink port profile set object.

To obtain an uplink port profile set object, use the Get-SCUplinkPortProfileSet cmdlet.

```yaml
Type: UplinkPortProfileSet
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md)

[New-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCLogicalSwitchVirtualNetworkAdapter.md)

[Remove-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCLogicalSwitchVirtualNetworkAdapter.md)

[Set-SCLogicalSwitchVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCLogicalSwitchVirtualNetworkAdapter.md)

