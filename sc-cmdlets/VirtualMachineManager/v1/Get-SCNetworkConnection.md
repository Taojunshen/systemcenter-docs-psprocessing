---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCNetworkConnection.md
schema: 2.0.0
ms.assetid: 154D2D09-467B-475F-90F7-422448AE9493
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCNetworkConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCNetworkConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCNetworkConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCNetworkConnection

## SYNOPSIS
Gets a network service connection.

## SYNTAX

### All (Default)
```
Get-SCNetworkConnection [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### ByNetworkService
```
Get-SCNetworkConnection [-VMMServer <ServerConnection>] -Service <NetworkService> [<CommonParameters>]
```

### ByID
```
Get-SCNetworkConnection [-VMMServer <ServerConnection>] -ID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNetworkConnection** cmdlet gets one or more network service connections.

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
Parameter Sets: All
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

### -Service
Specifies a network service object.

```yaml
Type: NetworkService
Parameter Sets: ByNetworkService
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

## NOTES

## RELATED LINKS

[Add-SCNetworkConnection](xref:VirtualMachineManager/v1/Add-SCNetworkConnection.md)

[Get-SCVMSubnet](xref:VirtualMachineManager/v1/Get-SCVMSubnet.md)

[Remove-SCNetworkConnection](xref:VirtualMachineManager/v1/Remove-SCNetworkConnection.md)

[Set-SCNetworkConnection](xref:VirtualMachineManager/v1/Set-SCNetworkConnection.md)

