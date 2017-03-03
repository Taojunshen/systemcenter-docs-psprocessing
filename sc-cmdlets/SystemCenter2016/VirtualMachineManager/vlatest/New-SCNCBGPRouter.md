---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7E376681-CC06-4BF3-B555-75711E5C81B5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPRouter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPRouter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPRouter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCNCBGPRouter

## SYNOPSIS
Creates VMM BGP Router object that can be used for BGP configuration.

## SYNTAX

```
New-SCNCBGPRouter [-VMMServer <ServerConnection>] -LocalASN <UInt32>
 [-RouterPeers <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.NCBGPPeer]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCNCBGPRouter** cmdlet creates a VMM Border Gateway Protocol (BGP) Router object that can be used for BGP configuration with System Center 2016 Virtual Machine Manager.
You must configure either a BGP Router or a BGP Peer role to provide connectivity between your data center and external internet end points.
You can create and configure more than one BGP Router by using one System Center 2016 Virtual Machine Manager installation.

## EXAMPLES

### Example: Create a BGP Router and peer with BGP Peer
```
PS C:\> $bgpPeer = New-SCNCBGPPeer RouterName "BGPPeer01"  -RouterIPAddress "10.10.50.45"  -RouterAsn 65 PS C:\> $bgpRouter = New-SCNCBGPRouter -LocalASN 64 -RouterPeers @($bgpPeer
```

This example creates a BGP Peer with router name BGPPeer01 and peers with BGP Router.
The BGP Router object can be used in **Set-SCFabricRoleResource** to configure the BGP peer routers for Fabric Role Resources such as Load Balancer and Gateway.

Step 1: Create BGP Peer

Step 2: Create BGP Router

Step 3: Use the bgpRouter created in step 2 to configure the BGP peer routers for Fabric Role Resources using **Set-SCFabricRoleResource**.

## PARAMETERS

### -LocalASN
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

### -RouterPeers
```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.NCBGPPeer]
Parameter Sets: (All)
Aliases: 

Required: False
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

[Set-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRoleResource.md)

