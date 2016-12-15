---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCLogicalSwitch.md
schema: 2.0.0
ms.assetid: 8CC9B2A5-3027-4BB9-9A90-68FD8D39D2C3
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitch.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitch.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitch.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCLogicalSwitch

## SYNOPSIS
Gets a logical switch.

## SYNTAX

### All (Default)
```
Get-SCLogicalSwitch [[-Name] <String>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ById
```
Get-SCLogicalSwitch [[-Name] <String>] [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLogicalSwitch** cmdlet gets a logical switch object.

## EXAMPLES

### Example 1: Get a logical switch by its name
```
PS C:\>$LogicalSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
```

This command gets the logical swtich named LogicalSwitch01 and stores it in the $LogicalSwitch variable.

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

[New-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLogicalSwitch.md)

[Remove-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLogicalSwitch.md)

[Set-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLogicalSwitch.md)

