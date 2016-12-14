---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCNativeUplinkPortProfile.md
schema: 2.0.0
ms.assetid: 9FA3653A-3DE0-40A8-A5F1-FD498FD6629D
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCNativeUplinkPortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCNativeUplinkPortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCNativeUplinkPortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCNativeUplinkPortProfile

## SYNOPSIS
Gets a native uplink port profile.

## SYNTAX

### All (Default)
```
Get-SCNativeUplinkPortProfile [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### ById
```
Get-SCNativeUplinkPortProfile [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNativeUplinkPortProfile** cmdlet retrieves a native uplink port profile object.

## EXAMPLES

### Example 1: Get a native uplink port profile by its name
```
PS C:\>$NativeUplinkPortProf = Get-SCNativeUplinkPortProfile -Name "NativeUplinkPortProfile01"
```

This command gets the native uplink port profile object named NativeUplinkPortProfile01 and stores the object in the $NativeUplinkPortProf variable.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ById
Aliases: 

Required: False
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

[New-SCNativeUplinkPortProfile](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCNativeUplinkPortProfile.md)

[Remove-SCNativeUplinkPortProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCNativeUplinkPortProfile.md)

[Set-SCNativeUplinkPortProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCNativeUplinkPortProfile.md)

