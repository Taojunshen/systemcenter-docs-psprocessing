---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 61A8BA39-5F72-4004-8B87-139E782FF402
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtensionManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtensionManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtensionManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVirtualSwitchExtensionManager

## SYNOPSIS
Gets a virtual switch extension manager.

## SYNTAX

### GlobalList (Default)
```
Get-SCVirtualSwitchExtensionManager [-VMMServer <ServerConnection>]
 [[-VirtualSwitchExtensionManagerConnectionString] <String>] [-Manufacturer <String>] [-Model <String>] [-All]
 [<CommonParameters>]
```

### ByHostGroup
```
Get-SCVirtualSwitchExtensionManager [-VMMServer <ServerConnection>]
 [[-VirtualSwitchExtensionManagerConnectionString] <String>] [-Manufacturer <String>] [-Model <String>]
 -VMHostGroup <HostGroup> [<CommonParameters>]
```

### ByID
```
Get-SCVirtualSwitchExtensionManager [-VMMServer <ServerConnection>]
 [[-VirtualSwitchExtensionManagerConnectionString] <String>] [-Manufacturer <String>] [-Model <String>]
 -ID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVirtualSwitchExtensionManager** cmdlet gets one or more virtual extension managers.

## EXAMPLES


## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: GlobalList
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

### -Manufacturer
Specifies the name of the company that manufactured a physical device.
The acceptable values for this parameter are:

- letters (a-z) 
- numbers (0-9) 
- underscore (_)
- hyphen (-)
- dot (.)
- single quote (')

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Model
Specifies the model of a physical device.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: ByHostGroup
Aliases: 

Required: True
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

### -VirtualSwitchExtensionManagerConnectionString
Specifies the information required to connect to the virtual switch extension manager.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVirtualSwitchExtensionManager.md)

[Read-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualSwitchExtensionManager.md)

[Remove-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualSwitchExtensionManager.md)

[Set-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualSwitchExtensionManager.md)

[Test-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVirtualSwitchExtensionManager.md)

