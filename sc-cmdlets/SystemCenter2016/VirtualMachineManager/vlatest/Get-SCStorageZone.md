---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCStorageZone.md
schema: 2.0.0
ms.assetid: 02F660E2-094F-46FD-9AFD-386E9D4851A0
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZone.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZone.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZone.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageZone

## SYNOPSIS
Gets a Fibre Channel zone object.

## SYNTAX

### All (Default)
```
Get-SCStorageZone [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### GetByZoneMember
```
Get-SCStorageZone [-VMMServer <ServerConnection>] [[-Name] <String>] -ZoneMember <String> [<CommonParameters>]
```

### ID
```
Get-SCStorageZone [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageZone** cmdlet gets a Fibre Channel zone object.

## EXAMPLES

### Example 1: Get a storage zone
```
PS C:\>Get-SCStorageZone -Name "Zone01"
```

This command gets the storage zone object named Zone01.

## PARAMETERS

### -All
Indicates that this cmdlet retrieves a full list of all subordinate Fibre Channel zones independent of the parent object with which they are associated.

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
Specifies the unique ID for a Fibre Channel zone.

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
Specifies the name of a Fibre Channel zone object.

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

### -ZoneMember
Specifies a storage zone member.

```yaml
Type: String
Parameter Sets: GetByZoneMember
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

### StorageZone
This cmdlet returns a **StorageZone** object.

## NOTES

## RELATED LINKS

[New-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageZone.md)

[Remove-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageZone.md)

[Set-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageZone.md)

