---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CFFBCDA4-8870-41FB-A513-995FC70D9F38
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkGateway.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkGateway.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkGateway.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCNetworkGateway

## SYNOPSIS
Gets a network gateway object.

## SYNTAX

### Global (Default)
```
Get-SCNetworkGateway [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### ByName
```
Get-SCNetworkGateway [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### ByID
```
Get-SCNetworkGateway [-VMMServer <ServerConnection>] -ID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNetworkGateway** cmdlet gets one or more network gateway objects.
You can get an individual network gateway by its name or ID, or all network gateway objects.

## EXAMPLES


## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: Global
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ByID
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
Parameter Sets: ByName
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

[Add-SCNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCNetworkGateway.md)

[Read-SCNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCNetworkGateway.md)

[Remove-SCNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNetworkGateway.md)

[Set-SCNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNetworkGateway.md)

[Test-SCNetworkGateway](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCNetworkGateway.md)

