---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMHostGroup.md
schema: 2.0.0
ms.assetid: EADBF80A-31D1-4FBB-9559-0F7F0765E48B
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCHostReserve.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCHostReserve.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCHostReserve.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCHostReserve

## SYNOPSIS
Gets the host reserve and placement settings for a host group.

## SYNTAX

```
Get-SCHostReserve -VMHostGroup <HostGroup> [-VMMServer <ServerConnection>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCHostReserve** cmdlet retrieves the placement settings for a host group.
In addition to host reserve calculations, placement settings are used for the dynamic optimization and power optimization features.

## EXAMPLES

### Example 1: Get the Host reserve for a specified host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> $HostReserve = Get-SCHostReserve -VMHostGroup $HostGroup
PS C:\> $HostReserve
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command gets the host reserve object for the host group stored in $HostGroup, and then stores the object in the $HostReserve variable.

The last command displays information about the host reserve settings stored in $HostReserve to the user.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ConfigurationProvider
This cmdlet returns a **ConfigurationProvider** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHostGroup.md)

[Set-SCHostReserve](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCHostReserve.md)

