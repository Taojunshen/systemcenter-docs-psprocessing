---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E03E28A6-0A93-4113-A98F-70C6828A16F9
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterPortProfileSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterPortProfileSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterPortProfileSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVirtualNetworkAdapterPortProfileSet

## SYNOPSIS
Gets a virtual network adapter port profile set.

## SYNTAX

### All (Default)
```
Get-SCVirtualNetworkAdapterPortProfileSet [-VMMServer <ServerConnection>] [[-Name] <String>]
 [<CommonParameters>]
```

### ById
```
Get-SCVirtualNetworkAdapterPortProfileSet [-VMMServer <ServerConnection>] [[-Name] <String>] -ID <Guid>
 [<CommonParameters>]
```

### LogicalSwitch
```
Get-SCVirtualNetworkAdapterPortProfileSet [-VMMServer <ServerConnection>] [[-Name] <String>]
 -LogicalSwitch <LogicalSwitch> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualNetworkAdapterPortProfileSet** cmdlet gets one or more virtual network adapter port profile sets.
You can get a virtual network adapter port profile set by its name or ID, or all virtual network adapter port profile sets for a logical switch.

## EXAMPLES

### Example 1: Get a virtual network adapter port profile set by its name
```
PS C:\> Get-SCVirtualNetworkAdapterPortProfileSet -Name "VirtualNetworkAdapterPortProfSet01"
```

This command gets the virtual network adapter port profile set object named VirtualNetworkAdapterPortProfileSet01 and displays information about the object to the user.

### Example 2: Get all virtual network adapter port profile sets for a logical switch
```
PS C:\> $LogSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01" 
PS C:\> Get-SCVirtualNetworkAdapterPortProfileSet -LogicalSwitch $LogSwitch
```

The first command gets the logical switch object named LogicalSwitch01 and stores the object in the $LogSwtich variable.

The second command gets all virtual network adapter port profile sets that use logical switch LogicalSwitch01.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalSwitch
Specifies a logical switch object.

```yaml
Type: LogicalSwitch
Parameter Sets: LogicalSwitch
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

## NOTES

## RELATED LINKS

[Get-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitch.md)

[New-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterPortProfileSet.md)

[Remove-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapterPortProfileSet.md)

[Set-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterPortProfileSet.md)

