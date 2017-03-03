---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 48476926-9EFA-427D-BA2C-99704E344222
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPXEServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPXEServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPXEServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCPXEServer

## SYNOPSIS
Gets a PXEServer object from the VMM database.

## SYNTAX

### ID (Default)
```
Get-SCPXEServer [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

### Name
```
Get-SCPXEServer [-VMMServer <ServerConnection>] [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPXEServer** cmdlet gets one or more **PXEServer** objects from the Virtual Machine Manager (VMM) database.

For information about adding a **PXEServer** object to VMM, type `Get-Help Add-SCPXEServer -Detailed`.

## EXAMPLES

### Example 1: Retrieve a PXE server by its FQDN
```
PS C:\> Get-SCPXEServer -ComputerName "WDSServer01.Contoso.com"
```

This command gets the PXE server named WDSServer01.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

```yaml
Type: String
Parameter Sets: Name
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
Parameter Sets: ID
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### PXEServer
This cmdlet returns a **PXEServer** object.

## NOTES

## RELATED LINKS

[Add-SCPXEServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCPXEServer.md)

[Remove-SCPXEServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPXEServer.md)

