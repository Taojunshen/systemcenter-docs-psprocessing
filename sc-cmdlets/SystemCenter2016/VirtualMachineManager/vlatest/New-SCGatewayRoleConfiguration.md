---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 122e2d3c-ee43-4828-9ff1-4c3a2fa148f6
schema: 2.0.0
ms.assetid: 289B358E-F43A-486B-BC22-DFEA80F367F6
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGatewayRoleConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGatewayRoleConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGatewayRoleConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCGatewayRoleConfiguration

## SYNOPSIS
Creates a gateway role configuration.

## SYNTAX

```
New-SCGatewayRoleConfiguration [-VMMServer <ServerConnection>] -RedundantResourceCount <UInt32>
 -GatewayCapacityKbps <UInt64>
 -PublicIPAddresses <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.AllocatedIPAddress]>
 -GreVipSubnets <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SubnetVLan]>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCGatewayRoleConfiguration** cmdlet creates a gateway role configuration in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Create gateway role configuration
```
PS C:\>$FabricRoleConfiguration = New-SCGatewayRoleConfiguration -GatewayCapacityKbps 1024000 -PublicIPAddresses $publicIPV4Address -RedundantResourceCount 1 -GreVipSubnets $SubnetVlansGreVip
PS C:\> $FabricRole = Set-SCFabricRole -FabricRole $FabricRole -GatewayConfiguration $FabricRoleConfiguration
```

The first command creates a gateway role configuration by using **New-SCGatewayRoleConfiguration**.

The second command configures the gateway fabric role with that configuration.

## PARAMETERS

### -GatewayCapacityKbps
Specifies the gateway capacity in Kbps.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GreVipSubnets


```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SubnetVLan]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIPAddresses
```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.AllocatedIPAddress]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedundantResourceCount
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
