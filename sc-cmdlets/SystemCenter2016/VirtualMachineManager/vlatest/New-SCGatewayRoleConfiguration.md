---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 289B358E-F43A-486B-BC22-DFEA80F367F6
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGatewayRoleConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGatewayRoleConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGatewayRoleConfiguration.md
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
PS C:\> $FabricRoleConfiguration = New-SCGatewayRoleConfiguration -GatewayCapacityKbps 1024000 -PublicIPAddresses $publicIPV4Address -RedundantResourceCount 1 -GreVipSubnets $SubnetVlansGreVip
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

