---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2D7DC118-99CA-41A6-85C5-B8A3F44081CE
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPPeer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPPeer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPPeer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCNCBGPPeer

## SYNOPSIS
Creates VMM BGP Peer object that can be used for BGP configuration.

## SYNTAX

```
New-SCNCBGPPeer [-VMMServer <ServerConnection>] -RouterName <String> -RouterIPAddress <String>
 -RouterAsn <UInt32> [<CommonParameters>]
```

## DESCRIPTION
The **New-SCNCBGPPeer** cmdlet creates a VMM Border Gateway Protocol (BGP) Peer object that can be used for BGP configuration with System Center 2016 Virtual Machine Manager.
You must configure either a BGP Peer or a BGP Router role to provide connectivity between your data center and external internet end points.
You can create and configure more than one BGP Peer by using one System Center 2016 Virtual Machine Manager installation.

## EXAMPLES

### Example 1: Create a NC BGP Peer
```
PS C:\> New-SCNCBGPPeer -RouterName "BGPPeer01" -RouterIPAddress "10.10.50.45" -RouterAsn 65
```

This command creates a BGP Peer with router name BGPPeer01.
This object can used as a peer for BGP Router using the **New-SCNCBGPRouter** cmdlet.

## PARAMETERS

### -RouterAsn
```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouterIPAddress
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

### -RouterName
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

### -VMMServer
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

[New-SCNCBGPRouter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPRouter.md)

[Set-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRoleResource.md)

