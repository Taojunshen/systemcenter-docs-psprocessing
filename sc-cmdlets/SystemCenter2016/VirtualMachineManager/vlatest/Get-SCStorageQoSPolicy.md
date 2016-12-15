---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCStorageQoSPolicy.md
schema: 2.0.0
ms.assetid: A5703917-D9F5-4E61-A19F-46B7AC7A7E8A
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageQoSPolicy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageQoSPolicy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageQoSPolicy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageQoSPolicy

## SYNOPSIS
Gets a top-level storage QoS policy object.

## SYNTAX

### All (Default)
```
Get-SCStorageQoSPolicy [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### FileServerFilterParamSet
```
Get-SCStorageQoSPolicy [-VMMServer <ServerConnection>] [[-Name] <String>]
 [-StorageFileServer <StorageFileServer>] [<CommonParameters>]
```

### ArrayFilterParamSet
```
Get-SCStorageQoSPolicy [-VMMServer <ServerConnection>] [[-Name] <String>] [-StorageArray <StorageArray>]
 [<CommonParameters>]
```

### ID
```
Get-SCStorageQoSPolicy [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageQoSPolicy** cmdlet gets a top-level storage Quality of Service (QoS) policy object.

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
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the policy.

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

### -StorageArray


```yaml
Type: StorageArray
Parameter Sets: ArrayFilterParamSet
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFileServer


```yaml
Type: StorageFileServer
Parameter Sets: FileServerFilterParamSet
Aliases: 

Required: False
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

### StorageQoSPolicy
This cmdlet returns a **StorageQoSPolicy** object.

## NOTES

## RELATED LINKS

[New-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageQoSPolicy.md)

[Remove-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageQoSPolicy.md)

[Set-SCStorageQoSPolicy](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageQoSPolicy.md)

