---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageZoneAlias.md
schema: 2.0.0
ms.assetid: 2EFCC310-1EC0-434C-913B-ED4E49A2CE77
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageZoneAlias.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageZoneAlias.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageZoneAlias.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCStorageZoneAlias

## SYNOPSIS
Removes a Fibre Channel zone alias from a fabric.

## SYNTAX

```
Remove-SCStorageZoneAlias [-StorageZoneAlias] <StorageZoneAlias> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCStorageZoneAlias** cmdlet removes a Fibre Channel zone alias from a fabric.

## EXAMPLES

### Example 1: Remove a Fibre Channel zone alias
```
PS C:\>$ZoneAlias = Get-SCStorageZoneAlias -Name "ZoneAlias01"
PS C:\> Remove-SCStorageZoneAlias -StorageZoneAlias $ZoneAlias
```

The first command gets the zone alias object named ZoneAlias01, and then stores that object in the $ZoneAlias variable.

The second command removes the zone alias stored in $ZoneAlias.

## PARAMETERS

### -JobVariable
Specifies the name of a variable that you use to track and store job progress.

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

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageZoneAlias
Specifies a Fibre Channel zone alias that this cmdlet removes.

```yaml
Type: StorageZoneAlias
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageZoneAlias
This cmdlet returns a **StorageZoneAlias** object.

## NOTES

## RELATED LINKS

[Get-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageZoneAlias.md)

[New-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageZoneAlias.md)

[Set-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageZoneAlias.md)

