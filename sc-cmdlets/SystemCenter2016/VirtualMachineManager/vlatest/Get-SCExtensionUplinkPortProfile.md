---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualSwitchExtension.md
schema: 2.0.0
ms.assetid: DA84CBF9-C068-4AAE-8667-F1D7A526C986
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCExtensionUplinkPortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCExtensionUplinkPortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCExtensionUplinkPortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCExtensionUplinkPortProfile

## SYNOPSIS
Gets an extension uplink port profile.

## SYNTAX

### All (Default)
```
Get-SCExtensionUplinkPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ByID
```
Get-SCExtensionUplinkPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>] -ID <Guid>
 [<CommonParameters>]
```

### ByVirtualSwitchExtension
```
Get-SCExtensionUplinkPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>]
 -VirtualSwitchExtension <VirtualSwitchExtension> [<CommonParameters>]
```

### ByVirtualSwitchExtensionManager
```
Get-SCExtensionUplinkPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>]
 -VirtualSwitchExtensionManager <VirtualSwitchExtensionManager> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCExtensionUplinkPortProfile** cmdlet gets one or more extension uplink port profiles.
You can get an extension uplink port profile by its name or ID, or by its virtual switch extension or virtual switch extension manager.

## EXAMPLES

### Example 1: Get extension uplink port profiles
```
PS C:\>Get-SCExtensionUplinkPortProfile
```

This command gets all the extension uplink port profiles and displays their information.

### Example 2: Get an extension uplink port profile using a virtual switch extension
```
PS C:\>$VSE = Get-SCVirtualSwitchExtension -Name "VirtualSwitchExtension01"
 PS C:\> $ExtUPP = Get-SCExtensionUplinkPortProfile --VirtualSwitchExtension $VSE
```

The first command gets a virtual switch extension named VirtualSwitchExtension01 by using the Get-SCVirtualSwitchExtension cmdlet.
The command stores the extension in the $VSE variable.

The second command gets the extension uplink port profiles for this virtual switch extension in $VSE.
This example is valid only if there are some switch extensions installed.

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

### -VirtualSwitchExtension
Specifies a virtual switch extension object.

To get a virtual switch extension object, use the Get-SCVirtualSwitchExtension cmdlet.

```yaml
Type: VirtualSwitchExtension
Parameter Sets: ByVirtualSwitchExtension
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualSwitchExtensionManager
Specifies a virtual switch extension manager object.

To obtain a virtual switch extension manager object, use the Get-SCVirtualSwitchExtensionManager cmdlet.

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

[Get-SCVirtualSwitchExtension](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtension.md)

[Get-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtensionManager.md)

