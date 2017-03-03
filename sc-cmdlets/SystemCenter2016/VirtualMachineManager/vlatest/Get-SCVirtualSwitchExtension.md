---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AAD0D8F5-516E-4746-992C-6F87BC71A2E1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtension.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtension.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtension.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVirtualSwitchExtension

## SYNOPSIS
Gets a virtual switch extension.

## SYNTAX

### All (Default)
```
Get-SCVirtualSwitchExtension [[-Name] <String>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ByID
```
Get-SCVirtualSwitchExtension [[-Name] <String>] [-VMMServer <ServerConnection>] -ID <Guid> [<CommonParameters>]
```

### ByVirtualSwitchExtensionManager
```
Get-SCVirtualSwitchExtension [[-Name] <String>] [-VMMServer <ServerConnection>]
 -VirtualSwitchExtensionManager <VirtualSwitchExtensionManager> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualSwitchExtension** cmdlet gets one or more virtual switch extension objects.

## EXAMPLES

### Example 1: Get a virtual switch extension by its name
```
PS C:\> Get-SCVirtualSwitchExtension -Name "VirtualSwitchExtension01"
```

This command gets the virtual switch extension object named VirtualSwitchExtension01 and returns information about the object for the user.

## PARAMETERS

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

### -VirtualSwitchExtensionManager
Specifies a virtual switch extension manager object.
To obtain a virtual switch extension manager object, use the **Get-SCVirtualSwitchExtensionManager** cmdlet.

```yaml
Type: VirtualSwitchExtensionManager
Parameter Sets: ByVirtualSwitchExtensionManager
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-SCVirtualSwitchExtension](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualSwitchExtension.md)

