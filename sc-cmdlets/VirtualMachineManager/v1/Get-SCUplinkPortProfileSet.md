---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCUplinkPortProfileSet.md
schema: 2.0.0
ms.assetid: 7B2B7E72-C9C1-4C7B-9F26-C9A58E22A277
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCUplinkPortProfileSet

## SYNOPSIS
Gets uplink port profile sets.

## SYNTAX

### All (Default)
```
Get-SCUplinkPortProfileSet [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### ById
```
Get-SCUplinkPortProfileSet [-VMMServer <ServerConnection>] [[-Name] <String>] -ID <Guid> [<CommonParameters>]
```

### LogicalSwitch
```
Get-SCUplinkPortProfileSet [-VMMServer <ServerConnection>] [[-Name] <String>] -LogicalSwitch <LogicalSwitch>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCUplinkPortProfileSet** cmdlet gets uplink port profile sets.
You can get all uplink port profile sets.
You can specify an uplink port profile set by its name or ID.
You can get all uplink port profile sets for a logical switch.

## EXAMPLES

### Example 1: Get an uplink port profile set by its name
```
PS C:\>Get-SCUplinkPortProfileSet -Name "UplinkPortProfileSet01"
```

This command gets the uplink port profile set named UplinkPortProfileSet01.

### Example 2: Get all uplink port profile sets for a logical swtich
```
PS C:\>$LogSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> Get-SCUplinkPortProfileSet -LogicalSwitch $LogSwitch
```

The first command gets the logical switch object named LogicalSwitch01, and then stores the object in the $LogSwitch variable.

The second command gets all uplink port profile sets for LogicalSwitch01.

## PARAMETERS

### -ID
Specifies the unique ID of the uplink port profile set that this cmdlet gets.

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
Specifies a logical switch for which this cmdlet gets uplink port profile sets.

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
Specifies the name of  the uplink port profile set that this cmdlet gets.

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
Specifies a VMM server on which this cmdlet gets uplink port profile sets.

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

[New-SCUplinkPortProfileSet](xref:VirtualMachineManager/v1/New-SCUplinkPortProfileSet.md)

[Remove-SCUplinkPortProfileSet](xref:VirtualMachineManager/v1/Remove-SCUplinkPortProfileSet.md)

[Set-SCUplinkPortProfileSet](xref:VirtualMachineManager/v1/Set-SCUplinkPortProfileSet.md)

