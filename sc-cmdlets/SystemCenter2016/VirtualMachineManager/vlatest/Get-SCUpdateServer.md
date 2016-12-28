---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8A730D38-FB20-4F79-AD08-9A5EC04D760F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdateServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdateServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdateServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCUpdateServer

## SYNOPSIS
Gets the WSUS server that has been added to VMM.

## SYNTAX

### ID (Default)
```
Get-SCUpdateServer [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

### Name
```
Get-SCUpdateServer [-VMMServer <ServerConnection>] [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCUpdateServer** cmdlet gets the Microsoft Windows Server Update Services (WSUS) computer that has been added to Virtual Machine Manager (VMM).
For information about how to add an update server to VMM, type `Get-Help Add-SCUpdateServer`.

## EXAMPLES

### Example 1: Get an update server
```
PS C:\> $UpdateServer = Get-SCUpdateServer -ComputerName "WSUSComputer01"
```

This command gets the update server object named WSUSComputer01, and then stores the object in the $UpdateServer variable.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.
The acceptable values for this parameter are:

- Fully qualified domain name (FQDN) 
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
Specifies the unique ID of the WSUS that this cmdlet gets.

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
Specifies a VMM server for which this cmdlet gets the WSUS server.

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

### UpdateServer
This cmdlet returns an **UpdateServer** object.

## NOTES

## RELATED LINKS

[Add-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUpdateServer.md)

[Remove-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUpdateServer.md)

[Set-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUpdateServer.md)

