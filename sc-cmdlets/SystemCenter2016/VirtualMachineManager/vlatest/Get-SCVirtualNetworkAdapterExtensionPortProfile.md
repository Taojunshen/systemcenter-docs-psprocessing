---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 2af46671-df2a-4372-aed6-682619e368c1
schema: 2.0.0
ms.assetid: 3E0AA3D9-A251-4E65-8360-F9302C2F05E5
updated_at: 12/20/2016 5:21 PM
ms.date: 12/20/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterExtensionPortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterExtensionPortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/485d58d80386539445685faae8425bdc96723376/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterExtensionPortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVirtualNetworkAdapterExtensionPortProfile

## SYNOPSIS
Gets a virtual network adapter extension port profile object.

## SYNTAX

### All (Default)
```
Get-SCVirtualNetworkAdapterExtensionPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

### ByID
```
Get-SCVirtualNetworkAdapterExtensionPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>] -ID <Guid>
 [<CommonParameters>]
```

### ByVirtualSwitchExtension
```
Get-SCVirtualNetworkAdapterExtensionPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>]
 -VirtualSwitchExtension <VirtualSwitchExtension> [<CommonParameters>]
```

### ByVirtualSwitchExtensionManager
```
Get-SCVirtualNetworkAdapterExtensionPortProfile [[-Name] <String>] [-VMMServer <ServerConnection>]
 -VirtualSwitchExtensionManager <VirtualSwitchExtensionManager> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualNetworkAdapterExtensionPortProfile** cmdlet gets one or more virtual network adapter extension port profile objects.

## EXAMPLES


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

To get a virtual switch extension object, use the **Get-SCVirtualSwitchExtension** cmdlet.

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

