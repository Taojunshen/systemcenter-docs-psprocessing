---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageZoneAlias.md
schema: 2.0.0
ms.assetid: 7E477BC7-322B-4F8F-90DE-E05CB34959C5
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageZoneAlias.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageZoneAlias.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageZoneAlias.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageZoneAlias

## SYNOPSIS
Modifies an existing Fibre Channel zone alias.

## SYNTAX

```
Set-SCStorageZoneAlias [-StorageZoneAlias] <StorageZoneAlias> [-Name <String>] [-Description <String>]
 [-AddZoneMembership <String[]>] [-RemoveZoneMembership <String[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageZoneAlias** cmdlet modifies an existing Fibre Channel zone alias.

## EXAMPLES

### Example 1: Add and remove members from a zone alias
```
PS C:\>$ZoneAlias = Get-SCStorageZoneAlias -Name "ZoneAlias01"
PS C:\> $AddMember = "C003FF3B8A610000"
PS C:\> $RemoveMember += "D113EF3A8F411234"
PS C:\> Set-SCStorageZoneAlias -StorageZoneAlias $ZoneAlias -AddZoneMembership $AddMember -RemoveZoneMembership $RemoveMember
```

The first command gets the zone alias object named ZoneAlias01, and then stores that object in the $ZoneAlias variable.

The second command assigns a value to the $AddMember variable.

The third command adds a member to the $RemoveMember variable.

The final command adds the member in $AddMember to, and removes the member in $RemoveMember from, the zone alias stored in $ZoneAlias.

### Example 2: Modify the name and description of a zone alias
```
PS C:\>$ZoneAlias = Get-SCStorageZoneAlias -Name "ZoneAlias01"
PS C:\> Set-SCStorageZoneAlias -StorageZoneAlias $ZoneAlias -Name "New Name" -Description "New Description"
```

The first command gets the zone alias object named ZoneAlias01, and then stores that object in the $ZoneAlias variable.

The second command assigns the zone alias stored in $ZoneAlias a new name and a description.

## PARAMETERS

### -AddZoneMembership
Specifies an array of zone members for this cmdlet to add.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the new zone alias.

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

### -Name
Specifies the name of the Fibre Channel zone alias to modify.

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

### -RemoveZoneMembership
Specifies an array of zone members for this cmdlet to remove.

```yaml
Type: String[]
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
Specifies the Fibre Channel zone alias that this cmdlet modifies.

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

[Get-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCStorageZoneAlias.md)

[New-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCStorageZoneAlias.md)

[Remove-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCStorageZoneAlias.md)

