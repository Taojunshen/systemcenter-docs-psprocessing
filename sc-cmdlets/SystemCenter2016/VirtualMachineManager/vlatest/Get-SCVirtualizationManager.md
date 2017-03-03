---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A189B6BE-DC66-4196-A0C6-F03D8812A273
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualizationManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualizationManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualizationManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVirtualizationManager

## SYNOPSIS
Gets a VMware vCenter Server object managed by VMM.

## SYNTAX

```
Get-SCVirtualizationManager [-VMMServer <ServerConnection>] [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualizationManager** cmdlet gets one or VMware vCenter Server objects managed by Virtual Machine Manager (VMM).
A vCenter Server is a virtualization manager that typically manages ESX hosts and virtual machines deployed on those hosts.

If a vCenter Server is connected to VMM, you can use this cmdlet to view the properties of the vCenter Server object or to store it in a variable for use by other cmdlets.

## EXAMPLES

### Example 1: Display information about each VMware vCenter Server managed by VMM
```
PS C:\> Get-SCVirtualizationManager -VMMServer "VMMServer01.Contoso.com"
```

This command retrieves all virtualization manager objects currently associated with VMM from VMMServer01 and displays information about the returned objects.

### Example 2: Get a specific VMware vCenter Server managed by VMM
```
PS C:\> Get-SCVirtualizationManager -VMMServer "VMMServer01.Contoso.com" -ComputerName "vCenterServer02.Contoso.com"
```

This command gets the vCenter Server object named VirtMgrServer02 and displays information about the returned object.

### Example 3: Get all VMware vCenter Servers that match specified criteria
```
PS C:\> $vCenterServers = Get-SCVirtualizationManager -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -match "Server"}
PS C:\> $vCenterServers
```

The first command gets all virtualization manager objects whose name includes the string "Server" and stores the returned objects in the $vCenterServers array.

The second command displays information about each vCenter Server object.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

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

### VirtualizationManager
This cmdlet returns a **VirtualizationManager** object.

## NOTES

## RELATED LINKS

[Add-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVirtualizationManager.md)

[Read-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualizationManager.md)

[Remove-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualizationManager.md)

[Set-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualizationManager.md)

