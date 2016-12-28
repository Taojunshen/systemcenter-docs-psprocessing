---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DD490ED7-43EA-41E4-B24C-5FC7AE529858
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageZone.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageZone.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageZone.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStorageZone

## SYNOPSIS
Creates a zone in a zone set for a given fabric.

## SYNTAX

```
New-SCStorageZone [-StorageZoneSet] <StorageZoneSet> -Name <String> [-Description <String>]
 [-AddZoneAlias <StorageZoneAlias[]>] [-AddZoneMembership <String[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageZone** cmdlet creates a zone in a zone set for a given fabric.

## EXAMPLES

### Example 1: Create a zone and commit it to the zone set
```
PS C:\> $ZoneSet = Get-SCStorageZoneSet -Name "ZoneSet01"
PS C:\> $Alias = Get-SCStorageZoneAlias -Name "MyArrayPorts"
PS C:\> $Members = @()
PS C:\> $Members += "D113ED3B8A310220"
PS C:\> $Members += "C003FF3B8A610000"
PS C:\> New-SCStorageZone -StorageZoneSet $ZoneSet -Name "MyZone" -Description "Zone for virtual machine host" -AddZoneAlias $Alias -AddZoneMembership $Members -ForceZoneSetActivation
```

The first command gets the zone set object named ZoneSet01, and then stores that object in the $ZoneSet variable.

The second command gets the storage zone alias named MyArrayPorts, and then stores that object in the $Alias variable.

The third command creates an array named $Members.
The fourth and fifth commands populate the $Members array.

The final command creates a storage zone and commits the zone to the zone set stored in $ZoneSet.

### Example 2: Create a zone without committing it to the zone set
```
PS C:\> $ZoneSet = Get-SCStorageZoneSet -Name "ZoneSet01"
PS C:\> $Members = @()
PS C:\> $Members += "D113ED3B8A310220"
PS C:\> $Members += "C003FF3B8A610000"
PS C:\> New-SCStorageZone -StorageZoneSet $ZoneSet -Name "MyZone" -Description "Zone for virtual machine host" -AddZoneMembership $Members
```

The first command gets the zone set object named ZoneSet01, and then stores that object in the $ZoneSet variable.

The second command creates an array named $members.
The third and fourth commands populate the $Members array.

The last command creates a storage zone without committing it to the zone set.

## PARAMETERS

### -AddZoneAlias
Specifies an array of zone aliases that represents one or more world-wide port names.
To obtain a **StorageZoneAlias** object, use the **Get-SCStorageZoneAlias** cmdlet.

```yaml
Type: StorageZoneAlias[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Specifies a description of the storage zone.

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
Specifies the name of the new storage zone.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### -StorageZoneSet
Specifies a storage zone set object.
To obtain a **StorageZoneSet** object, use the **Get-SCStorageZoneSet** cmdlet.

```yaml
Type: StorageZoneSet
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

### StorageZone
This cmdlet returns a **StorageZone** object.

## NOTES

## RELATED LINKS

[Get-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZone.md)

[Get-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZoneAlias.md)

[Get-SCStorageZoneSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZoneSet.md)

[Remove-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageZone.md)

[Set-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageZone.md)

