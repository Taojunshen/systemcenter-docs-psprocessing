---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCNetworkService.md
schema: 2.0.0
ms.assetid: 6F4C808F-6F42-4F77-9E3E-9B43B5821AF6
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCNetworkService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCNetworkService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCNetworkService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCNetworkService

## SYNOPSIS
Gets a network service.

## SYNTAX

### Global (Default)
```
Get-SCNetworkService [-VMMServer <ServerConnection>] [-All] [-ServiceType <NetworkServiceType>]
 [<CommonParameters>]
```

### ByName
```
Get-SCNetworkService [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### ByID
```
Get-SCNetworkService [-VMMServer <ServerConnection>] [-Name <String>] -ID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNetworkService** cmdlet gets a network service.

## EXAMPLES

### 1:
```

```

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
Specifies the name of a network object.

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

```yaml
Type: String
Parameter Sets: ByID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceType
Specifies the type of network service.
The acceptable values for this parameter are:

 

- Unspecified

- Gateway

- LoadBalancer

- NetworkVirtualizationPolicy

- NetworkManager

- VirtualSwitchExtensionManager

- NetworkSwitch

```yaml
Type: NetworkServiceType
Parameter Sets: Global
Aliases: 
Accepted values: Unspecified, Gateway, LoadBalancer, NetworkVirtualizationPolicy, NetworkManager, VirtualSwitchExtensionManager, NetworkSwitch

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCNetworkService](xref:VirtualMachineManager/v1/Add-SCNetworkService.md)

[Read-SCNetworkService](xref:VirtualMachineManager/v1/Read-SCNetworkService.md)

[Remove-SCNetworkService](xref:VirtualMachineManager/v1/Remove-SCNetworkService.md)

[Set-SCNetworkService](xref:VirtualMachineManager/v1/Set-SCNetworkService.md)

[Test-SCNetworkService](xref:VirtualMachineManager/v1/Test-SCNetworkService.md)
